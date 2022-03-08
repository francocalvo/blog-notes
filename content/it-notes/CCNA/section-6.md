# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [IP Addressing](#IP Addressing)
  - [IP Header](#IP Addressing#IP Header)
  - [Unicast, broadcast and multicast traffic](#IP Addressing#Unicast, broadcast and multicast traffic)
- [IPv4 Addresses](#IPv4 Addresses)
  - [Automatic and static addresses](#IPv4 Addresses#Automatic and static addresses)
  - [Subnet masks](#IPv4 Addresses#Subnet masks)
    - [Host portion](#IPv4 Addresses#Subnet masks#Host portion)
    - [Slash notation](#IPv4 Addresses#Subnet masks#Slash notation)

</div>
{{<toc>}}

- The Network layer is responsible for routing packets to their destination and
  for Quality of Service. 
- The IP is most known Layer 3 protocol, mainly the IPv4. This is a
  connectionless protocol with no acknowledgments at Layer 3.

# IP Addressing

- IP addressing is a logical addressing scheme which is implemented at Layer 3.
- The network designer uses IP addressing to partition the overall network into
  smaller subnets.
- This improves performance, security and makes troubleshooting easier.
- Layer 2 MAC addresses use una big flat addressing scheme. There is no logical
  separation between networks at Layer 2.

## IP Header

Important information in the header is the IP version, type of service, source
and destination IP address, Time To Live (TTL) field, 


The TTL is a counter, where the router keeps track of how many times a packet
went through it by decreasing the TTL specified. If it gets to 0 it will drop
de packet.

%% TODO: add image for the IP header

## Unicast, broadcast and multicast traffic

There are three types of IP traffic:

- Unicast traffic is to a single destination host.
- Broadcast traffic is to all hosts on the subnet. It doesn't go through
  routers.
- Multicast traffic is to multiple interested hosts. This allows to reduce the
  load on the bandwith of the subnet.

All of these are working inside the subnet, traveling through the switches and
routers.


# IPv4 Addresses

- An IPv4 address is 32 bits long.
- It's written as 4 octets in dotted decimal format.
- Each octet is 8 bits long.

As each octet is 8 bits long, the binary number `11111111` is 255, meaning no
number will be bigger than that. 

## Automatic and static addresses

- The IP address is usually manually set on servers, printers, etc and
  automatically assigned through the Dynamic Host Configuration Protocol DHCP
  on other computers.
  
## Subnet masks

- A host can send traffic directly to another host on the same subnet via
  switches.
- For a host to send traffic to another host in a different subnet, it most be
  forwarded by a router.
- The host need to understand if the destination is on the same or a different
  subnet in order to know how to send it. This is what a subnet mask does.

If the destination is in the same subnet, the host will send it directly,
otherwise it'll send it to the router.

Let's say you have a host IP and submask like `192.168.10.15/255.255.255.0`.
First, the IP address is compared with the subnet mask. Normally, a `1`
indicates that that bit in the IP address is part of the network address, and a
`0` that is part of the host address.

In our example, the network address part would be `192.168.10` and the host
portion of the address is `15`. It means that if the host wants to send
something to another host in the same subnet, like `192.168.10.25`, it can do
so directly. If it wants to send to another subnet, it'll have to send it
through a router.

### Host portion

The host portion of the address is available to be allocated to the different
hosts on the subnet, except for two cases. Also, the host portion must be unique on the subnet.

The exception are:
- All 0 in the host portion designates the network address, and is not allowed.
- All 1 in the host portion designates the directed broadcast address, and is
  not allowed.

This means we can have 253 different devices per subnet, from 1 to 254.

### Slash notation

Because the subnet mask always begins with contiguous `1`, it will be a 1 to 32 bits long counting from left to right. This allows us to write the subnet mask in slash notation, which is more convenient.

For example, for the previous example, we could write it is like:
`192.168.10.15/24`, as we subtract 8 bit for the host address.


