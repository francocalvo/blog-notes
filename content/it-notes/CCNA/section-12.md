# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Domain Name System or DNS](#Domain Name System or DNS)
  - [Router DNS commands](#Domain Name System or DNS#Router DNS commands)
- [Address Resolution Protocol or ARP](#Address Resolution Protocol or ARP)
  - [ARP through a router](#Address Resolution Protocol or ARP#ARP through a router)

</div>
{{<toc>}}

# Domain Name System or DNS

- The DNS resolves Fully Qualified Domain Names (FQDN) like www.francocalvo.ar
  to an IP address.
- Enterprises will typically have an internal DNS server which can resolve the
  IP addresses for internal hosts.
- Hosts will send their DNS queries to this server.
- If the internal DNS server cannot resolve a query, it will forward the
  request out to public DNS server on the internet.
- DNS request are sent using UDP port 53 (can fail over to TCP).

In a local DNS server, we can set custom records for hosts in the domain the
server is authoritative.

## Router DNS commands

To configure your router as a DNS client, you need to:
- `ip domain-lookup`
- `ip name-server 172.23.4.1`
- `ip domain-name flackboxA.lab`
- `ip domain-list flackboxB.lab`

If you wanted your router to be DNS server, you need to: 
- `ip dns server` 
- `ip host LinuxA 172.23.4.2` 

This is not normally used.

# Address Resolution Protocol or ARP

The sender needs to know the receiver's IP address and MAC address to form the
packet it's going to send. We could use both an IP or a FQDN, where a DNS
maintains a mapping of FQDN to IP addresses. On the other hand, ARP is used to
map IP addresses to MAC addresses. 

Both these protocols allows us, by knowing just a FQDN, compose a complete
packet to send.

If we got to hosts, a sender and a host, where the sender knows just the IP
address, it can get to the Layer 3 of the packet composing. After that, it'll
do a ARP request to the |switch, asking for the correct MAC address for that IP.
This ARP request has the following settings:
- Source MAC: 1111.2222.3333
- Destination MAC: FFFF.FFFF.FFFF

The switch is then going to flood it's connected hosts, looking for the MAC
address for that IP. When the receiver gets the request, it'll give an **ARP
Reply**, which returns its MAC address, which the switch will forward to the
sender.

These ARP replies are saved in a hosts ARP cache, so it doesn't need to send a
request every time it needs to communicate.

You can see this cache in Linux using `arp -n`.

## ARP through a router

When the sender and receiver are on different IP subnets, the traffic must be
forwarded by a router.

In the following example, the IP address `172.23.4.1/24` wants to send a packet
to `192.168.10.1/24`. 

We can't have ARP broadcast traffic through the router, so we need another
method. For this, the sender is not going to send an ARP request for the
receiver, since it knows it need to send it via a router, so it'll send its ARP
request to its default getaway. It'll look like this:

- ARP Request for *Default getaway* `172.23.4.254`.
- Source MAC: 1111.2222.3333
- Destination MAC: FFFF.FFFF.FFFF

This request will hit everything in the `172.23.4.0/24` subnet, including the
router. The router will see its an ARP request for itself, which it'll reply.
In this example the MAC address is going to be `4444.5555.6666`.

Now, the sender knows where to send the ARP request for the destination MAC
address, so it will now send this IP packet:

**IP Packet** 
- Source IP: `172.23.4.1`
- Destination IP: `192.168.10.1`
- Source MAC: `1111.2222.3333`
- Destination MAC: `4444.5555.6666`

This packet will hit the router, and it'll know it needs to send this packet to
the IP address `192.168.10.1`. If the router doesn't know its MAC address,
it'll send its own ARP request. When it finds the final MAC address, it'll
forward the packet to the destination, replacing the MAC address from the
sender for its own.


