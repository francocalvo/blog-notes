# Table of contents

<div class="hidden">
# Contents

- [Table of contents](#Table of contents)
- [Basics](#Basics)
    - [Characteristics:](#Basics#Characteristics:)
  - [Open Systems Interconnect Model](#Basics#Open Systems Interconnect Model)
    - [Benefits](#Basics#Open Systems Interconnect Model#Benefits)
      - [OSI Acronyms](#Basics#Open Systems Interconnect Model#Benefits#OSI Acronyms)
  - [TCP/IP Suite](#Basics#TCP/IP Suite)
    - [Protocol data unit (PDU)](#Basics#TCP/IP Suite#Protocol data unit (PDU))
  - [OSI Layers](#Basics#OSI Layers)
    - [Layer 7: Application layer](#Basics#OSI Layers#Layer 7: Application layer)
    - [Layer 6: Presentation layer](#Basics#OSI Layers#Layer 6: Presentation layer)
    - [Layer 5: Session layer](#Basics#OSI Layers#Layer 5: Session layer)
    - [Layer 4: Transport layer](#Basics#OSI Layers#Layer 4: Transport layer)
    - [Layer 3: Network layer](#Basics#OSI Layers#Layer 3: Network layer)
    - [Layer 2:  Data-link layer](#Basics#OSI Layers#Layer 2:  Data-link layer)
    - [Layer 1: Physical layer](#Basics#OSI Layers#Layer 1: Physical layer)

</div>

{{<toc>}}

# Basics

Switches allow us to connect different devices via Ethernet in the same Local
Area Network or LAN. Also, this switch can connect to a _Router_, which
connects directly to the internet, allowing us connect our LAN to internet.
Also, you can put a firewall between the router and the exterior to protect the
connections.
In the case that we also need to connect to another LAN, you can create a Wide
Area Network or WAN.

### Characteristics:

- Topology.
- Speed.
- Cost.
- Security.
- Availability.
- Scalability.
- Reliability.

## Open Systems Interconnect Model


The OSI reference model is a standard from ISO  standardises how computers
communicate with one another over a network. It has seven layers for data
transmission, dividing the operations into specific related group of actions at
each layer. A layer serves the layer above it and is served by the one below it.

This is, when a senders sends a __packet__ it needs to format it. This means:

1. Application.
2. Presentation.
3. Session.
4. Transport: TCP/UPD and port.
5. Network: source and destination IP address. (important for routers)
6. Data-link: it includes the MAC address. (Important for switches)
7. Physical.

When the receiver gets the packet, it checks for these layers in the inverse 
order.

### Benefits

The benefit of this model is that allows engineers to focus on just on one layer
instead of having to design a end to end, top to bottom model. 

#### OSI Acronyms

The most classic one is:

- **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way.

## TCP/IP Suite

This is a protocol stack which consists in two protocols including the
Transmission Control Protocol (TCP) and the Internet Protocol (IP). The
difference between this and the OSI model is conceptual, this stack is actually
used in production networks. 

This model also simplifies the layers of the OSI model, reducing the first three
in the same one and the last to in the another one, living us with:

4. **Application**: represents data users, encodes and controls the dialog.
3. **Transport**: supports communication between end devices across a diverse 
   network
2. **Internet**: provides a logical addressing and determines the best path 
   through the network.
1. **Network access**: control the hardware devices and media that make up the
   network.

### Protocol data unit (PDU)

When two hosts are communicating, the exchange PDUs, and depending which layer
we are talking, they'll have different names, being: data, segment, packet and
frames.

## OSI Layers
### Layer 7: Application layer 
- We start with the Layer 7, which provides network services to the
  applications or the user. 
- The main difference is that it doesn't provide services to any other OSI
  layer.
- The application establishes availability of intended communication between
  partners. 
- It then synchronizes and establishes agreement on procedures for error
  recovery and control of data integrity.

### Layer 6: Presentation layer
- This layer ensures that the information that is sent at the application layer
  of one system is readable by the application layer of another system.
- The presentation layer can translate among multiple data formats using a
  common format.

### Layer 5: Session layer
- This layer establishes, manages and terminates sessions between two
  communicating hosts.
- The sessions also syncs dialog between the presentation of two hosts and manages their data exchange.

### Layer 4: Transport layer
- It defines whether TCP or UDP transport is used, and the port number.
- Definition:
  -  The transport layer defines services to segment, transfer, and reassemble
     the data for individual communications between the end devices.
  - It breaks down large files into smaller segments that are less likely to incur transmission problems.

- It defines whether TCP or UDP transport is used, and the port number.
- Definition:
  -  The transport layer defines services to segment, transfer, and reassemble
     the data for individual communications between the end devices.
  - It breaks down large files into smaller segments that are less likely to incur transmission problems.

### Layer 3: Network layer
- It provides the source and destination IP address. Routers operates in this
  layer.
- Definition:
  -  The network layer provides connectivity and path selection between two
     host system that may be located on geographically separated networks.
  - The network layer is the layer that manages the connectivity of hosts by
    providing logical addressing.

### Layer 2:  Data-link layer
- It provides the source and destination layer 2 address, like the MAC address.
  Switches operate at layer 2.
- Definition:
  - The data link layer defines how data is formatted for transmission and how
    to access physical media is controlled.
  - It also includes error detection and correction to ensure a reliable
    delivery of the data.

### Layer 1: Physical layer
- This layer concerns literally the physical components like the cables.
- Definition:
  - The physical link enables bit transmission between end devices.
  - It defines specifications needed for activating, maintaining and
    deactivating the physical link between end devices.
