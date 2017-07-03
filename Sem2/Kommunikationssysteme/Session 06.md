# Session 06

## Network Fragmentation Example
* 2KByte message + 20 Byte Header = 2068KByte
* Sent along a path:
* A &rarr; X1 &rarr; (MTU 1024 Byte) X2 &rarr; (MTU 512 Byte) B
* 20 Byte Header is correct for IPv4 packets (might be larger with Options)

## IP Version 4 Protocol
### Time To Live
* If circular routing exists, a packet would not kill the routers by living forever

### Prefixes
* Addresses are allocated in blocks called **prefixes**
* Prefix is determined by the network portion
* Has 2^L addresses aligned on 2^L boundary
* Written address/length, e. g. 19.0.31.0/24

### Subnetting
* Subnetting splits up IP prefix to help with management
* Looks like a single prefix outside of the network
* Example:
  * 128.208.0.0/18
  * 128.208.128.0/17
  * 128.208.96.0/19
  * Outside: 128.208.0.0/16

### Aggregation
* Aggregation joins multiple IP prefixes into a single larger prefix to reduce routing table size

### Classful Addressing
* Old addresses came in blocks of fixed size (A, B, C)
* Carries size as part of address, but lacks flexibility
* Called classful (vs. classless) addressing

### NAT
* NAT (Network Address Translation) box maps one external IP address to many internal IP addresses
* Uses TCP/UDP port to tell connections apart
* Violates layering
* Very common in homes etc.

### Network Address
* Specified by the subnet mask
* 192.168.1.38 with subnet mask 24 (255.255.255.0): 192.168.1.0
* Network address = IP address &and; mask

### Broadcast Address
* Also reliant on the network mask
* 192.168.1.38 with subnet mask 27 (255.255.255.224): 192.168.1.63
* BC address = IP address &or; &not;mask
* Highest address in space
