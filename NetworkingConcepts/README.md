Computer Networks Concepts:
---------------------------
Reference link : [text](https://www.cloudflare.com/en-gb/learning/)

Terminology:
------------

- Networking
- Client
- Server
- Client-server architecture
- Protocols
- Packets
- IP-Address
    - IP-Address format
        - IPV4
        - IPV6
    - Public
    - Private
    - Static
    - Dynamic
-Port Number
    - Reserved Ports

Abbrevations:
-------------

ISP - Internet service provider
IP - Internet protocol
NAT - Network address translator
DHCP - Dynamic Host Configuration Protocol

Networking:
-----------
- Networking is the act of making communication and data exchange between different communities and organizations

Client:
-------
- A client is a program that makes requests to a server

Server:
-------
- A server is a program that fulfills those requests

client-server Architecture:
---------------------------

![alt text](https://github.com/pknviki95/DevSecops-Learning/blob/main/NetworkingConcepts/Images/client-server.png)


Workflow of Client-server Architecture:
---------------------------------------

- The user devices can be a computer or a mobile device with an application installed. 
- The user also calls the Client sends a request to the host server anticipating a response and is disconnected from the network after completing the request. 
- The Client's bandwidth ability will determine the speed of delivery.

*For Example:*

- when you type www.google.com into your web browser, **your browser is acting as a client**. 
- It makes a **request** to Google’s servers for the website you’ve requested. 
- Google’s servers then fulfill that request by **sending back response** the HTML code for the Google home page. 
- Your browser then renders that HTML code into the familiar page of text, images, and links we all know so well.

**(i.e) client sends request to server and server sends reponse to respective request back to client**

Protocols:
-----------
- A protocol is a **set of rules and guidelines for communicating data**. 
- Rules are defined for each step and process during communication between two or more computers. 
- Networks have to follow these rules to successfully transmit data.
- It is determined/Developed by Internet community
- TCP,UDP,HTTP,HTTPS,FTP are some of protocols

How Data is Transferred?
------------------------
- The data that is communicated between client and server is through something called **Packets**.

Packets:
--------
- A packet is a **small segment of a larger message**. 
- Data sent over computer networks*, such as the Internet, is divided into packets. 
- These packets are then recombined by the computer or device that receives them.

IP-address:
------------
- ‘IP’ stands for Internet Protocol, which is the set of rules that makes it possible for devices to communicate over the **Internet**. 
- With billions of people accessing the Internet every day, unique identifiers are necessary to keep track of who is doing what. 
- The Internet Protocol solves this by **assigning IP numbers to every device accessing the Internet**.
- The IP address has format **x.x.x.x** ;every place holds number from **0-255** (i.e) 192.168.2.2
(eg): google.com ip address - **8.8.8.8 and 8.8.4.4**

**(i.e) IP- Address is similar to people living address Internet Protocol assigns IP numbers for all the individual device you use for accessing the internet**

![alt text](https://github.com/pknviki95/DevSecops-Learning/blob/main/NetworkingConcepts/Images/IP-adresses-infographic.png)


IP-Address format:
------------------- 
Based on format of IP address it differs in two types
    - IPV4
    - IPv6

| IPV4 | IPV6   |
| :---:   | :---: |
| IPv4 was implemented in 1983 and is still in use today.  |  It was introduced as IPV4 cannot fulfill as increase in current internet users   |
| :---:   | :---: |
| The format for IPv4 addresses is four sets of numeric dot-decimal separated by dots     | IPv6 addresses use a more complex format that utilizes sets of alphanumbers and letters separated by single or double colons  |
| :---:   | :---: | 
|  for example: ‘192.0.2.1’. This is a **32-bit format**, which means that it allows for 232, or about 4.3 billion  |   for example: ‘2001:0db8:85a3:0000:0000:8a2e:0370:7334’. This **128-bit format** can support 2128 unique addresses. (That computes to a 39-digit number!)               | 


Various Types of IP-Address:
-----------------------------
- Public
- Private
- Static
- Dynamic

 ![alt text](https://github.com/pknviki95/DevSecops-Learning/blob/main/NetworkingConcepts/Images/Private-and-Public-IP-Address.jpg)

 Public IP-Addresses:
 ---------------------------------

- A public IP address is a **unique identifier assigned to a device directly connected to the internet, such as a computer or a router**. It is used to identify the device on the internet and allows it to communicate with other devices.
- Public IP addresses are assigned by **internet service providers (ISPs)** and are unique, meaning that no two devices on the internet can simultaneously have the same public IP address.
- Some examples of public IP address use include hosting a website or online game server, remote access to a computer or network, and virtual private network (VPN) connections.

Private IP-Addresses:
---------------------

- A private IP address is a **unique identifier assigned to a device connected to a local network**, such as an office network or home. We use Private IP addresses to identify devices within the network that are not accessible from the internet.
- **Dynamic Host Configuration Protocol (DHCP)** is used to dynamically assign Internet Protocol (IP) addresses to each host on your organization's network
-Private IP addresses are typically assigned by a **router or a network address translator (NAT)** and are used to allow devices within the network to communicate with each other
- Unlike public IP addresses, which are unique across the internet, **we can reuse private IP addresses within different local networks**

Static Ip-Adddress:
--------------------

- A static public IP address is a **permanent address that does not change over time**

Dynamic IP-Address:
-------------------

- Dynamic public IP address is **assigned temporarily and can change periodically**.

Ports:
-------

- A port is a virtual point where **network connections start and end**. 
- Ports are **software-based and managed by a computer's operating system**. 
- Each port is associated with a **specific process or service**. 
- Ports allow computers to easily **differentiate between different kinds of traffic**

Port number:
------------

- Port Number are **standardized across all network-connected devices, with each port assigned a number**. 
- Most port numbers are **reserved for certain protocols** — for example, all Hypertext Transfer Protocol (HTTP) messages go to port 80. 
- While **IP addresses enable messages to go to and from specific devices**, **port numbers allow targeting of specific services or applications within those devices**.

for eg:
-------

- **When a request is sent from the client the server sends back response to the client**
- **DHCP determines which device requested based on the IP address assigned through router or NAT to send back the response**
- **But to determine which application/services has requested for that IP address assigned device will be determined by the Port number**
- **(i.e) 192.168.1.1:8080 - The response is sent back to device with IP address 192.168.1.1 where the application/service running on port 8080 of that device** 

- Port Numbers are **16-bit** numbers around **65000** port number are available
- **Hypertext Transfer Protocol (HTTP)** assigned to port **80**.

Reserved ports:
---------------

- Reserved ports are the ports that are **reserved/pre-defined for set of protocols**.
- **0 to 1023** are reserved ports.
- Reserved ports cannot be used as **to host an application by individual as it is already reserved**
- **1024 to 49152** are reserved for application hosting (for eg : **SQL runs on port 1433**)

- Remaining ports can be used by individuals