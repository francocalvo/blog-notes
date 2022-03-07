# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [TCP](#TCP)
  - [TCP Header](#TCP#TCP Header)
- [UPD](#UPD)
- [TCP vs UDP](#TCP vs UDP)

<div>
{{<toc>}}

- The Transport layer provides transparent transfer of data between hosts and
  is responsible for the end-to-end recovery and flow control.
- The flow control is the process of adjusting the flow of data to ensure that
  the receiver can handle all of it.
- It also supports session multiplexing, meaning its a process by which the
  host is able to support multiple sessions simultaneously and manage the
  individual traffic streams over a single link. For this, it uses port
  numbers. Normally, HTTP uses 80, SSH 22, etc. The host will also add a random
  source port number, where the receiver is going to respond to.

# TCP

- TCP is connection oriented, meaning once a connection is established, data
  can be sent bidirectionally over that connection.
- TCP carries out sequencing to ensure segments are processed in the correct
  order and none are missing.
- TCP is reliable, meaning that the receiving host sends acknowledgments back
  to the sender, and if it doesn't receive one, the packet is going to be
  resent.
- TCP performs flow control.

This is done by a three-way handshake, where the sender first sends a
__Synchronized Message__ (SYN) over to the receiver, which he'll answer with an
__Synchronized Acknowledgments__ (SYN-ACK). Finally, the sender is
going to send an acknowledgments (ACK).


## TCP Header

The TCP header contains important information about the packet sent. This
includes the source port, destination port, sequence number, checksum and other
information.


%% TODO: Add image of TCP header

# UPD

- The User Datagram Protocol sends traffic best effort.
- It's not connection oriented, meaning there is no handshake connection setup.
- It doesn't carry out sequencing to ensure all segments are processed in the
  correct order.
- It's not reliable, as the receiver doesn't send back acknowledgments.
- It doesn't perform flow control.
- All error detection is up to the upper layers.

It's header is way more simple, having just four fields: source and destination
port, length and UDP checksum. 

%% TODO: Add image of UDP header

# TCP vs UDP

- Application developers will typically choose to use TCP for traffic which
  requieres reliability.
- Real-time applications like VOIP can't afford the extra overhead.
- Some applications use both TCP and UDP, like a DNS application.
