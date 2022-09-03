### Classless Inter-Domain Routing (CIDR)

CIDR (Classless Inter-Domain Routing) -- also known as supernetting -- is a method of assigning Internet Protocol Addresses that improve the efficiency of address distribution and replaces the previous system based on Class A, Class B and Class C networks.    

CIDR is a way to combine several address ranges into a single network or route. . These addresses are given out by Internet Service Providers (ISPs) for use by their customers. CIDR addresses can reduce the size of your routing tables and make more IP addresses available within your business.

In the past, you were required to enter a subnet mask that was equal to or greater than the mask required for the network class. For class-C addresses, a subnet of 255.255.255.0 was the largest (253 host) that could be specified. To conserve IP addresses, when companies needed more than 253 hosts in a network, the Internet was issuing several class-C addresses. This would make the configuration of routes and other things difficult.

Now, CIDR allows these contiguous class-C addresses to be combined into a single network address range by using the subnet mask. For example, if you are giving out four class-C network addresses (208.222.148.0, 208.222.149.0, 208.222.150.0, and 208.222.151.0 with a subnet mask of 255.255.255.0), you can ask your ISP to make them a supernet by using the subnet mask 255.255.252.0. This mask combines the four networks into one for routing purposes. CIDR is beneficial because it reduces the number of assigned but unnecessary IP addresses.

#### CIDR Notation

The idea is that you can add a specification in the IP address itself as to the number of significant bits that make up the routing or networking portion.

For example, we could express the idea that the IP address 192.168.0.15 is associated with the netmask 255.255.255.0 by using the CIDR notation of 192.168.0.15/24. This means that the first 24 bits of the IP address given are considered significant for the network routing.

This allows us some interesting possibilities. We can use these to reference “supernets”. In this case, we mean a more inclusive address range that is not possible with a traditional subnet mask. For instance, in a class C network, like above, we could not combine the addresses from the networks 192.168.0.0 and 192.168.1.0 because the netmask for class C addresses is 255.255.255.0.

However, using CIDR notation, we can combine these blocks by referencing this chunk as 192.168.0.0/23. This specifies that there are 23 bits used for the network portion that we are referring to.

So, the first network (192.168.0.0) could be represented like this in binary:

1100 0000 - 1010 1000 - 0000 0000 - 0000 0000

While the second network (192.168.1.0) would be like this:

1100 0000 - 1010 1000 - 0000 0001 - 0000 0000

The CIDR address we specified indicates that the first 23 bits are used for the network block we are referencing. This is equivalent to a netmask of 255.255.254.0, or:

1111 1111 - 1111 1111 - 1111 1110 - 0000 0000

As shown, with this block the 24th bit can be either 0 or 1 and it will still match, because the network block only cares about the first 23 digits.

CIDR allows us more control over addressing continuous blocks of IP addresses. This is much more useful than the subnetting. 

CIDR is the reverse of  variable-length subnet masking VLSM. VLSM enables network engineers to divide an IP address space into a hierarchy of subnets of different sizes, making it possible to create subnetworks with different host counts without wasting large numbers of addresses.

CIDR addresses are made up of two sets of numbers: a prefix, which is the binary representation of the network address -- similar to what would be seen in a normal IP address -- and a suffix, which declares the total number of bits in the entire address. For example, CIDR notation may look like: 192.168.129.23/17 -- with 17 being the number of bits in the address. IPv4 addresses allow a maximum of 32 bits.

The same CIDR notation can be applied to IPv6 addresses. The only difference would be that IPv6 addresses can contain up to 128 bits.

#### CIDR blocks

CIDR blocks are groups of addresses that share the same prefix and contain the same number of bits. The combination of multiple connecting CIDR blocks into a larger whole, sharing a common network prefix, is what constitutes supernetting.

The size of CIDR blocks can be determined by the length of the prefix. A short prefix allows for more addresses -- and, therefore, forms a bigger block -- while a longer prefix indicates less addresses and a smaller block.

Blocks are initially handled by the Internet Assigned Numbers Authority IANA. IANA is responsible for distributing large blocks of IP addresses to Regional Internet Registries (RIRs). These blocks are used for large geographical areas, such as North America, Africa and Europe.

Once an RIR receives its block, it must create smaller blocks to assign to Local Internet Registries (LIRs). Blocks may continue to be divided further until they reach the end user. The size of the block assigned to an end user is dependent on the number of individual addresses that the user will require.

Most end users are assigned blocks by their  ISP; however, organizations that use multiple ISPs must receive provider-independent blocks directly from an RIR or LIR.

#### CIDR notation

IP sets aside some addresses for specific purposes. For example, several ranges -- such as Class B 192.168.0.0 -- are set aside as non-routable and are used to define a private network. Most home Broadband routers will assign addresses from the 192.168 network for systems inside the home. IP also doesn't allow host identifiers of all zeros and reserves the all-ones identifier to serve as a broadcast address -- packets sent to that address will go to all hosts on the network.

Originally, IP addresses were assigned in four major address classes: A through C. Each class allocated one portion of a 32-bit IP address to identify the gateway router for that network -- the first 8 bits for Class A, the first 16 for Class B, the first 24 for Class C. Bits not used for the network identifier were available for specifying host identifiers for systems on that network.

It helps to think of the binary representation of the network addresses. For IPv4, the 32-bit address is broken into four groups of 8 bits each -- called a dotted quad of numbers. A dotted quad would look like this in decimal form, 192.168.0.0, and like this in binary form, 11000000.10101000.00000000.00000000.

An IP address can be parsed into its network identifier and host identifier by applying a network mask to the address -- another dot address, with ones wherever a bit is used to indicate the network portion of the address. For example, a classic Class B would be written as 255.255.0.0.

If a network is further broken up into subnets, we speak of the subnet mask, which just adds bits to the network mask. If we break 192.168.0.0 into two subnets, the subnet mask gets one bit longer and could be indicated with 255.255.128.0.

CIDR notation compactly indicates the network mask for an address and adds the total number of bits in the entire address using slash notation. For example, 192.168.129.23/17 indicates a 17-bit network mask. Internet users can refer to a /17 network to indicate the network's size without specifying an actual network mask.

#### How CIDR works

Routers using CIDR use a destination address to route a packet toward a gateway, which can then take care of further unpacking the address based on its understanding of the details of the supernetwork -- also called the supernet. If a router knows routes for different parts of the same supernet, then it will use the most specific one -- or the one with the longest network address.

In IPv6, a CIDR block always gets 64 bits for specifying network addresses.

#### Advantages of CIDR

CIDR reduced the problem of wasted IPv4 address space without causing an explosion in the number of entries in a routing table. CIDR also lets one routing table entry for a supernet represent an aggregation of networks -- about which only a router closer to the destination actually needs to know the details.

CIDR is now the routing system on the internet's  backbone network, and every ISP uses it. It is supported by the Border Gateway Protocol BGP, the prevailing exterior (interdomain) gateway protocol and the Open Shortest Path First OSPF Gateway protocol.

Older gateway protocols, such as Exterior Gateway Protocol and Routing Information Protocol, do not support CIDR.

#### When to use supernetting

An organization or service provider managing addressing for a large number of hosts or networks should use supernetting -- possibly in combination with network address translation (NAT) -- to partition out addresses and optimize traffic efficiency.

For example, the supernetting process might want to break an internal network into subnets for administrative purposes so each office could manage its own address space. Or it might need to cobble together address space from multiple CIDR blocks of different sizes from its ISP.
