# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Classless Inter-Domain Routing (CIDR)](#Classless Inter-Domain Routing (CIDR))
  - [Subnetting example](#Classless Inter-Domain Routing (CIDR)#Subnetting example)

</div>
{{<toc>}}


# Classless Inter-Domain Routing (CIDR)

- A problem with classful addresses was that if a company had more than 254
  hosts they would need to be assigned a Class B network.
- They would have much less than the 65534 hosts allocated, so this was a huge
  amount of the global address space being wasted.

CIDR removed the fixed `/8`, `/16` and `/24` requirements for the address
classes, and allowed them to be split into smaller networks, like
`175.10.0.0/20` . This alsow restricts issues to the local part of the network
and reduces CPU load.


## Subnetting example

Let's say that you work for a company with 4 departments in two different
offices. You could buy four different Class C IP ranges, or buy a single one
and subnet it.

To subnet the network into smaller subnets, we need to "borrow" host bits and
add them to the network portion of the address, moving the network address line
to the right.

Let's say we've been allocated Class C `200.15.10.0/24`. To calculate the
number of available subnets, the formula is $2^{subnet-bits}$.






