---
title: IPv6 Protocol
date: 2024-11-22 10H:21:00 -0300
categories: [Distributed Systems, Networks]
tags: [distributed-systems, networks, IPv6]
author: 0
description:
image:
  path: https://upload.wikimedia.org/wikipedia/commons/thumb/1/15/Ipv6_address.svg/640px-Ipv6_address.svg.png
  alt: Picture
---

# IPv6 protocol
![IPv6 Example](https://upload.wikimedia.org/wikipedia/commons/thumb/1/15/Ipv6_address.svg/640px-Ipv6_address.svg.png)

IPv6 is a protocol that was born from detected base deficiencies in IPv4. IPv4 has a maximum of 4,294,967,296 addresses while IPv6 has a maximum of 7.8 * 10^28 (vm).
IPv6 addresses are assigned to interfaces, not nodes. An interface can have more than one IPv6 address, while a node can be responsible for more than one interface.
*Characteristics of IPv6 addresses*
* An IPv6 address is 128 bits long and consists of eight 16-bit fields.
* The parts of the fields are 3:
  1. Prefix
  2. Subnet ID
  3. Interface ID
* Most of the IPv6 addresses 'do not fill' the 128 bits and in the absence of information in the capmos they are 0's

**IPv6 protocol:**
* unicast: Identifies a single node interface.
* multicast: Identifies a group of Interfaces .
* anycast: Identifies interfaces that are members of anycast groups.
