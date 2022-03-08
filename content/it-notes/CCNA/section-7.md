# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Class A](#Class A)
  - [Subnetting](#Class A#Subnetting)
- [Class B](#Class B)
- [Class C](#Class C)
- [Private addresses](#Private addresses)
- [Class D](#Class D)
- [Class E](#Class E)

</div>
{{<toc>}}

# Class A

- These class of addresses are assigned to networks with a very large number of
  hosts.
- The high-order bit in a class A is always set to zero and the default mask is
  /8.
- Its valid networks addresses go from `1.0.0.0` to `126.0.0.0/8`.
- It allows for 126 networks, with 16777214 hosts per network.
- Both the `0.0.0.0/8` and `127.0.0.0/8` are reserved addresses.

## Subnetting

- Companies noramlly split their `/8` address allocation into smaller subnets
  and allocate these to different offices and types of hosts.
- For example if they received `15.0.0.0/8`, they could allocate the subnet
  `15.0.1.0/24` to an office and `15.0.2.0/24` to another.

# Class B

- Class B addresses are assigned to medium to large sized networks.
- The two high order pits in a class B address are always set to binary `1 0`.
- The default subnet mask is `/16`.
- Valid networks addresses range from `128.0.0.0` to `192.255.0.0/16`.
- This allows for 16384 networks and 65434 hosts per network.
- This would also be subnetted in a real world environment.

# Class C

- These classes are used for small networks.
- The three high-order bits in a class C address are always set to binary `1 1 0`.
- The default subnet mask is `/24`.
- Valid network addresses go from `192.0.0.0` to `223.255.255.0/24`.
- This allows for 2097152 networks and 254 hosts per network.

# Private addresses

There are valid addresses to be assigned to hosts but they are not routable on
the public internet. They were originally designed for hosts in a closed
private network with no internet connectivity. The ranges are:

- Class A: `10.0.0.0` to `10.255.255.255`.
- Class B: `172.16.0.0` to `172.31.255.255`.
- Class C: `192.168.0.0` to `192.168.255.255`.

# Class D

- These addresses are reserved for IP multicast addresses.
- The four high-order bits in a class D address are always set to binary
  `1 1 1 0`. 
- These addresses are not allocated to hosts and there is not default subnet
  mask.
- Valid addresses range from `224.0.0.0` to `239.255.255.255`.

# Class E 

- These addresses are experimental and reserved for future use.
- The high-order address is set to `1 1 1 1`.
- These addresses are not allocated to hosts and there is not default subnet
  mask.
- Valid addresses range from `240.0.0.0` to `255.255.255.255`.
- The last is the broadcast address for this network.


