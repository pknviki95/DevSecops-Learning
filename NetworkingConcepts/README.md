# Computer Networks Concepts:


Reference link : [Networking](https://www.cloudflare.com/en-gb/learning/)

## Concepts:

- Networking
- Client
- Server
- Client-server architecture
- Protocols
- Packets
- IP-Address
- IP-Address format
- Types of IP-Address    
- Port Number
- Types of Network
- Networking devices
- Network Topologies

## Abbrevations:

| Abbrevations | Description   |
| :---:   | :---: |
| ISP | Internet service provider |
| IP | Internet protocol |
| NAT | Network address translator |
| DHCP|  Dynamic Host Configuration Protocol|

## Networking:

- Networking is the act of making communication and data exchange between different communities and organizations

## Client:

- A client is a program that makes requests to a server

## Server:

- A server is a program that fulfills those requests

## client-server Architecture:

![alt text](https://github.com/pknviki95/DevSecops-Learning/blob/main/NetworkingConcepts/Images/client-server.png)


### Workflow of Client-server Architecture:

- The user devices can be a computer or a mobile device with an application installed. 
- The user also calls the Client sends a request to the host server anticipating a response and is disconnected from the network after completing the request. 
- The Client's bandwidth ability will determine the speed of delivery.

**for example:**

- when you type www.google.com into your web browser, **your browser is acting as a client**. 
- It makes a **request** to Google’s servers for the website you’ve requested. 
- Google’s servers then fulfill that request by **sending back response** the HTML code for the Google home page. 
- Your browser then renders that HTML code into the familiar page of text, images, and links we all know so well.

**(i.e) client sends request to server and server sends reponse to respective request back to client**

## Protocols:

- A protocol is a **set of rules and guidelines for communicating data**. 
- Rules are defined for each step and process during communication between two or more computers. 
- Networks have to follow these rules to successfully transmit data.
- It is determined/Developed by Internet community
- TCP,UDP,HTTP,HTTPS,FTP are some of protocols

### How Data is Transferred?

- The data that is communicated between client and server is through something called **Packets**.

## Packets:

- A packet is a **small segment of a larger message**. 
- Data sent over computer networks*, such as the Internet, is divided into packets. 
- These packets are then recombined by the computer or device that receives them.

## IP-address:

- ‘IP’ stands for Internet Protocol, which is the set of rules that makes it possible for devices to communicate over the **Internet**. 
- With billions of people accessing the Internet every day, unique identifiers are necessary to keep track of who is doing what. 
- The Internet Protocol solves this by **assigning IP numbers to every device accessing the Internet**.
- The IP address has format **x.x.x.x** ;every place holds number from **0-255** (i.e) 192.168.2.2
(eg): google.com ip address - **8.8.8.8 and 8.8.4.4**

**(i.e) IP- Address is similar to people living address Internet Protocol assigns IP numbers for all the individual device you use for accessing the internet**

![alt text](https://github.com/pknviki95/DevSecops-Learning/blob/main/NetworkingConcepts/Images/IP-adresses-infographic.png)


## IP-Address format:
 
Based on format of IP address it differs in two types

- **IPV4**
- **IPv6**

| IPV4 | IPV6   |
| :---:   | :---: |
| IPv4 was implemented in 1983 and is still in use today.  |  It was introduced as IPV4 cannot fulfill as increase in current internet users   |
| :---:   | :---: |
| The format for IPv4 addresses is four sets of numeric dot-decimal separated by dots     | IPv6 addresses use a more complex format that utilizes sets of alphanumbers and letters separated by single or double colons  |
| :---:   | :---: | 
|  for example: ‘192.0.2.1’. This is a **32-bit format**, which means that it allows for 232, or about 4.3 billion  |   for example: ‘2001:0db8:85a3:0000:0000:8a2e:0370:7334’. This **128-bit format** can support 2128 unique addresses. (That computes to a 39-digit number!)               | 

## Various Types of IP-Address:

- **Public**
- **Private**
- **Static**
- **Dynamic**

 ![alt text](https://github.com/pknviki95/DevSecops-Learning/blob/main/NetworkingConcepts/Images/Private-and-Public-IP-Address.jpg)

### Public IP-Addresses:

- A public IP address is a **unique identifier assigned to a device directly connected to the internet, such as a computer or a router**. It is used to identify the device on the internet and allows it to communicate with other devices.
- Public IP addresses are assigned by **internet service providers (ISPs)** and are unique, meaning that no two devices on the internet can simultaneously have the same public IP address.
- Some examples of public IP address use include hosting a website or online game server, remote access to a computer or network, and virtual private network (VPN) connections.

### Private IP-Addresses:

- A private IP address is a **unique identifier assigned to a device connected to a local network**, such as an office network or home. We use Private IP addresses to identify devices within the network that are not accessible from the internet.
- **Dynamic Host Configuration Protocol (DHCP)** is used to dynamically assign Internet Protocol (IP) addresses to each host on your organization's network
-Private IP addresses are typically assigned by a **router or a network address translator (NAT)** and are used to allow devices within the network to communicate with each other
- Unlike public IP addresses, which are unique across the internet, **we can reuse private IP addresses within different local networks**

### Static IP-Adddress:

- A static public IP address is a **permanent address that does not change over time**

### Dynamic IP-Address:

- Dynamic public IP address is **assigned temporarily and can change periodically**.

### Ports:

- A port is a virtual point where **network connections start and end**. 
- Ports are **software-based and managed by a computer's operating system**. 
- Each port is associated with a **specific process or service**. 
- Ports allow computers to easily **differentiate between different kinds of traffic**

## Port number:

- Port Number are **standardized across all network-connected devices, with each port assigned a number**. 
- Most port numbers are **reserved for certain protocols** — for example, all Hypertext Transfer Protocol (HTTP) messages go to port 80. 
- While **IP addresses enable messages to go to and from specific devices**, **port numbers allow targeting of specific services or applications within those devices**.
- Port Numbers are **16-bit** numbers around **65000** port number are available
- **Hypertext Transfer Protocol (HTTP)** assigned to port **80**.

**for example**:

- **When a request is sent from the client the server sends back response to the client**
- **DHCP determines which device requested based on the IP address assigned through router or NAT to send back the response**
- **But to determine which application/services has requested for that IP address assigned device will be determined by the Port number**
- **(i.e) 192.168.1.1:8080 - The response is sent back to device with IP address 192.168.1.1 where the application/service running on port 8080 of that device** 

### Reserved ports:

- Reserved ports are the ports that are **reserved/pre-defined for set of protocols**.
- **0 to 1023** are reserved ports.
- Reserved ports cannot be used as **to host an application by individual as it is already reserved**
- **1024 to 49152** are reserved for application hosting (for eg : **SQL runs on port 1433**)
- Remaining ports can be used by individuals

## Types of Network:

Based on the range of Network connection the networks are divided as below

- **Local Area Network**
- **Metropolitan Area Network**
- **Wide Area Network**

### Local Area Network (LAN):

- The full form of LAN is **Local-area Network**. 
- It is a computer network that **covers a small area such as a building or campus up to a few kilometers in size**. 
- LANs are commonly used to **connect personal computers and workstations in company offices to share common resources, like printers, and exchange information**

### Metropolitan Area Network (MAN):

- The full form of MAN is **Metropolitan Area Network**.
- MAN is a network that spans a **metropolitan area or a city. It is designed to connect multiple locations within a metropolitan area, typically covering a range of up to 50 kilometers**. 
- A single organization can own a MAN or can be shared by multiple organizations, such as universities, hospitals, or government agencies. 
- MANs are typically used to provide high-speed network connectivity between **local area networks (LANs) and wide area networks (WANs), enabling data transfer and communication between different locations within a city**. 
- MANs can be implemented using various technologies such as **Ethernet, Fiber Distributed Data Interface (FDDI), Asynchronous Transfer Mode (ATM), and Wireless technologies such as Wi-Fi, WiMAX, and microwave links**.

### Wide Area Network (WAN):

- WAN stands for **Wide Area Network**. 
- It is a computer network that covers a **large geographical area consisting of two or more LANs or MANs**. 
- These networks are established with **leased telecommunication circuits, in which two sides which are connected have routers that connect the LAN of both sides together in a network to facilitate communication**.
- SONET stands for **Synchronous Optical Network**. SONET is a **communication protocol**, developed by Bellcore – that is used to transmit a large amount of data over relatively large distances using optical fibre
- Frame Relay is a packet-switching network protocol that is designed to work at the data link layer of the network. It is used to connect Local Area Networks (LANs) and transmit data across Wide Area Networks (WANs)

## Networking devices:

### Modem:

- A Modem is a short form of **Modulator/Demodulator**. 
- The Modem is a hardware component/device that can connect **computers and other devices such as routers and switches to the internet**. 
- Modems **convert or modulate the analog signals coming from telephone wire into a digital form that is in the form of 0s and 1s**. 
- It acts as a **bridge between the telephone line and the computer**. 
- It converts the **input analog signal to a digital signal and directs it to the computer and vice versa**.
(i.e)  Modulator - converts analog signal from telephone line to digital signal to the computer connected to it; De-Modulator - converts digital signal from computer to analog signal and sends through telephone line  

### Routing:

- Routing is the process of **selecting a path for traffic in a network or between or across multiple networks**

![alt text](https://github.com/pknviki95/DevSecops-Learning/blob/main/NetworkingConcepts/Images/Routing.png)

**for example**:

Consider the image above.

- For a data packet to get from Computer A to Computer B, should it pass through networks 1, 3, and 5 or networks 2 and 4? 
- The packet will take a shorter path through networks 2 and 4, but networks 1, 3, and 5 might be faster at forwarding packets than 2 and 4. 
- These are the kinds of **choices network routers constantly make using routing**.

### Router:

- A Router is a **networking device that forwards data packets between computer networks**. 
- One or more packet-switched networks or subnetworks can be connected using a router. 
- By sending data packets to their intended IP addresses, it manages traffic between different networks and permits several devices to share an Internet connection by routing.

## Network Topologies:

- Topology defines the structure of the network of how all the components are interconnected to each other. There are two types of topology: physical and logical topology.

![alt text](https://github.com/pknviki95/DevSecops-Learning/blob/main/NetworkingConcepts/Images/6_types_of_network_topology.png)

