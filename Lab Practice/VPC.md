**What is a VPC?**

**VPC** stands for **Virtual Private Cloud**.  
It is a **virtual network** in cloud platforms (like AWS, GCP, Azure) that mimics a traditional on-premise network.

- You define your own IP address ranges.
- You can launch resources (like servers, databases) inside the VPC.
- It offers control over routing, subnets, firewalls, and gateways.

**Think of it like:** Your own private section of the cloud where your services live.

**What is a Subnet?**

A **subnet** (short for _subnetwork_) is a **smaller section of a VPC**.

- It allows you to divide your VPC's IP address range into smaller chunks.
- Subnets can be **public** (internet accessible) or **private** (no direct internet access).
- Resources in the same subnet can communicate locally.

**Example:**

- VPC CIDR: 10.0.0.0/16
- Subnet A: 10.0.1.0/24
- Subnet B: 10.0.2.0/24

**What is CIDR and Netmask?**

**CIDR** = _Classless Inter-Domain Routing_  
It defines **IP address blocks** using this format: IP_address/CIDR_prefix_length.

- CIDR **prefix** determines how many bits are used for the **network** part of the address.
- The rest are for **hosts**.

**Example:**

- 10.0.0.0/24 means:
- First 24 bits are the network.
- Remaining 8 bits are for hosts.
- **Total IPs**: 2⁸ = 256 addresses (254 usable).

| **CIDR** | **Netmask** | **IPs in Range** |
| --- | --- | --- |
| 10.0.0.0/16 | 255.255.0.0 | 65,536 |
| 10.0.1.0/24 | 255.255.255.0 | 256 |
| 10.0.1.0/28 | 255.255.255.240 | 16  |

**What are Private IPs?**

**Private IP addresses** are used **within** private networks (like your VPC or home router network).  
They **cannot be accessed** directly from the internet.

**Private IP ranges (as per RFC 1918):**

- 10.0.0.0 - 10.255.255.255 (10/8)
- 172.16.0.0 - 172.31.255.255 (172.16/12)
- 192.168.0.0 - 192.168.255.255 (192.168/16)

These IPs are used for:

- Internal communication
- Servers, databases, and internal services

For public internet access, you need a **public IP** or a **NAT Gateway**.

**Let's Create VPC and Subnet in AWS with reference to below architecture**
<img width="940" height="426" alt="Image" src="https://github.com/user-attachments/assets/db600d0c-8093-48f4-84ca-e2959836b92f" />

**Steps to Create a VPC and Subnets**

- **Create a VPC:**

- Enter a VPC name.
- Provide an IPv4 CIDR block (must be between /16 and /28).
- Click "Create VPC".

- **Create Subnets:**

- Navigate to the Subnets section.
- Click "Create Subnet".
- Select the VPC you just created.
- Enter a Subnet name.
- Choose an Availability Zone (AZ).
- Specify an IPv4 CIDR block for the subnet (it must be within the range of the VPC's CIDR block).
- Click "Add new subnet" to create a second subnet and repeat the above steps.
- Once both subnets are configured, click "Create Subnet".
<img width="940" height="401" alt="Image" src="https://github.com/user-attachments/assets/6e65f60a-4c0a-4047-95ee-d718670fa0e0" />
**Internet Gateway (IGW)**

**✅ What It Is:**

An **Internet Gateway** is a **VPC component** that allows communication between **your VPC and the internet**.

✅ What It Does:

Allows instances in public subnets to send and receive traffic from the internet.

It must be:

- Attached to a VPC
- Referenced in a Route Table (with 0.0.0.0/0 route)

**✅ Example:**

Your EC2 in a **public subnet** can reach Google.com if:

- It has a public IP address
- The subnet's route table points to the **IGW**

**NAT Gateway (Network Address Translation)**

**✅ What It Is:**

A **NAT Gateway** lets **instances in a private subnet** access the internet **outbound only**, **without exposing** them to incoming internet traffic.

✅ What It Does:

- Allows private instances to: Download update, Access APIs or external services
- But no one from the internet can access them directly.

**✅ Example:**

Your EC2 in a **private subnet** needs to install packages from the internet:

- It sends the request to the **NAT Gateway** in a **public subnet**
- The NAT Gateway translates the request and sends it out via the **IGW**

NAT Gateway must be placed in a **public subnet** with a route to the **IGW**

**Route Table (RT)**

**✅ What It Is:**

A **Route Table** controls how network traffic is directed **within a VPC** and **to outside destinations**.

✅ What It Does:

Each subnet in your VPC must be associated with a route table.

It defines routes like:

- Local (within VPC)
- To Internet Gateway (for public subnets)
- To NAT Gateway (for private subnets)
- To VPN or other VPCs

**✅ Example Routes:**

| **Destination** | **Target** | **Purpose** |
| --- | --- | --- |
| 10.0.0.0/16 | local | Default, VPC internal traffic |
| 0.0.0.0/0 | IGW | Internet access (public) |
| 0.0.0.0/0 | NAT Gateway | Internet access (private) |

**📊 Summary Table**

| **Component** | **Purpose** | **Used By** |
| --- | --- | --- |
| **Internet Gateway (IGW)** | Enables public internet access | Public Subnets |
| **NAT Gateway** | Allows private subnets to access internet **outbound only** | Private Subnets |
| **Route Table** | Defines how traffic moves (e.g., to IGW or NAT) | All Subnets (must be associated) |

**🖼️ Real-World Use Case**

| **Subnet Type** | **Can Access Internet?** | **Can Be Accessed from Internet?** | **Uses** |
| --- | --- | --- | --- |
| **Public** | ✅ Yes | ✅ Yes (if public IP) | Web Servers |
| **Private** | ✅ Yes (via NAT) | ❌ No | Databases, Internal Apps |

**Let's Create Public and Private Networks with reference to below Architecture**
