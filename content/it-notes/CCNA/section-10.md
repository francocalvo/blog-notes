# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Connection types](#Connection types)
  - [Straight-through vs Crossover UTP](#Connection types#Straight-through vs Crossover UTP)
  - [Fiber cables](#Connection types#Fiber cables)
  - [Power over Ethernet (PoE)](#Connection types#Power over Ethernet (PoE))

</div>
{{<toc>}}

- The OSI Layer 1 conveys the bit stream, electrical impulse, light, radio,
  etc, through the network at the electrical and mechanical level.
- It provides the hardware menas of sending and receiving data.

# Connection types

- Ethernet LAN connections can be carried over coaxial cable, twisted copper
  pair cable, fiber cable or wireless.
- It's commonly used the copper UTP (unshielded twisted pair) to connect to
  switches, which a connector type RJ-45.

## Straight-through vs Crossover UTP

- The receive and transmit wires in a UTP cable can be wired to the RJ-45
  connector as either straight-trough or crossover. 
- Straight-through cables are used to connect an end device like a router or PC.
- Crossover cables are used to connect devices together directly, like to
  devices of the same type.
- Modern switches support Auto MDI-X, where the receive and transmit signals
  are reconfigured automatically to yield the expected result.

## Fiber cables

- Fiber optic cables can be used to support longer distances or higher
  bandwidth requirements. 
- For example, between separate buildings in a campus, or for switch to switch
  connections inside a building.

The fiber can be single mode or multi-mode, where single mode supports higher
bandwidth and longer distances, but is more expensive.

Also, fiber connectors are very different.

## Power over Ethernet (PoE)

This allows to give power to certain stuff like repeaters, Raspberry Pi, etc.
This can be achieved by PoE switches or a Power Injector.
