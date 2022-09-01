## TCP/IP Addressing and Subnetting

In order to communicate, every device in a network needs to be uniquely identified, hence the introduction of Internet Protocol (IP) addresses by the Internet Engineering Task Force (IETF).

Two versions of the Internet Protocol (IP) addresses are in use: IP Version 4 (IPv4) and IP Version 6(IPv6).

An IPv4 address is a 32-bit number arranged in groups of 8 bit which is usually expressed in dotted-decimal format, with four numbers separated by periods, such as 192.168.56.105.

An IPv6 address is 128 bits long, arranged in eight groups, each of which is 16 bits. The 16 bits group is further divided into subgroups of 4 bits and expressed as four hexadecimal digits separated by colons such as FE80:CD00:0000:0CDE:1257:0000:211E:729C

### IPv6
The Internet Protocol version 6 (IPv6) is more advanced and has better features compared to IPv4. It has the capability to provide an infinite number of addresses. It is replacing IPv4 to accommodate the growing number of networks worldwide and help solve the IPv4 address exhaustion problem.

#### Benefits of IPv6

- More efficient routing with smaller routing tables and aggregation of prefixes.
- Simplified packet processing due to more streamlined packet headers.
- Support of multicast packet flows.
- Hosts can generate their own IP addresses.
- Eliminates the need for network address translation (NAT).
-Easier to implement services like peer-to-peer (P2P) networks, voice over IP (VoIP) and stronger security.

#### Types of IPv6

**Global unicast**: These addresses are routable on the internet and start with "2001:" as the prefix group. Global unicast addresses are the equivalent of IPv4 public addresses.

**Unicast address**: Used to identify the interface of an individual node. A node is a system with an IPv6 address and interface that is configured for IPv6 support.

**Anycast address**: Used to identify a group of interfaces on different nodes.

**Multicast address**: An address used to define multicast Multicasts are used to send a single packet to multiple destinations at one time.

**Link local addresses**: One of the two internal address types that are not routed on the internet. Link local addresses are used inside an internal network, are self-assigned and start with "fe80:" as the prefix group.

**Unique local addresses**: This is the other type of internal address that is not routed on the internet. Unique local addresses are equivalent to the IPv4 addresses 10.0.0.0/8, 172.16.0.0/12 and 192.168.0.0/16.

### IPv4
#### Classful and Classless Addressing
In IPv4, there’re two kinds of addressing: classful and classless.
Classful IP addressing is divided further into 5 classes: A, B, C, D, and E where address range has a default subnet mask as shown in the table below:
Classless IP addressing, however, decouples IP address ranges from a default subnet mask, allowing for variable-length subnet masking (VLSM).
Classless IP addressing help to address the limitations of classful IP addressing by providing more IP address allocations, more balanced use of IP address ranges, and more efficient routing.
Classless Inter-Domain Routing (CIDR) is another name for classless addressing.

 #### Public and Private IP Addresses

According to the Internet Engineering Task Force (IETF), IPv4 ranges is divided into two: private and public.
Private IP addresses are non-routable addresses which means the scope is internal and communication is within the network. This makes it reusable within various internal networks of organizations and it is free.
Public IP addresses are routable addresses which means the scope is global and it is used to communicate outside the network (the internet). Every public IP address is unique and cannot be used by others so no two devices on the internet can have the same public IP address. It is usually not free of cost.
However, for a private IP address to communicate with the internet, it has to be translated to a public IP address by a Network Address Translation (NAT) gateway.
When creating virtual networks, it is recommended by the internet Assigned Numbers Authority (IANA) to use the address ranges enumerated in RFC 1918, for private, non-routable address spaces:

10.0.0.0 - 10.255.255.255 (10/8 prefix)

172.16.0.0 - 172.31.255.255 (172.16/12 prefix)

192.168.0.0 - 192.168.255.255 (192.168/16 prefix)

The following address ranges are reserved for specific purposes:

224.0.0.0/4 (Multicast)

255.255.255.255/32 (Broadcast)

127.0.0.0/8 (Loopback)

169.254.0.0/16 (Link-local)

168.63.129.16/32 (Internal DNS)

#### IP addresses: Networks and hosts

To understand how subnet masks are used to distinguish between hosts, networks, and subnetworks, it is necessary examine an IP address in binary notation.

For example, the dotted-decimal IP address 192.168.123.132 is (in binary notation) the 32-bit number 110000000101000111101110000100. This number may be hard to make sense of, so divide it into four parts of eight binary digits.

These 8-bit sections are known as octets. The example IP address, then, becomes 11000000.10101000.01111011.10000100. This number only makes a little more sense, so for most uses, convert the binary address into dotted-decimal format (192.168.123.132). The decimal numbers separated by periods are the octets converted from binary to decimal notation.

