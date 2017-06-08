# Session 03

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [The Data Link Layer](#the-data-link-layer)
* [Frames](#frames)
  * [Possible services](#possible-services)
  * [Framing methods](#framing-methods)
    * [Byte count](#byte-count)
    * [Byte stuffing](#byte-stuffing)
    * [Bit stuffing](#bit-stuffing)
    * [Error control](#error-control)
    * [Flow control](#flow-control)
  * [Error detection and correction](#error-detection-and-correction)
    * [Parity](#parity)
    * [Checksum](#checksum)
    * [CRCs](#crcs)
* [Link layer environment](#link-layer-environment)
* [Example protocols](#example-protocols)
  * [Utopian Simplex Protocol](#utopian-simplex-protocol)
    * [Sender](#sender)
    * [Receiver](#receiver)
  * [Stop-and-wait protocol (Error-free channel)](#stop-and-wait-protocol-error-free-channel)
    * [Sender](#sender-1)
    * [Receiver](#receiver-1)
  * [Sliding-window](#sliding-window)
* [The MAC sublayer](#the-mac-sublayer)
  * [Channel allocation problem](#channel-allocation-problem)
  * [ALOHA](#aloha)

<!-- tocstop -->

## The Data Link Layer
* Responsible for delivering frames of information over a single link
* Handles transmission errors and regulates the flow of data

## Frames
* Link layer accepts **packets** from the network layer
* Encapsulates them into **frames**
* Sends the frames using the physical layer
* Reception is the opposite process

### Possible services
* Unacknowledged connectionless service
  * Frame is sent with no connection/error recovery
  * Ethernet
* Acknowledged connectionless service
  * Frame is sent with retransmissions if needed
  * Example is 802.11
* Acknowledged connection-oriented service
  * Connection is set up; rare

### Framing methods
* Byte count
* Flag byte with byte stuffing
* Flag bits with bit stuffing
* Physical layer coding violations
  * Use non-data symbol to indicate frame

#### Byte count
* Frame begins with a count of the number of bytes in it

#### Byte stuffing
* Special **flag** bytes delimit frames
* Occurrences of flags in the data must be stuffed (escaped)
* Longer, but easy to resynchronize after an error

#### Bit stuffing
* Stuffing done at the bit level
* Frame flag has six consecutive 1s
* On transmit, after five 1s, a 0 is added
* On receive, a 0 after five 1s is deleted

#### Error control
* Error control repairs frames that are received in error
* Requires errors to be detected at the receiver
* Typically retransmit unacknowledged frames
* Timer protects against lost acknowledgements

#### Flow control
* Prevents a fast sender from out-pacing a slow receiver
* Receiver gives feedback on the data it can accept
* Rare in the link layer as NICs run at "wire speed"
  * Receiver can take data as fast as it can be sent
* Topic in the Link and Transport layers

### Error detection and correction
* Error codes add structured redundancy to data so errors can either be detected or corrected
* There are different error correction codes
  * Hamming codes
  * Binary convolutional codes
  * Reed-Solomon and Low-Density Parity Check codes
    * Mathematically complex, widely used in real systems
* Error detection codes
  * Parity
  * Checksums
  * Cyclic redundancy codes

#### Parity
* Parity bit is added as the modulo 2 sum of data bits
  * Equivalent to XOR; this is even parity
  * Example: 1110000 &rarr; 11100001
  * Detection checks if the sum is wrong (an error)
* Simple way to detect an *odd* number of errors
  * Example: 1 error, 11100101: detected, sum is wrong
  * Example: 3 errors, 11011001: detected, sum is wrong
  * Example: 2 errors, 11101101: Not detected, sum is right!

#### Checksum
* Checksum treats data as N-bit words and adds  N check bits that are the modulo 2^N sum of the words
* Example: Internet 16-bit 1s complement checksum
* Improved error detection

#### CRCs
* Adds bits so that transmitted frame viewed as a polynomial is evenly divisible by a generator polynomial
* Based on standard polynomials
* Computed with simple shift/XOR circuits
* Stronger detection than checksums
  * Can detect all double bit errors
  * Not vulnerable to systematic errors

## Link layer environment
* Commonly implement as NICs and OS drivers
* Network layer (IP) is often OS software

## Example protocols
### Utopian Simplex Protocol
* An optimistic protocol to get us started
  * Assumes no error
  * Receiver as fast as senders* Considers one-way data transfers

#### Sender
```
void sender1(void) {
  frame s;
  packet buffer;

  while (true) {
    from_network_layer(&buffer);
    s.info = buffer;
    to_physical_layer(&s);
  }
}
```

#### Receiver
```
void receiver1(void) {
  frame r;
  event_type event;

  while (true) {
    wait_for_event(&event);
    from_physical_layer(&r);
    to_network_layer(&r.info);
  }
}
```

### Stop-and-wait protocol (Error-free channel)
* Protocol ensures sender can't outpace receiver
* Receiver returns a dummy frame (ack) when ready
* Only one frame out at a time - called stop-and-wait

#### Sender
```
void sender2(void) {
  frame s;
  packet buffer;
  event_type event;

  while (true) {
    from_network_layer(&buffer);
    s.info = buffer;
    to_physical_layer(&s);
    wait_for_event(&event);
  }
}
```

#### Receiver
```
void receiver2(void) {
  frame r, s;
  event_type event;

  while (true) {
    wait_for_event(&event);
    from_physical_layer(&r);
    to_network_layer(&r.info);
    to_physical_layer(&s);
  }
}
```

### Sliding-window
* Sender maintains window of frames it can send
  * Needs to buffer them for possible retransmission
  * Window advances with next acknowledgements
* Receiver maintains window of frames it can receive
  * Need to keep buffer space for arrivals
  * Window advances with in-order arrivals
* Larger windows enable **pipelining** for efficient link use
  * Stop-and-wait (w=1) is inefficient for long links
  * Best window (w) depends on bandwidth-delay (BD)
  * Want w &geq; 2BD+1 to ensures high link utilization
* Pipelining leads to different choices for errors/buffering
  * We will consider **Go-Back-N** and **Selective Repeat**

## The MAC sublayer
* Responsible for deciding who sends next on a multi-access link
* Important part of the link layer, especially for LANs

### Channel allocation problem
* For fixed channel and traffic from N users
  * Divide up bandwidth using FTM, TDM, CDMA etc
  * This is a static allocation, e. g. FM radio
* Sstatic allocation performs poorly from bursty traffic
  * Allocation to a user will sometimes go unused
* Dynamic allocation gives the channel to a user when they need it
  * Potentially N times as efficient for N users

|Assumption                 |Implication                                  |
|---------------------------|---------------------------------------------|
|Independent traffic        |Often not a good model, but permits analysis |
|Single channel             |No external way to coordinate senders        |
|Observable collisions      |Needed for reliability; mechanisms vary      |
|Continuous or slotted time |Slotting may improve performance             |
|Carrier sense              |Can improve performance if available         |

### ALOHA
* In pure ALOHA, users transmit frames whenever they have data
* Collisions happen when other users transmit during a vulnerable period that is twice the frame timing
* Slotted ALohA is twice as efficient as the pure ALOHA
  * Low load wastes slots, high loads cause collisions
  * Efficiency up to 1/e (37%) for random traffic models
