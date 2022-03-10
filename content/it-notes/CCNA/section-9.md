# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
  - [Ethernet header](#Table of contents#Ethernet header)
- [Media Access Control (MAC)](#Media Access Control (MAC))

</div>
{{<toc>}}

- The **frames** are encoded and decoded into bits at Layer 2. 
- Error detection and correction for the physical layer can be provided here.
- Ethernet is the Layer 2 medium used on Local Area Network.

When a packet is composed, the sender goes from the top of the OSI model down.
During the 7-5 layers, it's called **data**, in the Layer 4 (Transport), it's
called **segment**, in Layer 3 (Network), it's called **packet** and in this
layer it's called **frame**.

## Ethernet header

It's composed of:

- Preamble: 8 bytes.
- Destination address: 6 bytes.
- Source address: 6 bytes.
- Length/Ethertype: 2 bytes.
- Data: from 45-1500 bytes.
- Frame Check Sequence (FCS): 4 bytes.

# Media Access Control (MAC)

- Ethernet uses a 48 bit hexadecimal MAC address.
- The first 24 bits is the Organizationally Unique Identifier or OUI, which
  uniquely identifies the manufacturer of the Ethernet port.
- The last 24 bits is vendor assigned.
- The burned in MAC address on every NIC port in the world is globally unique.

