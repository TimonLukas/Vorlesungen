# Session 02

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Abbreviations](#abbreviations)
* [Guided Transmission (Wires & Fibres)](#guided-transmission-wires-fibres)
  * [Reality check](#reality-check)
  * [Wires](#wires)
    * [Twisted pair](#twisted-pair)
      * [Link terminology](#link-terminology)
    * [Coaxial Cable ("Co-ax")](#coaxial-cable-co-ax)
    * [Power lines](#power-lines)
    * [Fiber cables](#fiber-cables)
  * [Wireless Transmission](#wireless-transmission)
    * [Electromagnetic Spectrum](#electromagnetic-spectrum)
    * [Radio transmission](#radio-transmission)
    * [Microwave transmission](#microwave-transmission)
    * [Light transmission](#light-transmission)
* [Wireless vs. Wires/Fiber](#wireless-vs-wiresfiber)
  * [Wireless](#wireless)
    * [Pros](#pros)
    * [Cons](#cons)
  * [Wires/Fiber](#wiresfiber)
    * [Pros](#pros-1)
    * [Cons](#cons-1)
* [Communication satellites](#communication-satellites)
  * [Kinds of satellites](#kinds-of-satellites)
* [Satellite vs. Fiber](#satellite-vs-fiber)
  * [Satellite](#satellite)
    * [Pros](#pros-2)
    * [Cons](#cons-2)
  * [Fibre](#fibre)
    * [Pros](#pros-3)
    * [Cons](#cons-3)
* [The Public Switched Telephone Network](#the-public-switched-telephone-network)
  * [Structure of the telephone system](#structure-of-the-telephone-system)
  * [Local loop: Modems, ADSL and FFTH](#local-loop-modems-adsl-and-ffth)
    * [Modem](#modem)
    * [Digital Subscriber Lines](#digital-subscriber-lines)
    * [Fiber To The Home](#fiber-to-the-home)
  * [Switching](#switching)
  * [Generation of mobile telephone systems](#generation-of-mobile-telephone-systems)
    * [1G (analog voice)](#1g-analog-voice)
    * [2G (analog voice and digital data)](#2g-analog-voice-and-digital-data)
    * [3G (digital voice and data)](#3g-digital-voice-and-data)
    * [4G (digital data including voice)](#4g-digital-data-including-voice)
  * [Internet over Cable](#internet-over-cable)

<!-- tocstop -->

## Abbreviations
* VLF: Very low frequency
* LF: Low frequency
* MF: Medium frequency
* HF: High frequency

## Guided Transmission (Wires & Fibres)
* Media have different properties, hence performance
* Reality check
  * Storage media
* Wires
  * Twisted pairs
  * Coaxial cable
  * Power lines
* Fibre lines

### Reality check
* Send data on tape/disk/DVD for a high bandwidth link
  * Mail one box with 1,000 800 GB tapes (6,400 Tbit)
  * Takes on day to send (86,400 seconds)
  * Data rate is 70 Gbps
* Data rate is faster than long-distance networks
* Message delay is poor

### Wires
#### Twisted pair
* Very common
* Used in LANs, telephone lines
* Twists reduce radiated signal (interference)

##### Link terminology
* Full-duplex link
  * Used for transmission in both directions at once
  * E. g. use different twisted pairs for each direction
* Half-duplex link
  * Both directions, but not at the same time
  * E. g. senders take turns on a wireless channel
* Simplex link
  * Only one fixed direction at all times
  * Not common

#### Coaxial Cable ("Co-ax")
* Also common
* Better shielding and more bandwidth for longer distances and higher rates than twisted pair
* Consists of:
  * Copper core
  * Insulating material
  * Braided outer conductor
  * Protective plastc covering

#### Power lines
* Household electrical wiring is another example of wires
* Convenient to use, but horrible for sending data

#### Fiber cables
* Common for high rates and long distances
  * Long distance ISP links, Fiber-to-the-Home
  * Light carried in a very long, thin strand of glass

### Wireless Transmission
#### Electromagnetic Spectrum
* Differents bands have different uses
  * Radio: Wide-area broadcast
  * Infrared/Light: Line-of-sight
  * Microwave: LANs and 3G/4G
* To manage intereference, the spectrum is carefully divided
  * It's use is regulated and licensed (e. g. sold at an auction)
* There are also unlicsended ("ISM") bands
  * Free for use at low power-lines
  * Devices manage interference
  * Widely used for networking
    * WiFi
    * Bluetooth

#### Radio transmission
* Radio signals penetrate buildings well
* They propagate for long distances with path loss
* VLF, LF and MF band signals follow the curvature of the earth
* HF band signals bounce off the ionosphere

#### Microwave transmission
* Microwaves have a lot of bandwidth and are widely used indoors (WiFi) and outdoors (3G)

#### Light transmission
* Line-of-sight light (no fiber) can be used for links)
  * Light is highly directional, has a lot of bandwidth
  * Use of LEDs/cameras and lasers/photodetectors

## Wireless vs. Wires/Fiber
### Wireless
#### Pros
* Easy and inexpensive to deploy
* naturally supports mobility
* Naturally supports broadcast

#### Cons
* Transmissions interfere and must be managed
* Signal strengths (hence data rates) vary greatly

### Wires/Fiber
#### Pros
* Easy to engineer a fixed data rate over point-to-point links

#### Cons
* Can be expensive to deploy, especially over distances
* Doesn't readily support mobility or broadcast

## Communication satellites
* Satellites are effective for broadcast distribution and anywhere/anytime connection

### Kinds of satellites
* Satellites and their properties vary by altitude
  * Geostationary (GEO) (35k km, 270ms latency)
  * Medium-Earth Orbit (MBO) (6k to 15k, 35-85ms latency)
  * Low-Earth Orbit (LEO) (<5k, 1-7ms latency)

|Type               |Abbreviation |Altitude (km)|Latency|Satellites needed for global coverage|
|Geostationary      |GEO          |35k          |270ms  |3                                    |
|Medium-Earth Orbit |MEO          |6k to 15k    |35-85ms|10                                   |
|Low-Earth Orbit    |LEO          |<5k          |1-7ms  |50                                   |

## Satellite vs. Fiber
### Satellite
#### Pros
* Can rapidly set up anywhere/anytime communications (after satellites have been launched)
* Can broadcast to large regions

#### Cons
* Limited bandwidth and interference to manage

### Fibre
#### Pros
* Enormous bandwidth over long distances

#### Cons
* Installation can be more expensive/difficult

## The Public Switched Telephone Network
### Structure of the telephone system
* A hierarchical system for carrying voice calls
  * Local loops, mostly analog twisted pairs to houses
  * Trunks, digital fiber optic links that carry calls
  * Switching offices, that move calls among trunks

### Local loop: Modems, ADSL and FFTH
#### Modem
* Modulator/Demodulator
* Telephones modems send digital data over an 3.3 KHz analog voice channel interface to the POTS
* Rates < 56kbps
* Early way to connect to the internet

#### Digital Subscriber Lines
* DSL broadband sends data over the local loop to the local office using frequencies that are not used for POTS
* Telephones/computers attach to the same old phone line
* Rates vary with line
  * ADSL2 up to 12Mbps
* OFDM is used up to 1.1 MHz for ADSL2
  * Most bandwidth down

#### Fiber To The Home
* FTTH broadband relies on deployment of fiber optic cables to provide high data rates customers
  * One wavelength can be shared among many houses
  * Fiber is passive (no amplifiers etc.)

### Switching
* PSTN uses circuit switching (a physical line is established)
* Internet uses packet switching (a theoretical connection is established)
* Circuit switching requires call setup (connection) before data flows smoothly
  * Also teardown at the end
* Packet switching treats messages independently
  * No setup, but variable queuing delay at routers

|Item                               |Circuit switched |Packet switched|
|-----------------------------------|-----------------|---------------|
|Call setup                         |Required         |Not needed     |
|Dedicated physical path            |Yes              |No             |
|Each packet follows the same route |Yes              |No             |
|Packets arrive in order            |Yes              |No             |
|Is a switch crash fatal            |Yes              |No             |
|Bandwidth available                |Fixed            |Dynamic        |
|Time of possible congestion        |At setup time    |On every packet|
|Potentially wasted bandwidth       |Yes              |No             |
|Store-and-forward transmission     |No               |Yes            |
|Charging                           |Per minute       |Per packet     |

### Generation of mobile telephone systems
#### 1G (analog voice)
* AMPS (Advanced Mobile Phone System)
* 1980s
* Modulation based on FM (as in radio)

#### 2G (analog voice and digital data)
* GSM (Global System for Mobile communications)
* 1990s
* Modulation based on QPSK

#### 3G (digital voice and data)
* UMTS (Universal mobile Telecommunications System)
* 2000s
* Modulation based on CDMA

#### 4G (digital data including voice)
* LTE (Long Term Evolution)
* 2010s
* Modulation based on OFDM

### Internet over Cable
* Internet over cable reuses the cable television plant
* Data is sent on the shared cable tree from the head-end
* Not on a dedicated line per subscriber (DSL)
