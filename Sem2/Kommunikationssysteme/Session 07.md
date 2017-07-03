# Session 07

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [IP Version 6](#ip-version-6)
* [Internet Control Protocols](#internet-control-protocols)
* [BGP - Exterior Routing Protocol](#bgp-exterior-routing-protocol)
* [Transport Layer](#transport-layer)
  * [Transport Service](#transport-service)
    * [Services provided to the Upper Layers](#services-provided-to-the-upper-layers)
    * [Transport Service Primitives](#transport-service-primitives)
    * [Berkeley Sockets](#berkeley-sockets)
  * [Elements of Transport Protocols](#elements-of-transport-protocols)
    * [Addressing](#addressing)
    * [Connection Establishment](#connection-establishment)
    * [Error Control and Flow Control](#error-control-and-flow-control)
* [Internet Protocols](#internet-protocols)
  * [UDP](#udp)
  * [RPC (Remote Procedure Call)](#rpc-remote-procedure-call)
  * [TCP](#tcp)
    * [Service Model](#service-model)
    * [Connection Establishment](#connection-establishment-1)
    * [Sliding Window](#sliding-window)
    * [Congestion Control](#congestion-control)

<!-- tocstop -->

## IP Version 6
* Major upgrade in the 1990s due to impending address exhaustion
* Lots of advantages
  * Support billions of hosts
  * Reduce routing table size
  * Simplify protocol
  * Better security
  * Attention to type of service
  * Aid multicasting
  * Roaming host without changing address
  * Allow future protocol evolution
  * Permit coexistence of old, new protocols, ...
* Deployment has been slow & painful
  * May pick up pace now that all addresses are exhausted
* IPv6 protocol header has much longer addresses
  * 128 vs. 32 bits
  * Is simpler (by using extension headers)

## Internet Control Protocols
* IP works with the help of several control protocols
* **ICMP** is a companion to IP that returns error info
  * Required
  * Used in many ways, e. g. traceroute
* **ARP** finds Ethernet address of local IP address
  * Glue that is needed to send any IP packets
  * Host queries an address and the owner replies
* **DHCP** assigns a local IP address to a host
  * Gets host started by automatically configuring it
  * Host sends request to server, which grants a lease

## BGP - Exterior Routing Protocol
* BGP (Border Gateway Protocol) computes routes across interconnected, autonomous networks
* Key role is to respect networks' policy constraints
* Example constraints:
  * No commercial traffic for educational network
  * Never put Iraq on route starting at Pentagon
  * Choose cheaper network
  * Choose better performing network
  * Don't go from Apple to Google to Apple

## Transport Layer
* Responsible for delivering data across networks with desired reliability or quality
### Transport Service
#### Services provided to the Upper Layers
* Transport layer adds reliability to the network layer
* Offers connectionless (e. g. UDP) and connection-oriented (e. g. TCP) service to applications
* Transport layer sends **segments** in packets (in frames)
#### Transport Service Primitives
* Primitives that applications might call to transport data for a simple connection-oriented service
  * Client calls CONNECT, SEND, RECEIVE, DISCONNECT
  * Server calls LISTEN, RECEIVE, SEND, DISCONNECT

|Primitive  |Segment sent       |Meaning                                    |
|-----------|-------------------|-------------------------------------------|
|LISTEN     |(none)             |Block until some process tries to connect  |
|CONNECT    |CONNECTION REQ.    |Actively attempt to establish a connection |
|SEND       |DATA               |Send information                           |
|RECEIVE    |(none)             |Block until a DATA packet arrives          |
|DISCONNECT |DISCONNECTION REQ. |This side wants to release the connection  |

#### Berkeley Sockets
* Very widely used primitives started with TCP on Unix

### Elements of Transport Protocols
#### Addressing
* Transport layer adds TSAPs (Transport Services Access Point)
* Multiple clients and servers can run on a host with a single network (IP) address
* TSAPs are ports for TCP/UDP

#### Connection Establishment
* Key problem is to ensure reliability even though packets may be lost, corrupted, **delayed** and **duplicated**
* Don't treat an old or duplicate packet as new
* Use ARQ and checksums for loss/corruption
* Three-way handshake used for initial packet
  * No state from previous connection
  * Both hosts contribute fresh seq. numbers
  * CR = Connection Request
* Three-way handshake protects against odd cases
  * Duplicate CR. Spurious ACK does not connect
  * Duplicate CR and DATA. Same plus DATA will be rejected (wrong ACK)

#### Error Control and Flow Control
* Foundation for error control is a sliding window (from Link layer) with checksums and retransmissions
* Flow control manages buffering at the sender/receiver
  * Issue is that data goes from/to the network and applications at different times
  * Window tells sender available buffering at receiver

## Internet Protocols
### UDP
* UDP (User Datagram Protocol) is a shim over IP
* Header has ports (TSAPs), length and checksum

### RPC (Remote Procedure Call)
* RPC connects applications over the network with the familiar abstraction of procedure calls
* Stubs package parameters/results into a message
* UDP with retransmissions is a low-latency transport

### TCP
* TCP provides applications with a reliable byte stream between processes
* "Workhorse of the Internet"
* Popular servers run on well-known ports

#### Service Model
* Applications using TCP see only the byte stream and not the segments sent as separate IP packets

#### Connection Establishment
* TCP sets up connections with the three-way handshake
* Release is symmetric, also as described before

#### Sliding Window
* TCP adds flow control to the sliding window as before
* ACK + WIN is the sender's limit
* Need to add special cases to avoid unwanted behaviour
  * E. g. silly window syndrome

#### Congestion Control
* TCP uses AIMD with loss signal to control congestion
* Implemented as a **congestion window** (cwnd) for the number of segments that may be in the network
* Uses several mechanisms that work together
* Congestion window controls the sending rate
  * Rate is cwnd/RTT; window can stop sender quickly