For a TCP/IP wide area network (WAN) to work efficiently as a collection of networks, the routers that pass packets of data between networks don't know the exact location of a host for which a packet of information is destined. Routers only know what network the host is a member of and use information stored in their route table to determine how to get the packet to the destination host's network. After the packet is delivered to the destination's network, the packet is delivered to the appropriate host.

For this process to work, an IP address has two parts. The first part of an IP address is used as a network address, the last part as a host address. If you take the example 192.168.123.132 and divide it into these two parts, you get 192.168.123. Network .132 Host or 192.168.123.0 - network address. 0.0.0.132 - host address.

#### Subnet mask

The second item, which is required for TCP/IP to work, is the subnet mask. The subnet mask is used by the TCP/IP protocol to determine whether a host is on the local subnet or on a remote network.

In TCP/IP, the parts of the IP address that are used as the network and host addresses aren't fixed. Unless you have more information, the network and host addresses above can't be determined. This information is supplied in another 32-bit number called a subnet mask. The subnet mask is 255.255.255.0 in this example. It isn't obvious what this number means unless you know 255 in binary notation equals 11111111. So, the subnet mask is 11111111.11111111.11111111.00000000.

Lining up the IP address and the subnet mask together, the network, and host portions of the address can be separated:

11000000.10101000.01111011.10000100 - IP address (192.168.123.132)  
11111111.11111111.11111111.00000000 - Subnet mask (255.255.255.0)

The first 24 bits (the number of ones in the subnet mask) are identified as the network address. The last 8 bits (the number of remaining zeros in the subnet mask) are identified as the host address. It gives you the following addresses:

11000000.10101000.01111011.00000000 - Network address (192.168.123.0)  
00000000.00000000.00000000.10000100 - Host address (000.000.000.132)

So now you know, for this example using a 255.255.255.0 subnet mask, that the network ID is 192.168.123.0, and the host address is 0.0.0.132. When a packet arrives on the 192.168.123.0 subnet (from the local subnet or a remote network), and it has a destination address of 192.168.123.132, your computer will receive it from the network and process it.

Almost all decimal subnet masks convert to binary numbers that are all ones on the left and all zeros on the right. Some other common subnet masks are:

Decimal

Binary

255.255.255.192

1111111.11111111.1111111.11000000

255.255.255.224

1111111.11111111.1111111.11100000

Internet RFC 1878,  describes the valid subnets and subnet masks that can be used on TCP/IP networks.

#### Network classes
Internet addresses are allocated by the Internet Assigned Numbers Authority (IANA), the organization responsible for assignment to local Internet registries, such as Internet service providers (ISPs), and other end users. These IP addresses are divided into classes. The most common of them are classes A, B, and C. Classes D and E exist, but aren't used by end users. Each of the address classes has a different default subnet mask. You can identify the class of an IP address by looking at its first octet. The following are the ranges of Class A, B, and C Internet addresses, each with an example address:

-   Class A networks use a default subnet mask of 255.0.0.0 and have 0-127 as their first octet. The address 10.52.36.11 is a class A address. Its first octet is 10, which is between 1 and 126, inclusive.
-   Class B networks use a default subnet mask of 255.255.0.0 and have 128-191 as their first octet. The address 172.16.52.63 is a class B address. Its first octet is 172, which is between 128 and 191, inclusive.
-   Class C networks use a default subnet mask of 255.255.255.0 and have 192-223 as their first octet. The address 192.168.123.132 is a class C address. Its first octet is 192, which is between 192 and 223, inclusive.
    
In some scenarios, the default subnet mask values don't fit the organization needs for one of the following reasons:
-   The physical topology of the network
-   The numbers of networks (or hosts) don't fit within the default subnet mask restrictions.
This gives rise to the need for subnetting.
    

### Subnetting

A Class A, B, or C TCP/IP network can be further divided, or subnetted, by a system administrator. It becomes necessary as you reconcile the logical address scheme of the Internet (the abstract world of IP addresses and subnets) with the physical networks in use by the real world.

A system administrator who is allocated a block of IP addresses may be administering networks that aren't organized in a way that easily fits these addresses. For example, you have a wide area network with 150 hosts on three networks (in different cities) that are connected by a TCP/IP router. Each of these three networks has 50 hosts. You are allocated the class C network 192.168.123.0. (For illustration, this address is actually from a range that isn't allocated on the Internet.) It means that you can use the addresses 192.168.123.1 to 192.168.123.254 for your 150 hosts.

