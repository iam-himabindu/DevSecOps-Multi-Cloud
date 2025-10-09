# What is a Network?

When two or more computers and computing devices connected together with each other through communication channels, such as cables or wireless media and sharing some files, then it is called a **Network**.

A network is used to:

Allow the connected devices to communicate with each other.

Enable multiple users to share devices over the network, such as music and video servers, printers and scanners.

The Internet is the largest network in the world and can be called "the network of networks".

## Types of Networks

There are different types of networks. But the main two are LAN and WAN

- **LAN** (Local Area Network) - interconnects computer within a limited area, such as residences, schools. e.g.: Wi-Fi, Ethernet
- **MAN** (Metropolitan area network) - used in metropolitan area (cities).
- **WAN** (Wide Area Network) - extends LAN over a large geographic area. e.g:- optical fiber cable
- **SONET** (Synchronous Optical Network) - used in submarine.

## Network Components

### Switch

It is a device which connects two or more computers.

### Router

It is a device which is actually used to connect one network with another.

### Modem

It is also a device used for modulation and Demodulation.

### Hub

It is just a power extension dummy device that just broadcast the signals to its connected computers.

### NIC

It is known as Network Interface Card which is used to connect your computer with the internet. It is wireless card preinstalled on motherboard now-a-days. It has a MAC (Media Access Control) address.

### Bridge

It is also a networking device that connects multiple LANs (local area networks) together to form a larger LAN. It reduces the broadcasting part, and it store the MAC address of the computer but now this device is also obsoleted and replaced by switch.

## What is Protocol?

A network protocol is a set of rules which is set up by people that determine how a particular data is transmitted between different devices in the same network. e.g.: HTTP, TCP, IP, FTP, SMTP etc.

**IP Address and its Types and Classes:**

**IP Address**: An IP (Internet Protocol) address is a unique number assigned to each device on a network, allowing them to communicate with each other. Itʼs like a device's "address" on the internet or local network.

### Types of IP Addresses

#### IPv4

32-bit address, written as four numbers separated by dots (e.g.,

).

123.89.46.7

