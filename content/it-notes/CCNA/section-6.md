# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [IP Addressing](#IP Addressing)
  - [IP Header](#IP Addressing#IP Header)
  - [Unicast, broadcast and multicast traffic](#IP Addressing#Unicast, broadcast and multicast traffic)
- [IPv4 Addresses](#IPv4 Addresses)
  - [Automatic and static addresses](#IPv4 Addresses#Automatic and static addresses)

</div>
{{<toc>}}

- The Network layer is responsible for routing packets to their destination and
  for Quality of Service. 
- The IP is most known Layer 3 protocol, mainly the IPv4. This is a connectionless protocol with no acknowledgments at Layer 3.

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
  