Two addresses that can't be used in your example are 192.168.123.0 and 192.168.123.255 because binary addresses with a host portion of all ones and all zeros are invalid. The zero address is invalid because it's used to specify a network without specifying a host. The 255 addresses (in binary notation, a host address of all ones) is used to broadcast a message to every host on a network. Just remember that the first and last address in any network or subnet can't be assigned to any individual host.

You should now be able to give IP addresses to 254 hosts. It works fine if all 150 computers are on a single network. However, your 150 computers are on three separate physical networks. Instead of requesting more address blocks for each network, you divide your network into subnets that enable you to use one block of addresses on multiple physical networks.

In this case, you divide your network into four subnets by using a subnet mask that makes the network address larger and the possible range of host addresses smaller. In other words, you are 'borrowing' some of the bits used for the host address, and using them for the network portion of the address. The subnet mask 255.255.255.192 gives you four networks of 62 hosts each. It works because in binary notation, 255.255.255.192 is the same as 1111111.11111111.1111111.11000000. The first two digits of the last octet become network addresses, so you get the additional networks 00000000 (0), 01000000 (64), 10000000 (128) and 11000000 (192). (Some administrators will only use two of the subnetworks using 255.255.255.192 as a subnet mask. For more information on this topic, see RFC 1878.) In these four networks, the last six binary digits can be used for host addresses.

Using a subnet mask of 255.255.255.192, your 192.168.123.0 network then becomes the four networks 192.168.123.0, 192.168.123.64, 192.168.123.128 and 192.168.123.192. These four networks would have valid host addresses:

192.168.123.1-62 192.168.123.65-126 192.168.123.129-190 192.168.123.193-254

Remember, again, that binary host addresses with all ones or all zeros are invalid, so you can't use addresses with the last octet of 0, 63, 64, 127, 128, 191, 192, or 255.

You can see how it works by looking at two host addresses, 192.168.123.71 and 192.168.123.133. If you used the default Class C subnet mask of 255.255.255.0, both addresses are on the 192.168.123.0 network. However, if you use the subnet mask of 255.255.255.192, they are on different networks; 192.168.123.71 is on the 192.168.123.64 network, 192.168.123.133 is on the 192.168.123.128 network.

#### Default gateways

If a TCP/IP computer needs to communicate with a host on another network, it will usually communicate through a device called a router. In TCP/IP terms, a router that is specified on a host, which links the host's subnet to other networks, is called a default gateway. This section explains how TCP/IP determines whether or not to send packets to its default gateway to reach another computer or device on the network.

When a host attempts to communicate with another device using TCP/IP, it performs a comparison process using the defined subnet mask and the destination IP address versus the subnet mask and its own IP address. The result of this comparison tells the computer whether the destination is a local host or a remote host.

If the result of this process determines the destination to be a local host, then the computer will send the packet on the local subnet. If the result of the comparison determines the destination to be a remote host, then the computer will forward the packet to the default gateway defined in its TCP/IP properties. It's then the responsibility of the router to forward the packet to the correct subnet.

#### Troubleshooting

TCP/IP network problems are often caused by incorrect configuration of the three main entries in a computer's TCP/IP properties. By understanding how errors in TCP/IP configuration affect network operations, you can solve many common TCP/IP problems.

**Incorrect Subnet Mask**: If a network uses a subnet mask other than the default mask for its address class, and a client is still configured with the default subnet mask for the address class, communication will fail to some nearby networks but not to distant ones. As an example, if you create four subnets (such as in the subnetting example) but use the incorrect subnet mask of 255.255.255.0 in your TCP/IP configuration, hosts won't be able to determine that some computers are on different subnets than their own. In this situation, packets destined for hosts on different physical networks that are part of the same Class C address won't be sent to a default gateway for delivery. A common symptom of this issue is when a computer can communicate with hosts that are on its local network and can talk to all remote networks except those networks that are nearby and have the same class A, B, or C address. To fix this problem, just enter the correct subnet mask in the TCP/IP configuration for that host.

**Incorrect IP Address**: If you put computers with IP addresses that should be on separate subnets on a local network with each other, they won't be able to communicate. They'll try to send packets to each other through a router that can't forward them correctly. A symptom of this problem is a computer that can talk to hosts on remote networks, but can't communicate with some or all computers on their local network. To correct this problem, make sure all computers on the same physical network have IP addresses on the same IP subnet. 

**Incorrect Default Gateway**: A computer configured with an incorrect default gateway can communicate with hosts on its own network segment. But it will fail to communicate with hosts on some or all remote networks. A host can communicate with some remote networks but not others if the following conditions are true:
-   A single physical network has more than one router.
-   The wrong router is configured as a default gateway.
 
This problem is common if an organization has a router to an internal TCP/IP network and another router connected to the Internet.
