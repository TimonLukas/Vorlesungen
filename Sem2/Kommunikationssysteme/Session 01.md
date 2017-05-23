# Session 01

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Computer Networks](#computer-networks)
  * [Uses](#uses)
  * [Business applications](#business-applications)
  * [Home applications](#home-applications)
  * [Mobile users](#mobile-users)
  * [Wireless, mobile](#wireless-mobile)
  * [Social issues](#social-issues)
* [Network hardware](#network-hardware)
  * [Classification](#classification)
* [Network software](#network-software)
  * [Protocol layers](#protocol-layers)
  * [Design issues for the layers](#design-issues-for-the-layers)
  * [Connection-oriented vs. connectionless](#connection-oriented-vs-connectionless)
    * [Connetion-oriented](#connetion-oriented)
    * [Connectionless](#connectionless)
  * [Service primitives](#service-primitives)
  * [Relationship of services to protocols](#relationship-of-services-to-protocols)
* [Reference models](#reference-models)
  * [OSI Reference model](#osi-reference-model)
  * [TCP/IP Reference model](#tcpip-reference-model)
  * [Model used in this course](#model-used-in-this-course)
  * [Critique of OSI & TCP/IP](#critique-of-osi-tcpip)
    * [OSI](#osi)
    * [TCP/IP](#tcpip)
* [Internet](#internet)
  * [History](#history)
    * [ARPANET](#arpanet)
    * [NSFNET](#nsfnet)
    * [Today](#today)
* [Network standardization](#network-standardization)
* [Metric units](#metric-units)

<!-- tocstop -->

## Computer Networks
### Uses
* *Computer networks* are collections of autonomous computers, e. g. the Internet
* Many different uses
  * Business applications
  * Home applications
  * Mobile users
* These uses raise
  * Social issues
  * Political issues

### Business applications
* Companies use networks and computers for resource sharing
* Use the client-server model
  * Client &rarr; request &rarr; server &rarr; response &rarr; client
* Other popular uses are communication
  * E-Mail
  * VoIP
  * eCommerce
  * File servers

### Home applications
* Homes contain many networked devices
  * Computers
  * TV
* Connected to the internet by:
  * Cable
  * DSL
  * Wireless
* Home users:
  * Communicate (e. g. social networks)
  * Consume content (e. g. videos)
  * Transact (e. g. auctions)
* Some applications use the peer-to-peer model
  * No fixed clients and servers

### Mobile users
* Tablets, laptops and smartphones are popular devices
* Connected by WiFi hotspots, 3G
* Mobile users
  * Communicate (voice and texts)
  * Consume content (video and web)
  * Use sensors (GPS)

### Wireless, mobile
|Wireless |Mobile |Typical applications                     |
|---------|-------|-----------------------------------------|
|No       |No     |Desktop computers in offices             |
|No       |Yes    |A notebook computer used in a hotel room |
|Yes      |No     |Networks in unwired buildings            |
|Yes      |Yes    |Store inventory with a handheld computer |

### Social issues
* Network neutrality (no network restrictions)
* Content ownership, e. g. DMCA takedowns
* Anonymity and censorship
* Privacy, e. g. web tracking and profiling
* Theft, e. g. botnets and phishing

## Network hardware
### Classification
|Scale    |Type                                   |
|---------|---------------------------------------|
|Vicinity |PAN (Personal Area Network)            |
|Building |LAN (Local Area Network)               |
|City     |MAN (Metropolitan Area Network)        |
|Country  |WAN (Wide Area Network)                |
|Planet   |The Internet (network of all networks) |

## Network software
### Protocol layers
* Protocol layering is the main structuring method used to divide up network functionality
* Each protocol instance talks virtually to its peer
* Each layer communicates only by using the one below
* Lower layer services are accessed by an interface
* At bottom, messages are connected by the medium (e. g. cable)
* Each layer adds its own header (with control information) to the message to transmit and removes it on receive
* Layers may also split and join messages, etc.

### Design issues for the layers
* Each layer solves a particular problem
* Must include mechanisms to address a set of recurring design issues

|Issue|Example mechanisms at different layers|
|-----|--------------------------------------|
|Reliability despite failures|Codes for error detection/correction (§3.2, 3.3)<br />Routing around failures (§5.2)|
|Network growth and evolution|Addressing (§5.6) and naming (§7.1)<br />Protocol layering (§1.3)|
|Allocation of resources like bandwidth|Multiple access (§4.2)<br />Congestion control (§5.3, 6.3)|
|Security against various threats|Confidentiality of messages (§8.2, 8.6)<br />Authentication of communicating parties (§8.7)|

### Connection-oriented vs. connectionless
* Services provided by a layer may be kinds of either
#### Connetion-oriented
* Must be set up for ongoing use (and torn down after use), e. g. phone call

|Service                |Example          |
|-----------------------|-----------------|
|Reliable message stream|Sequence of pages|
|Reliable byte stream   |Movie download   |
|Unreliable connection  |Voice over IP    |
#### Connectionless
* Messages are handled seperately, e. g. postal delivery

|Service              |Example              |
|---------------------|---------------------|
|Unreliable datagram  |Electronic junk mail |
|Acknowledged datagram|Text messaging       |
|Request-reply        |Database query       |

### Service primitives
* A service is provided to the layer above as primitives
* Hypothetical example of service primitives that may provide a reliable byte stream (connection-oriented) service:

|Primitive  |Meaning                                    |
|-----------|-------------------------------------------|
|LISTEN     |Block waiting for incoming connection      |
|CONNECT    |Establish a connection with a waiting peer |
|ACCEPT     |Accept an incoming connection from a peer  |
|REVEICE    |Block waiting for incoming message         |
|SEND       |Send a message to the peer                 |
|DISCONNECT |Terminate a connection                     |

* Hypothetical example of how these primitives may be used for a client-server interaction

|                     |Client   |                 |Server   |                       |
|---------------------|---------|-----------------|---------|-----------------------|
|                     |         |                 |         |LISTEN (0)             |
|CONNECT (1)          |&rarr;   |Connect request  |&rarr;   |                       |
|                     |&larr;   |Accept response  |&larr;   |ACCEPT<br />RECEIVE (2)|
|SEND<br />RECEIVE (3)|&rarr;   |Request for data |&rarr;   |                       |
|                     |&larr;   |Reply            |&larr;   |SEND (4)               |
|DISCONNECT (5)       |&rarr;   |Disconnect       |&rarr;   |                       |
|                     |&larr;   |Disconnect       |&larr;   |DISCONNECT (6)         |

### Relationship of services to protocols
* A layer provides a **service** to the one above (vertical)
* A layer talks to its peer using a **protocol** (horizontal)

## Reference models
* Describe the layers in a network architecture
* Examples
  * OSI reference model
  * TCP/IP reference model

### OSI Reference model
* Principled, international standard
* Seven layer model to connect different systems

|Layer|Content|Explanation|
|-----|-------|-----------|
|7    |Application|Provides functions needed by users|
|6    |Presentation|Converts different representations|
|5    |Session|Manages task dialogs|
|4    |Transport|Provides end-to-end delivery|
|3    |Network|Sends packets over multiple links|
|2    |Data link|Sends frames of information|
|1    |Physical|Sends bits as signals|

### TCP/IP Reference model
* Four layer model
* Derived from experimentation
* Omits some OSI layers
* Uses the IP as the network layer

|Layer      |Protocols                        |
|-----------|---------------------------------|
|Application|[HTTP] [SMTP] [RTP] [DNS]        |
|Transport  |[TCP] [UDP]                      |
|Internet   |[IP] [ICMP]                      |
|Link       |[DSL] [SONET] [802.11] [Ethernet]|

* IP is the "narrow waist" of the Internet

### Model used in this course
* Based on the TCP/IP model
* Call out the physical layer and look beyond IP

|Layer|Content    |
|-----|-----------|
|5    |Application|
|4    |Transport  |
|3    |Network    |
|2    |Link       |
|1    |Physical   |

### Critique of OSI & TCP/IP
#### OSI
* Very influential model with clear concepts
* Models, protocols and adoption all bogged down by politics and complexity

#### TCP/IP
* Very successful protocols that worked well and thrived
* Weak model derived after the fact from protocols

## Internet
### History
#### ARPANET
* Before the Internet was the ARPANET
  * Decentralized, packet-switched network
  * Based on Baran's ideas
* Nodes were IMPs, or early routers, linked to hosts
* 56 kbps links

#### NSFNET
* Early internet used NSFNET (1985 - 1995) as its backone
* Universities connected to get on the internte
* T1 links (1.5 Mbps)

#### Today
* Modern internet is more complex
* ISP networks serve as the Internet backbone
* ISPs connect or peer to exchange traffic at IXPs
* Within each network routers switch packets
* Between networks, traffic exchange is set by business agreements
* Customers connect at the edge by many means
  * Cable
  * DSL
  * Fiber-to-the-Home
  * 3G/4G wireless
  * Dialup
* Data centers concentrate many servers ("the cloud")
* Most traffic is content from data centers (esp. video)
* The architecture continues to evolve

## Network standardization
* Standards define what is needed for interoperability
* Some of the many standards bodies:

|Body |Area               |Examples                                   |
|-----|-------------------|-------------------------------------------|
|ITU  |Telecommunications |G.992, ADSL, H.264, MPEG4                  |
|IEEE |Communications     |802.3, Ethernet, 802.11, WiFi              |
|IETF |Internet           |RFC 2616, HTTP/1.1, RFC 1034/RFC 1035, DNS |
|W3C  |Web                |HTML5 standard, CSS standard               |

## Metric units
* Main prefixes:

|Prefix     |Exp.           |
|-----------|---------------|
|n(ano)     |10<sup>-9</sup>|
|&mu;(micro)|10<sup>-6</sup>|
|m(illi)    |10<sup>-3</sup>|
|K(ilo)     |10<sup>3</sup> |
|M(ega)     |10<sup>6</sup> |
|G(iga)     |10<sup>6</sup> |

* Use powers of 10 for rates
* Powers of 2 for storage
  * E. g. 1 Mbps = 1,000,000 bps, 1 KB = 1024 bytes
* "B" is for bytes
* "b" is for bits
