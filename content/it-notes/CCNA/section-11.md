# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Switches and hubs](#Switches and hubs)
  - [Hubs](#Switches and hubs#Hubs)
- [Switches](#Switches)
- [Switch Operation](#Switch Operation)
  - [Simple setup](#Switch Operation#Simple setup)
  - [More complex setup](#Switch Operation#More complex setup)
- [Routers](#Routers)
- [Other products](#Other products)
- [Lab exercise](#Lab exercise)

</div>
{{<toc>}}

# Switches and hubs

Hubs and switches perform a similar function, where you take your end hosts in
a LAN such as PCs, and plug them in with an Ethernet cable. This will allow the
end hosts to communicate with each other through the hub or switch.

## Hubs

- Hubs always operate in *half-duplex* mode, meaning attached hosts cannot send
  and receive data at the same time.
- All hosts share the same **collision domain**, meaning only one device can
  transmite at a time. If two hosts send at the same time, a collision will
  occur.
- The method to recover from collision is CSMA/CD, or Carrier-Sense Multiple
  Access with Collision Detection to detect collisions and resend.

These operate at OSI Level 1, meaning that they are not MAC address aware, and
because of that, whenever a frame is received, it is flooded out all ports
apart from the one it was received on, and all attached hosts must process all
packets.

# Switches

- Switches can operate at *full-duplex* or *half-duplex*.
- Attached hosts can both send and receive data at the same time.
- All hosts have their own dedicated collision domain.
- Collision detection is not required.

A big difference with hubs is:
- Switches operate at the OSI Layer 2, meaning they are MAC address aware.
  Whenever a frame is received, the switch will look at the source MAC address
  in the header of the Layer 2.
- The learned MAC address will be added to the switch's MAC address table,
  which maps MAC addresses to ports.
- If a unicast frame is later received with a known MAC address as the
  destination, the switch will send the frame out only to the relevant port.

This is better for performance and security as frames only go where they are
required. Whenever a frame is received for the broadcast address or an unknown
unicast destination, it will be flooded out all the ports apart from the one it
was received on.


# Switch Operation

## Simple setup

If we got three PC connected to a switch like:

- `1.1.1` connected to Port 1.
- `2.2.2` connected to Port 2.
- `3.3.3` connected to Port 3.

Lets suppose the switch is just powered on, so the MAC address is empty. If the
address `1.1.1` sends a frame to `2.2.2`, the switch learns that the Port 1 has
the MAC `1.1.1`. Then, the switch will flood all ports, sending the frame to
the `2.2.2` and `3.3.3`, which will discard it. Then, the `2.2.2`  will send
some traffic back to `1.1.1`, which the switch will see, and it'll put the Port
2 to the MAC `2.2.2.2`.

## More complex setup

In a more complex operation, where we got a switch connected to another, the
function is very similar, but the switches will map the ports that connect them
to the MAC address. Then, the second switch can map the frame to the correct
MAC using its own table. What's interesting, that one port can be mapped to
more than one MAC address, but not the other way.

# Routers

- Routers know the paths to get to different IP subnets on a network.
- They are required to send traffic from one subnet to another.
- Routers operate at the Layer 3 of the OSI model.

Comparing them to switches, we see that:
- Routers can route traffic between different networks, while switches can
  switch traffic between hosts on the same LAN.
- Routers support many interfaces such as Ethernet, Serial, ISDN, etc.
- Switches normally have more ports than routers.
- Switches forward broadcast traffic, routers don't by default.

# Other products


Other CISCO products are: 

- **Security** : the Cisco ASA (Adaptive Security Appliance) Firewall.
- **Wireless**:  Cisco Wireless Access Points and LAN controllers.
- **Collaboration:** Cisco IP phones, WebEx, TelePresences, etc.
- **Datacenter**: Cisco UCS (Unified Computing System) or Cisco Nexus Switches.

# Lab exercise 

**First part:** 
- R1: GigEth 0/0 10.10.10.1. MAC: 0090.2b82.ab01
- R2: GigEth 0/0 10.10.10.2. MAC: 0060.2fb3.9152
- R3: GigEth 0/1 10.10.10.3. MAC: 0001.9626.8970
- R4: GigEth 0/0 10.10.10.4. MAC: 00d0.9701.02a9

After pinging each router from *R1*, and accessing the switch *SW1*, I can see
the following MAC address table:

```ios
SW1#show mac address-table dynamic 
          Mac Address Table
-------------------------------------------

Vlan    Mac Address       Type        Ports
----    -----------       --------    -----

   1    0001.9626.8970    DYNAMIC      Fa0/24
   1    000c.cf84.8418    DYNAMIC      Fa0/24
   1    0060.2fb3.9152    DYNAMIC      Fa0/2
   1    0090.2b82.ab01    DYNAMIC      Fa0/1
   1    00d0.9701.02a9    DYNAMIC      Fa0/24
```

Doing the same in *SW2* yields:

```ios
SW2#sh mac-address-table 
          Mac Address Table
-------------------------------------------

Vlan    Mac Address       Type        Ports
----    -----------       --------    -----

   1    0001.9626.8970    DYNAMIC     Fa0/3
   1    000b.be53.6418    DYNAMIC     Fa0/24
   1    0060.2fb3.9152    DYNAMIC     Fa0/24
   1    0090.2b82.ab01    DYNAMIC     Fa0/24
   1    00d0.9701.02a9    DYNAMIC     Fa0/4
```

You can clear the dynamic MAC address table with the following command:

```ios
clear mac address-table dynamic
```

We can configure an interface entering this:

```ios
R1#configure terminal 
Enter configuration commands, one per line.  End with CNTL/Z.
R1(config)#interface gigabitEthernet 0/1
R1(config-if)#ip address 10.10.20.1 255.255.255.0
R1(config-if)#no shutdown 
```

This will configure the interface and generate two routes, one connected, to 
`10.10.20.0/24` and one local to `10.10.20.1/32`.

Lastly, you can configure a static route to another subnet like this:

```ios
R1(config)#ip route 10.10.30.0 255.255.255.0 10.10.10.2
```

---

I've found this about **local** and **connected** routes:

> A connected route is one that is assigned directly to an interface. A local
> route is one that is one that is not known by a protocol. But since static
> routes are considered a 'protocol', that only happens in the case of secondary
> addresses on the interfaces.
