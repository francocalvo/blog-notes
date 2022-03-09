# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Classless Inter-Domain Routing (CIDR)](#Classless Inter-Domain Routing (CIDR))
- [Subnetting](#Subnetting)
    - [Command: `ip subnet-zero`](#Subnetting#Command: `ip subnet-zero`)
    - [Class C/31 subnet](#Subnetting#Class C/31 subnet)
    - [Class C/30 subnet](#Subnetting#Class C/30 subnet)
    - [Class C/29 subnet](#Subnetting#Class C/29 subnet)
  - [Subnetting practice](#Subnetting#Subnetting practice)
- [Variable length subnet mask or VLSM](#Variable length subnet mask or VLSM)
  - [VLSM Class C Example](#Variable length subnet mask or VLSM#VLSM Class C Example)
  - [VLSM Class B](#Variable length subnet mask or VLSM#VLSM Class B)
    - [Example 1](#Variable length subnet mask or VLSM#VLSM Class B#Example 1)
    - [Example 2](#Variable length subnet mask or VLSM#VLSM Class B#Example 2)
  - [VLSM Class A](#Variable length subnet mask or VLSM#VLSM Class A)
    - [Example 1](#Variable length subnet mask or VLSM#VLSM Class A#Example 1)
    - [Example 2](#Variable length subnet mask or VLSM#VLSM Class A#Example 2)
    - [Example 3](#Variable length subnet mask or VLSM#VLSM Class A#Example 3)
  - [Subnetting question categories](#Variable length subnet mask or VLSM#Subnetting question categories)

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


# Subnetting

Let's say that you work for a company with 4 departments in two different
offices. You could buy four different Class C IP ranges, or buy a single one
and subnet it.

To subnet the network into smaller subnets, we need to "borrow" host bits and
add them to the network portion of the address, moving the network address line
to the right.

Let's say we've been allocated Class C `200.15.10.0/24`. To calculate the
number of available subnets, the formula is $2^{subnet-bits}$. On the other
hand, to get the number of available hosts we need to make $2^{host-bits}-2$.
We subtract 2 because the network address and broadcast address cannot be
assigned to hosts.

### Command: `ip subnet-zero`

As we subtract 2 bits from the host address, we used to subtract two from the
network address. This wasn't really practical and is not done anymore. In CISCO
routers, the command `ip subnet-zero` overrides this behavior and is enabled by
default.

### Class C/31 subnet

Following the same example, we'll use a submask of `/31`, which is the max you
can use. This borrows 7 bits out of 8, and gives us 128 subnets with 2 hosts
each. This breaks the breaks the standard rules for IP addressing, but it's
supported for point to point link, which don't need a broadcast address. 

### Class C/30 subnet

We now use a `/30`  subnet mask, or `255.255.255.252`. This let's us have 2
bits per ahost address, meaning: $2^2-2=2$. It borrows 6 bits for the network
address, meaning we got $2^6=64$.

We see that the `/31` is useful if you need to maximise use of your address
space, but `/30` is more standard and used.

### Class C/29 subnet

With this setup we get $2^3-2=6$ for the hosts, and $2^5=32$ for the network
address. This means that valid host addresses are going to be:

- `200.15.10.1` to `200.15.10.6`  (0 for network and 7 for broadcast). 
- `200.15.10.9` to `200.15.10.14`  (8 for network and 15 for broadcast). 

## Subnetting practice

1. What are the network address, broadcast address, and valid host addresses
   for the IP address `192.22.45.173/26`?
2. What's the subnet mask in the dotted decimal notation?

The number of host bits is six, so we got $2^6 -2=62$ host addresses. Going
from 0, we got:
- `.1` to `.62`  (`.0` network and `.63` broadcast).
- `.65` to `.126`  (`.64` network and `.127` broadcast).
- `.129` to `.190`  (`.128` network and `.191` broadcast).

The subnet mask borrowed the last two bits in the last octet, so we got:
$128+64=192$. Then, the submask is `255.255.255.192`.

---

# Variable length subnet mask or VLSM

Early routing protocols only supported fixed length subnet masking, where all
subnets had to be the same size. Now, you can have subnets of different sizes
according to how many hosts you have.

**Subnetting considerations:** 
- How many locations do we have in the network?
- How many hosts are in each location?
- What are the IP addressing requirements for each location?
- What size is appropriate for each subnet?

For designing the subnettings, you first find the largest segment and allocate
a suitable subnet size for it and the start of the address space, then rinse
and repeat.

## VLSM Class C Example

> Let's say we got an office in New York with two departments: Engineering, with
> 28 hosts, and Sales with 14. Then we got Boston with other two departments:
> Engineering with 28 hosts, and Sales with 7.
> Design the subnets for this setting.

For the Eng. Dept. we can calculate that the submask is going to be: 

$$
x = \frac{log(30)}{log(2)} \approx 5
$$

Where $x$ is the bit size of the host address. This means we can have a submask
of `/27` or `255.255.255.224`. It'll leave us with:

$$
\text{hosts }= 2^5 - 2 = 30
$$

We'll get these subnets for both Eng Depts:

- `.1` to `.30` (`.0` and `.31` reserved) for NY Eng Dept.
- `.33` to `.62` (`.32` and `.63` reserved) for Boston Eng Dept.

The next largest subnet is NY sales with 14. It'll require the following bit
size for the host address:

$$
x = \frac{log(16)}{log(2)} = 4
$$

With this, we know the subnet mask is `/28` or `255.255.255.240`, which means
16 addresses. We'll have:
- `.65` to `.78`  (`.64` and `.79` reserved) for the NY Sales Dept.

For departments, we still need a subnet for the Boston Sales Dept. We got:

$$
x = \frac{log(9)}{log(2)} \approx 4
$$

With this, we know the subnet mask is `/28` or `255.255.255.240`, which means
16 addresses. We'll have:
- `.81` to `.94`  (`.80` and `.95` reserved) for the Boston Sales Dept.

Lastly, we need a link between both New York and Boston. As we saw, we can do it
with a `/30` or `255.255.255.252` subnet mask. We'll have it as:

- `.97` to `99` (`.96` and `.100` reserved) for the link between offices.

## VLSM Class B

### Example 1
If we subnet an Class B on the 4 Octet into `/29`, we got 3 bits for host
addressing. This yields 6 hosts per network, but as we have a Class B `/16`
address range, we have 13 bits for the network address, meaning we can have
8192 subnets. 

> For the IP address `135.15.10.138/29`, which would be the network address,
> broadcast address and range of valid IP addresses?

For this, we know addresses go from 8 to 8, so one will begin in 0, 8, 16, etc.
We can see that the IP address for that range is going to be starting from
`135.15.10.136`, so we can get:

- Network address: `135.15.10.136`.
- Broadcast address: `135.15.10.143`.
- Valid IP addresses: `135.15.10.137-142`.

### Example 2

> You've been asked to subnet the 134.65.0.0 network into six different
> networks. Which subnet mask do you use?

We see that we need at least 3 bits, so knowing a Class B has as default `/16`, 
I'd use `/19`.

---

## VLSM Class A

### Example 1
> If we have a Class A 60.0.0.0/8, and apply the subnet mask 255.255.255.240,
> how many subnets we have an how many hosts per subnet?

We can see that $128+64+32+16=240$, so we know that the network bit is 4 and
the host bit 4 for the last octet. It means we have $2^{28-8}=1048576$ subnets
with $2^4-2=14$ hosts each.

### Example 2
> For the IP address `60.15.10.75/28`, what's the network, broadcast and host
> addresses?

We can see that we got 4 bits for the hosts. This means we get $2^4=16$ block
of addresses. We can see that we'll have the block starting at 64. Then:
 
- Network address: `60.15.10.64`.
- Broadcast address: `60.15.10.79`.
- Valid IP addresses:`60.15.10.65-78`.

### Example 3

We're allocated Class A 60.0.0.0/8. 

> If we subnet this into `/19`  networks, how many subnets do we have, and how
> many hosts per subnet?

We know we got 13 bits for the host address, and we borrow 11 bits for the
network address. We can get:
 
- Subnets: $2^11=2048$.
- Hosts per subnet: $2^13-2 = 8190$.

> For the IP address `60.15.10.75/19`, what are the important addresses?

We are working on the third octet. From this, we can see we'll subtract the
bits from the first octet: $19-8=11$. From this, we know that from the 16 bits,
11 will be from the network bits. The last 8 will be from the second octet, so
we can see that we got 3 bits from the network in the third octet. The rest are
going to be bits for the host addresses. This means we get $2^5=32$ host
addresses per network. Then:

- Network address: `60.15.0.0`.
- Broadcast address: `60.15.31.255`.
- Host addresses: `60.15.1-31.0-255`

## Subnetting question categories

- Given a network requirement of "x" amount of subnets and "y" amount of hosts
  per subnet, what network address and subnet mask should be used for each
  subnet?
- Given a particular IP address and subnet mask, calculate the subnet's network
  address, the broadcast address and range of valid host IP addresses.