This is a 32-bit IP address, means it contains a combo of 32 (1 and 0's). In this version of IP address there are 4 groups or **Octets** (8 bits), and each octet is represented by a decimal value in the address. It is easy to remember.

<img width="819" height="405" alt="Image" src="https://github.com/user-attachments/assets/91a6d7c7-f43c-4788-ad18-cf89e3a98d6b" />

Commonly used, but limited number of addresses (about 4.3 billion).

#### IPv6

128-bit address, written in eight groups of hexadecimal numbers (e.g.,

2001:0db8:85a3:0000:0000:8a2e:0370:7334 ).

Provides a vastly larger pool of addresses, designed to replace IPv4 as it runs out.

<img width="904" height="193" alt="Image" src="https://github.com/user-attachments/assets/2c8aa969-f106-411f-971b-7a99eaee2c1f" />

#### Public IP

Used to identify devices on the internet. Assigned by ISPs and accessible globally.

#### Private IP

Used within private networks (like home or office networks).

Not accessible from the internet; usually in ranges like 192.168.x.x ,

10.x.x.x , or 172.16.x.x - 172.31.x.x .

#### Static IP

Manually assigned, doesnʼt change.

Often used for servers and devices that need a consistent address.

#### Dynamic IP

Automatically assigned by a DHCP (Dynamic Host Configuration Protocol) server. Changes periodically; commonly used for home devices.

### IP Address Classes (IPv4 Only)

There is an organization called **IANA** (Internet Assigned Numbers Authority) who divides the IP address into different classes. You have to know about binary to decimal conversion to understand this.

IPv4 addresses are divided into **five classes** based on the starting number, which determines their usage in networks.

| **Class** | **Range** | **Purpose** |
| --- | --- | --- |
| **A** | 1.0.0.0 - 126.0.0.0 | Large networks, like big organizations. |
| **B** | 128.0.0.0 - 191.255.0.0 | Medium-sized networks. |
| **C** | 192.0.0.0 - 223.255.255.0 | Small networks, like home or business LANs. |
| **D** | 224.0.0.0 -<br><br>239.255.255.255 | Reserved for multicasting. |
| **E** | 240.0.0.0 -<br><br>255.255.255.255 | Experimental, used for research. |

<img width="962" height="845" alt="Image" src="https://github.com/user-attachments/assets/b681735b-9f65-4212-be41-1e3b647fb23b" />

Note:

Class A addresses in IPv4 officially start from **1.0.0.0** and go up to **126.0.0.0**. The address **0.0.0.0** is not part of the Class A range and has a special purpose in networking.

**0.0.0.0** is a special address, not part of the usable IP address range in Class A.

The **127.0.0.0** to **127.255.255.255** range, especially **127.0.0.1**, is reserved for

**loopback addresses** in IPv4.

### What is Loopback?

**Loopback address** allows a device to communicate with itself. Itʼs often used for testing network software on the local machine.

### Key Points

**127.0.0.1** is commonly known as "localhost."

Any IP address in the **127.x.x.x** range will loop back to the same device.

Useful for **testing** networking applications without needing an external network.

#### IP address - Network ID and Host ID

There are two parts to an IP address - Network ID and Host ID (Any device which gets the IP address is called a Host).

The **Network ID** portion differs depending on the IP class:

**Class A**: 1st octet is the Network ID.

**Class B**: 1st and 2nd octets are the Network ID.

**Class C**: 1st, 2nd, and 3rd octets are the Network ID.

**Direct Connection**: Devices with the same Network ID can connect without a router.

**Router Requirement**: Devices with different Network IDs need a router to connect.

# Subnetting

Divides a network into smaller, more manageable segments.

Example: A network with IP address 192.168.1.0/24 can be divided into subnets like 192.168.1.0/25 and 192.168.1.128/25.

### Example of Subnetting

Given network: **192.168.1.0/24 192.168.1.0/24** is a Class C network.

**/24** indicates a subnet mask of **255.255.255.0**, meaning there are **8 bits for hosts** (32 total bits in IPv4 - 24 bits for the network portion ![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAPCAYAAAA2yOUNAAAABmJLR0QA/wD/AP+gvaeTAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAAlklEQVQokXXPMQoCQQyF4f+tLjbiyQUt7Kw9ywpWth7AA8iisArPJsKMmwkMDMlHeBHwALC9oVGyjSQHVIa6YjhJsqRligKugCfwltRXynb1gBEwsPj1Ov7K9hp4AZ8qeHqRNAG9bTVRQFfBEzDGdzsLHpvvEX5nO73uVoIZAq4B9lW/AJcAh9n2AOcAx0ZGhgCnDNjmC2nMtF+e3DDqAAAAAElFTkSuQmCC) 8 bits for hosts).

**192.168.1.0/24** provides **256 IP addresses** (from 192.168.1.0 to 192.168.1.255).

### Dividing into Smaller Subnets

To divide this into two equal subnets, we can use **/25** subnet masks, which allocate **7 bits for hosts** (32 - 25 ![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAPCAYAAAA2yOUNAAAABmJLR0QA/wD/AP+gvaeTAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAAlklEQVQokXXPMQoCQQyF4f+tLjbiyQUt7Kw9ywpWth7AA8iisArPJsKMmwkMDMlHeBHwALC9oVGyjSQHVIa6YjhJsqRligKugCfwltRXynb1gBEwsPj1Ov7K9hp4AZ8qeHqRNAG9bTVRQFfBEzDGdzsLHpvvEX5nO73uVoIZAq4B9lW/AJcAh9n2AOcAx0ZGhgCnDNjmC2nMtF+e3DDqAAAAAElFTkSuQmCC) 7 bits for hosts).

#### Subnet 1: 192.168.1.0/25

**Range**: 192.168.1.0 to 192.168.1.127

**Subnet Mask**: 255.255.255.128

**Total IPs**: 128 addresses (126 usable for hosts, as the first address is the network address and the last is the broadcast address).

#### Subnet 2: 192.168.1.128/25

**Range**: 192.168.1.128 to 192.168.1.255

**Subnet Mask**: 255.255.255.128

**Total IPs**: 128 addresses (126 usable for hosts).

### Summary Table

<img width="797" height="191" alt="Image" src="https://github.com/user-attachments/assets/7e740a33-0825-4490-8f67-d7d13a6c4d22" />

**Explanation:**

By using a **/25 mask** instead of **/24**, we split the network into two subnets with 128 IP addresses each.

This creates smaller segments within the original network, making it easier to manage specific groups of hosts separately.

### Benefits of Subnetting

- **Improves Network Performance**: Reduces broadcast domains, limiting broadcast traffic to specific subnets.
- **Enhances Security**: Allows segregation of different departments or functions within an organization.
- **Efficient IP Usage**: Prevents wasting IP addresses by only allocating what is necessary for each subnet.

### CIDR (Classless Inter-Domain Routing)

**CIDR (Classless Inter-Domain Routing)** is a method for allocating IP addresses and IP routing that replaces the older **classful network** system. It was introduced to improve IP address utilization and simplify routing.

**The table below outlines the most common combination of addresses and netmasks and important details about them.**

<img width="779" height="586" alt="Image" src="https://github.com/user-attachments/assets/24d07af0-6eb1-41ba-b46c-2347ab6eefc1" />
