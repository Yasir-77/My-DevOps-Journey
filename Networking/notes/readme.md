## Chapter 1: Introduction to Networking fundamentals

### Overview of computer networks

A computer network is a group of devices connected to each other allowing them to share information and resources.

Importance in modern infrastructure:

- Foundation - Enables communication between devices
- Resource sharing - Facilitates sharing of files, printers and more
- Internet functionality - Critical for browsing, streaming and communication 
- Application support - Backbone for app connectivity and data transfer

Netowking in Devops

- Server Interactions - Enables communication between servers and applications.
- Deployment - Critical for mlaunching and updating applications 
- Management - Crucial in monitoring and managing infrastructure
- Optimisation - Enhances troubleshooting, performance and scalability

### Network basics/Types of Networks

Two core types of networks

1 - LAN (Local area Network) small area, like home or office, connects devices to share resources e.g. Home Wi-Fi, printers any devices in single location 

2 - WAN (Wide Area Network) covers large areas, like a city, country or a larger regions,connects multiple LANs over long distances e.g. Internet

### Key Networking components

Switches - Connect devices within the same network, manage data flow within a LAN

Routers - Direct traffic between networks, connect different networks

Firewalls - Protect networls from unauthorised access, monitor and control incoming and outgoing network traffic

### IP address & MAC address

IP addressing refers to the system used to assign unique identifiers, known as IP addresses, to devices connected to a computer network, typically the Internet. An IP address acts like a mailing address for a device, allowing data to be routed between different devices over the network.

Two main types of IP adresses:

- IPv4 - Format: 32-bit address written in four groups of decimal numbers (each group representing 8 bits), separated by periods, like 192.168.0.5
- IPv6 - Format: 128-bit address written in eight groups of hexadecimal numbers (each group representing 16 bits), separated by colons, like 2001:0db8:85a3:0000:0000:8a2e:0370:7334

Ip addresses enable devices to identify and communicate with each other on a network, without them devices wouldnt know where to send or recieve data. 

MAC addresses 

A MAC (Media Access Control) address is a unique identifier assigned to a network interface controller (NIC) for use within a network. a MAC address is permanently assigned to the hardware by the manufacturer and is often referred to as a hardware address or physical address. MAC address help indetify eachother in a Local netowrk. They play an esential role for network communication and security.

A MAC address is a 48-bit address, usually represented as six pairs of hexadecimal digits separated by colons (:) or hyphens (-), like 00:1A:2B:3C:4D:5E.

### Ports and protocols

What are ports? A port is a logical endpoint for communication through which network connections are made. It helps differentiate between different types of traffic on a device. For example, while an IP address helps identify a device on a network, the port helps identify which service or application on that device should receive the data.

What are protocols? A protocol is a set of rules or standards that determine how data is transmitted across a network. Different protocols are used for different types of communication.

Importance of ports and protocols - Ports ensure data gets to the right application on your device while protocols ensure that the data is undertandable and properly formatted.

#### Two main types of Protocols:

1. TCP (Transmission control protocol) - TCP ensures that data sent from one device reaches another device accurately and in the correct order

Characterisitcs of TCP:

- It is connection oriented
- It requires a "handshake" where two devices agree to communicate, in networking this is a 3 step process.
- Reliable data transfer, TCP ensures that all data sent is recieved correctly on the other end, any data corruipted or incorrect TCP  will resend it.

Use cases of TCP:

- Ensures data is delivered in order
- Error checking and flow control
- Any bidirectional communication

2. UDP (User Datagram Protocol) - UDP is a simple protocol used to send and recieve data often reffered to as connectionless.

Characteristics of UDP:

- Simple protocol to send and recieve data
- Prior communication not required (Can be good and bad)
- connectionless - no form of connection established betwween sender and reciever.
- Fast but less reliable

Use cases of UDP:

- Suitable for real time applications e.g video streaming
- DNS
- VPN protocols

TCP VS UDP 

| FEATURE  | UDP  | TCP     |
|-------|------|----------|
| Connection  | Connectionless |Connection-oriented (uses a handshake)  |
| Reliability | Unreliable (no guarantees of delivery) | Reliable (ensures delivery and order) |
| Speed | Faster, no connection or handshake setup needed   | Slower due to overheaad of connection |
| Error Checking | No error checking or flow control   | Error checking and flow control |

## Chapter 2: OSI Model (open system interconnection model)

### Overview of OSI Model

Why do we need a communication model?

Application independence
- Without a standard model, applications must understand the underlying network.
- Imagine having different versions of your application/software for Wi-Fi, Ethernet, Fibre etc
- With a communicstion model applications can work independently of the network making development and coding much simpler and more efficient.

Simplified Network Equipment Managment
- Upgrading network mequipment is difficult without a standard model.
- Easier to upgrade and manage network gear because everything speaks the same language with the communication model
- Standardization makes maintenence and upgrading smoother and less prone to issues.

Decoupled innovation
-Innovations can happen in each layer independently, without affecting the entire system.

### 7 Layers of the OSI Model



















