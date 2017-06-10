# Session 04

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Ethernet](#ethernet)
  * [Classic Ethernet](#classic-ethernet)
    * [Physical layer](#physical-layer)
    * [MAC](#mac)
  * [Switched/Fast Ethernet](#switchedfast-ethernet)
  * [Gigabit/10 Gigabit Ethernet](#gigabit10-gigabit-ethernet)
* [Data Link Layer Switching](#data-link-layer-switching)
  * [Uses of Bridges](#uses-of-bridges)
  * [Learning Bridges](#learning-bridges)
* [Repeaters, Hubs, Bridges, Switches, Routers, Gateways](#repeaters-hubs-bridges-switches-routers-gateways)
* [Virtual LANs](#virtual-lans)

<!-- tocstop -->

## Ethernet
* FF FF FF FF FF FF (all bits are 1s) as receiver address is a broadcast
### Classic Ethernet
#### Physical layer
* One shared coaxial cable
* All hosts attached to that cable
* Up to 10 Mbps (with Manchester encoding)
* Hosts ran the classic Ethernet protocol for access

#### MAC
* MAC protocol is 1-persistent CSMA/CD (earlier)
* Random delay (backoff) after collision is computed with BEB (Binary Exponential Backoff)
* Frame format is still used with modern Ethernet
* Collisions can occur and take as long as 2&tau; to get detected
* &tau; is the time it takes to propagate over the Ethernet
* Leads to minimum packet size for reliable detection
* Efficient for large frames
  * Even with many senders
  * Degrades for small frames (over long LANs)

### Switched/Fast Ethernet
* Hubs wire all lines into a single CSMA/CD domain
* Switches isolate each port to a separate domain
  * Much greater throughput for multiple ports
  * No need for CSMA/CD with full-duplex lines
* Fast Ethernet extended Ethernet from 10 to 100 Mbps
  * Twisted pair (with Cat 5) dominated the market

|Name       |Cable        |Max. segment |Advantages                         |
|-----------|-------------|-------------|-----------------------------------|
|100Base-T4 |Twisted pair |100m         |Uses category 3 UDP                |
|100Base-TX |Twisted pair |100m         |Full duplex at 100Mbps (Cat 5 UDP) |
|100Base-FX |Fiber optics |2000m        |Full duplex at 100Mbps; long runs  |

### Gigabit/10 Gigabit Ethernet
* Switched Gigabit Ethernet is now the garden variety
  * With full-duplex lines between computers/switches

## Data Link Layer Switching
### Uses of Bridges
* Common setup is a building with centralized wiring
  * Bridges (switches) are placed in or near wiring closets

### Learning Bridges
* A bridge operates as a switched LAN (not a hub)
  * Computers, bridges and hubs connect to its ports
* Backward learning algorithm picks the output port
  * Associates the source address on frame with input port
  * Frame with destination address is sent to learned port
  * Unlearned destinations are sent to all other ports
* Needs no configuration
  * Forget unused addresses to allow changes
  * Bandwidth efficient for two-way traffic

## Repeaters, Hubs, Bridges, Switches, Routers, Gateways
* Devices are named according to the layer they process
   * A bridge or LAN switch operators in the Link layer

|Layer            |Device             |
|-----------------|-------------------|
|Application layer|Application gateway|
|Transport layer  |Transport gateway  |
|Network layer    |Router             |
|Data link layer  |Bridge, Switch     |
|Physical layer   |Repeater, Hub      |

## Virtual LANs
* VLANs (Virtual LANs) splits one physical LAN into multiple logical LANs to ease management tasks
  * Port are "colored" according to their VLAN
* 802.1Q frames carry a color tag (VLAN identifier)
  * Length/Type value is 0x8100 for VLAN protocol
