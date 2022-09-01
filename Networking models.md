
## Networking Models

The networking model describes the architecture, components, and design used to establish communication between the source and destination systems. Aliases for network models include protocol stacks, protocol suites, network stacks, and network protocols. There are 2twopredominant models available:

1.  Open Systems Interconnection (OSI) Model
    

2.  Transmission Control Protocol/Internet Protocol (TCP/IP) Model
    

### OSI Model

The Open Systems Interconnection (OSI) model describes seven layers that computer systems use to communicate over a network. It was the first standard model for network communications, adopted by all major computer and telecommunication companies in the early 1980s.

The modern Internet is not based on OSI, but on the simpler TCP/IP model. However, the OSI 7-layer model is still widely used, as it helps visualize and communicate how networks operate, and helps isolate and troubleshoot networking problems.

OSI was introduced in 1983 by representatives of the major computer and telecom companies and was adopted by ISO as an international standard in 1984.

### The OSI 7 Layers

The following is a “top down” description of the OSI layers; from the application layer that directly serves the end user, down to the physical layer.

- **Application Layer**: The application layer is used by end-user software such as web browsers and email clients. It provides protocols that allow software to send and receive information and present meaningful data to users. A few examples of application layer protocols are the Hypertext Transfer Protocol (HTTP), File Transfer Protocol (FTP), Post Office Protocol (POP), Simple Mail Transfer Protocol (SMTP), and Domain Name System (DNS).

- **Presentation Layer**: The presentation layer prepares data for the application layer. It defines how two devices should encode, encrypt, and compress data so it is received correctly on the other end. The presentation layer takes any data transmitted by the application layer and prepares it for transmission over the session layer.

- **Session Layer**: The session layer creates communication channels, called sessions, between devices. It is responsible for opening sessions, ensuring they remain open and functional while data is being transferred, and closing them when communication ends. The session layer can also set checkpoints during a data transfer—if the session is interrupted, devices can resume data transfer from the last checkpoint.

- **Transport Layer**: The transport layer takes data transferred in the session layer and breaks it into “segments” on the transmitting end. It is responsible for reassembling the segments on the receiving end, turning it back into data that can be used by the session layer. The transport layer carries out flow control: sending data at a rate that matches the connection speed of the receiving device, and error control: checking if data was received incorrectly and if not, requesting it again.

- **Network Layer**: The network layer has two main functions. One is breaking up segments into network packets and reassembling the packets on the receiving end. The other is routing packets by discovering the best path across a physical network. The network layer uses network addresses (typically Internet Protocol addresses) to route packets to a destination node.

- **Data Link Layer**: The data link layer establishes and terminates a connection between two physically connected nodes on a network. It breaks up packets into frames and sends them from source to destination. This layer is composed of two parts—Logical Link Control (LLC), which identifies network protocols, performs error- checking and synchronizes frames, and Media Access Control (MAC) which uses MAC addresses to connect devices and define permissions to transmit and receive data.

- **Physical Layer**: The physical layer is responsible for the physical cable or wireless connection between network nodes. It defines the connector, the electrical cable or wireless technology connecting the devices, and is responsible for transmission of the raw data, which is simply a series of 0s and 1s, while taking care of bit rate control.

### Advantages of OSI Model

The OSI model helps users and operators of computer networks:

-   Determine the required hardware and software to build their network.
    
-   Understand and communicate the process followed by components communicating across a network.
  
-   Perform troubleshooting, by identifying which network layer is causing an issue and focusing efforts on that layer.
    
The OSI model helps network device manufacturers and networking software vendors:

-   Create devices and software that can communicate with products from any other vendor, allowing open interoperability
    
-   Define which parts of the network their products should work with.
    
-   Communicate to users at which network layers their product operates – for example, only at the application layer, or across the stack.
    

## TCP/IP Model

The network of networks that we refer to as the Internet is based on the TCP/IP Model. Therefore, it is also referred to as the TCP/IP Protocol Suite. It is a four-layered architecture specifically built for the internet. The protocol is defined in the IETF (Internet Engineering Task Force) RFC (Request For Comments)  791 and 793. The TCP/IP Model features meet the following internet requirement:

-   Reliability
    
-   Security
    
-   Traffic Efficiency

To achieve the above, TCP/IP model uses TCP in the transport layer and IP in the network layer. 
The four layers of the network model are as follows:

-   **Application Layer**: In the TCP/IP Model, the Application layer encompasses the first three layers in the OSI model, that is, Application layer, Presentation layer, and the Session Layer.
    
-   **Transport Layer**: This layer is the same as the one mentioned in the OSI model. Transmission Control Protocol (TCP) is used in this model. TCP ensures reliability and helps avoid congestion in networks.
    
-   **Network Layer**: Internet Protocol (IP) is used predominantly in this layer. Until recently, IPv4 was the most common protocol in use. It provided 32 bits for assigning addresses. It supported around 4.29 million unique devices. In the late 1990s, the number of devices overtook the 4 million mark, and therefore IPv6 was introduced. IPv6 is the protocol that allows 4.3 billion devices. It has 128 bits assigned to the network address.
    
-   **Network Interface**: It enables the transmission of data. The layer corresponds to the data link layer and the physical layer in the OSI Model.

## OSI vs. TCP/IP Model
The Transfer Control Protocol/Internet Protocol (TCP/IP) is older than the OSI model and was created by the US Department of Defense (DoD). A key difference between the models is that TCP/IP is simpler, collapsing several OSI layers into one:

-   OSI layers 5, 6, 7 are combined into one Application Layer in TCP/IP

-   OSI layers 1, 2 are combined into one Network Access Layer in TCP/IP – however TCP/IP does not take responsibility for sequencing and acknowledgement functions, leaving these to the underlying transport layer.
 
Other important differences:

-   TCP/IP is a functional model designed to solve specific communication problems, and which is based on specific, standard protocols. OSI is a generic, protocol-independent model intended to describe all forms of network communication.
    
-   In TCP/IP, most applications use all the layers, while in OSI simple applications do not use all seven layers. Only layers 1, 2 and 3 are mandatory to enable any data communication.
