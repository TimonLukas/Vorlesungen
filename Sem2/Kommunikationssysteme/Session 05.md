# Session 05

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [The Network Layer](#the-network-layer)
  * [Store-and-Forward Packet Switching](#store-and-forward-packet-switching)
    * [Connectionless Service - Datagrams](#connectionless-service-datagrams)
    * [Connection-Oriented - Virtual Circuits](#connection-oriented-virtual-circuits)
  * [Comparison of Virtual-Circuits & Datagrams](#comparison-of-virtual-circuits-datagrams)
* [Routing](#routing)
  * [Routing Algorithms](#routing-algorithms)
  * [The Optimality Principle](#the-optimality-principle)
  * [Shortest Path Algorithm](#shortest-path-algorithm)
    * [Algorithm](#algorithm)
  * [Flooding](#flooding)
  * [Distance Vector Routing](#distance-vector-routing)
  * [Hierarchical routing](#hierarchical-routing)
  * [Routing for Mobile Hosts](#routing-for-mobile-hosts)
  * [Traffic-Aware Routing](#traffic-aware-routing)
* [Quality of Service](#quality-of-service)
  * [Application requirements](#application-requirements)
  * [Traffic shaping](#traffic-shaping)
  * [Packet Scheduling](#packet-scheduling)
* [Internetworking](#internetworking)
  * [How networks differ](#how-networks-differ)
  * [How Networks Can Be Connected](#how-networks-can-be-connected)
* [Packet Fragmentation](#packet-fragmentation)
* [Network Layer in the Internet](#network-layer-in-the-internet)
  * [IP version 4 Protocol](#ip-version-4-protocol)

<!-- tocstop -->

## The Network Layer
* Responsible for delivering packets between endpoints over multiple links

### Store-and-Forward Packet Switching
* **Hosts** send **packets** into the network
* **Packets** are **forwarded** by **routers**

#### Connectionless Service - Datagrams
* Packet is forwarded using destination address inside it
* Different packets may take different paths

#### Connection-Oriented - Virtual Circuits
* Packet is forwarded along a virtual circuit using tag inside it
* Virtual circuit (VC) is set up ahead of time

### Comparison of Virtual-Circuits & Datagrams
|Issue                    |Datagram network                                           |Virtual-circuit network|
|-------------------------|-------------------------------------------------------------|-----------------------------------------------------------------|
|Circuit setup            |Not needed                                                 |Required                                                   |
|State information        |Each packet contains the full source and destination address |Each packet contains a short VC number                           |
|State information        |Routers do not hold state information about connections      |Each VC requires router table space per connection               |
|Routing                  |Each packet is routed independently                          |Route chosen when VC is set up; all packets follow it      |
|Effect of router failures|None, except for packets lost during the crash               |All VCs that passed through the failed router are terminated    |
|Quality of service       |Difficult                                                    |Easy if enough resources can be allocated in advance for each VC |
|Congestion control       |Difficult                                                    |Easy if enough resources can be allocated in advance for each VC |

## Routing
### Routing Algorithms
* **Routing** is the process of discovering network paths
* Model the network as a graph of nodes and links
* Decide what to optimize (e. g. fairness vs. efficiency)
* Update routes for changes in topology (e. g. failures)
* **Forwarding** is the sending of packets along a path

### The Optimality Principle
* Each portion of a best path is also a best path
* The union of them to a router is a tree called a *sink tree*
* Best means fewest hops in the example

### Shortest Path Algorithm
* **Dijkstra**'s algorithm computes a skind tree on the graph
  * Each link is assigned a non-negative weight/distance
  * Shortest path is the one with lowest total weight
  * Using weights of 1 gives paths with fewest hops

#### Algorithm
* Start with sink, set distance at other nodes to infinity
* Relax distance to other nodes
* Pick the lowest distance node, add it to the sink tree
* Repeat until all nodes are in the sink tree

### Flooding
* A simple method to send a packet to all network nodes
* Each node floods a new packet received on an incoming link by sending it out to all of the other links
* Nodes need to keep track of flooded packets to stop the flood; even using a hop limit can blow up exponentially

### Distance Vector Routing
* **Distance vector** is a distributed routing algorithm
  * Shortest path computation is split across nodes
* Algorithm
  * Each node knows distance of links to its neighbours
  * Each node advertises vector of lowest known distances to all neighbors
  * Each node uses received vectors to update its own
  * Repeat periodically
* Basically, each node sends the distance to its neighbours, which allows building up a table of weights for **Dijkstra**'s algorithm

### Hierarchical routing
* Hierarchical routing reduces the work of route computation but may result in slightly longer paths than flat routing

### Routing for Mobile Hosts
* Mobile hosts can be reached via a home agent
* Fixed home agent tunnels packets to reach the mobile host
* Reply can optimize path for subsequent packets
* No changes to routers or fixed hosts

### Traffic-Aware Routing
* Choose routes depending on traffic, not just topology
* E. g., use one route if another is loaded
* Take care to avoid oscillation

## Quality of Service
### Application requirements
* Different applications care about different properties
* We want all applications to get what they need


|Application      |Bandwidth|Delay    |Jitter   |Loss   |
|-----------------|---------|---------|---------|-------|
|E-Mail           |Low      |Low      |Low      |Medium |
|File sharing     |**High** |Low      |Low      |Medium |
|Web access       |Medium   |Medium   |Low      |Medium |
|Remote login     |Low      |Medium   |Medium   |Medium |
|Audio on demand  |Low      |Low      |**High** |Low    |
|Video on demand  |High     |Low      |**High** |Low    |
|Telephony        |Low      |**High** |**High** |Low    |
|Vidoeconferencing|**High** |**High** |**High** |Low    |
**Bold** means a demanding requirement, e. g. low delay

* Network provides service with different kinds of QoS (Quality of Service) to meet application requirements


|Network Service                |Application      |
|-------------------------------|-----------------|
|Constant bit rate              |Telephony        |
|Real-time variable bit rate    |Videoconferencing|
|Non-real-time variable bit rate|Streaming a move |
|Available bit rate             |Filesharing      |

### Traffic shaping
* Traffic shaping regulates the average rate and burstiness of data entering the network
* Lets us make guarantees
* Token/Leaky bucket limits both the average rate (R) and short-term burst (B) of traffic
* For token, bucket size is B, water enters at rate R and is removed to send
* For leaky, bucket size is B, water leaves at rate R and is put in

### Packet Scheduling
* Packet scheduling divides router/link resources among traffic flows with alternatives to FIFO
* Fair Queueing approximates bit-level fairness with different packet sizes
* Weights change target levels
* Result is WFQ (Weighted Fair Queueing)

## Internetworking
* Internetworking joins multiple, different networks into a single, larger network

### How networks differ
* Differences can be large
* Complicates internetworking

### How Networks Can Be Connected
* Internetworking based on a common network layer - IP  

## Packet Fragmentation
* Networks have different packet size limits for many reasons
* Large packets sent with fragmentation & reassembly
* Path MTU discovery avoids network fragmentation
  * Routers return MTU (Max. Transmission Unit) to source and discard large packets

## Network Layer in the Internet
* IP has been shaped by guiding principles
  * Make sure it works
  * Keep it simple
  * Make clear choices
  * Exploit modularity
  * Expect heterogenity
  * Avoid static options and parameters
  * Look for good design (not perfect)
  * Strict sending, tolerant receiving
  * Think about scalability
  * Consider performance and cost
* Internet is an interconnected collection of many networks that is held together by the IP protocol

### IP version 4 Protocol
* IPv4 header is carried on all packets and has fields for the key parts of the protocol
  * DF = Do not fragment
  
