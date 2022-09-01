
# Introduction to networking
A network is a collection of network-enabled devices, typically made up of computers, switches, routers, printers, and servers. Networks are a fundamental part of day-to-day life and exist in homes, workplaces, and public areas. Networks allow all types of network-enabled devices to communicate.

## Network types
Networks vary in size, shape, and usage. To make it easier to identify different network types, they're categorized into one of the following network categories:
-   Personal area networks (PAN)
    
-   Local area networks (LAN)
    
-   Metropolitan area networks (MAN)
    
-   Wide area networks (WAN)

### Personal area network

A personal area network (PAN) provides networking needs around an individual. An example of a PAN is where a smartphone, smartwatch, tablet, and laptop all connect and share data without the need to connect to an access point or other third-party network services. PAN networks typically use Bluetooth to communicate because it provides a low-power, short-range data-sharing capability. The network standards associated with a PAN are Bluetooth and IEEE 802.15.

### Local area network

A local area network (LAN) provides networking needs around a single location. This location might be an organization's office, a school, a university, a hospital, an airport, and many others. A LAN is usually privately owned and needs authentication and authorization to access. Of the different classifications of a network, a LAN is by far the most commonly used.

### Wide area network
A wide area network (WAN) provides networking capabilities amongst different geographical locations locally or worldwide. For example, a WAN is used to connect an organization's head office with branch offices all over the country. A WAN links multiple LANs together to create one super network. As a WAN, you use a virtual private network (VPN) to manage the connection between different LANs.

## Differences between LAN and WAN networks

Several aspects set a LAN apart from a WAN. Knowing what these items are makes it easier to plan the services to deploy across these networks.
|LAN| WAN |
|--|--|
|A LAN is a privately operated network typically contained in a single building.  | A WAN is used to connect geographically separate offices to each other. Multiple organizations might operate WANs. |
| A LAN operates at speeds of 10 Gbps or higher. | A WAN typically operates at speeds of less than 1 Gbps. |
| A LAN is less congested compared to other network types. | A WAN is more congested compared to other network types. |
|  A LAN can be managed and administrated in-house.| A WAN typically requires the use of a third party to configure and set up, which increases cost. |

## Network topologies

A network topology describes the physical composition of a network. They include:

-   Bus
    
-   Ring
    
-   Mesh
  
-   Star
- 
### Bus topology
n a bus topology, each network device is connected to a single network cable. Even though it's the simplest type of network to implement, there are limitations to it. The first limitation is the length of the main cable or bus. The longer it gets, the higher the chance of signal dropout. This limitation constrains the physical layout of the network. All devices have to be physically located near each other, for example, in the same room. Finally, if there's a break in the bus cable, the whole network fails.

### Ring topology
In a ring topology, each network device is connected to its neighbor to form a ring. This form of network is more resilient than the bus topology. A break in the cable ring also affects the performance of the network.

### Mesh topology
The mesh topology is described as either a physical mesh or a logical mesh.

In a physical mesh, each network device connects to every other network device in the network. It dramatically increases the resilience of a network but has the physical overhead of connecting all devices. Few networks today are built as a full mesh. Most networks use a partial mesh, where some machines interconnect, but others connect through one device.

There's a subtle difference between a physical mesh network and a logical one. The perception is that most modern networks are mesh based, since each device can see and communicate with any other device on the network. This description is of a logical mesh network and is primarily made possible through the use of network protocols.

### Star/Hub and Spoke  topology
The star/Hub and Spoke topology is the most commonly used network topology. Each network device connects to a centralized hub or switch. Switches and hubs can be linked together to extend and build more extensive networks. This type of typology is, by far, the most robust and scalable.

## Network Standards

### Ethernet

Ethernet is a networking standard that's synonymous with wire-based LAN networks and also used in MAN and WAN networks. Ethernet has replaced other wired LAN technologies like ARCNET and Token Ring and is an industry standard.

While Ethernet is associated with wired networks, keep in mind that it's not limited to wire, since it's used over fiber-optic links as well.

The Ethernet standard defines a framework for data transmission, error handling, and performance thresholds. It describes the rules for configuring an Ethernet network and how each element in the network interacts with each other.

Ethernet is used in the OSI model at the data link and physical layers. It formed the basis for the IEEE 802.3 Standard. This standard helped to unify network and hardware development.

Ethernet is a continually evolving standard, and the original version supported a data transmission rate of only 2.94 Mbps. In recent years, several iterations were released to keep up with the demands for increased speed. Today, rates extend up to 400 Gbps.

### Fast Ethernet

Fast Ethernet (IEEE 802.3u) was developed to support data transmission speeds of up to 100 Mbps. Faster Ethernet is also referred to as the 100BASE-TX standard.

### Gigabit Ethernet

Gigabit Ethernet (IEEE 802.3ab) was developed to support faster communication networks that can support services like streaming multimedia and Voice over IP (VoIP). The 1000BASE-T standard runs 10 times faster than the 100BASE-TX standard. Gigabit Ethernet is now included in the 802.3 standards and recommended for enterprise networks. The new standard is backward compatible with the 100BASE-T and the older 10BASE-T standards.

### 10 Gigabit Ethernet

The 10 Gigabit Ethernet (IEEE 802.3ae) standard has a nominal data transfer speed of 10 Gbps, which is 10 times faster than its predecessor. This speed improvement is made possible only by using fiber optics. The standard now requires that 10 Gigabit Ethernet networks use area-based routing rather than broadcasting data to all nodes. In that way, network noise and traffic are reduced.

### Terabit Ethernet

Terabit Ethernet offers data transfer speeds of 200 Gbps and 400 Gbps. It's expected that Terabit Ethernet will offer speeds of 800 Gbps and 1.6 Tbps in the future.


## Cloud networking

Cloud networking is a type of IT infrastructure in which some or all of an organization’s network capabilities and resources are hosted in a public or private cloud platform, managed in-house or by a service provider, and available on demand.

Companies can either use on-premises cloud networking resources to build a private cloud network or use cloud-based networking resources in the public cloud or hybrid cloud (combination of both). These network resources can include virtual routers, firewalls, and bandwidth and network management software, with other tools and functions available as required.

### Why cloud networking?

Businesses today turn to the cloud to drive agility, deliver differentiation, accelerate time-to-market, and increase scale. The cloud model has become the standard approach to build and deliver applications for the modern enterprise.

Cloud networking has also played a critical role in the way organizations address their growing infrastructure needs, regional expansions, and redundancy plans. Many organizations are adopting multi-data center strategy and leveraging multiple clouds from multiple cloud service providers (CSPs).

### Benefits of cloud networking

Most organizations have become a patchwork of on-premises technologies, public cloud services, legacy applications and systems, and emerging technologies — a complex situation that contributes to a weak security posture and results in inadequate governance, visibility, and manageability across fragmented networks.

A virtual cloud network is an architectural approach  built in software at global scale from edge-to-edge, that’s able to deliver consistent, pervasive connectivity and security for apps and data wherever they reside, independent of underlying physical infrastructure. Whether your workloads are on premises or in the cloud, the same network and security stack can be used to provide connectivity, security, and visibility. It is also the kind of next-generation networking service consumption technology that organizations are increasingly adopting to provide the digital fabric that helps unify a hyper-distributed world.
