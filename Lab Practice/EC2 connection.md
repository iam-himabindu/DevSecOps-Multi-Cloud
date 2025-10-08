
**Launching an Instance using EC2**

Amazon Elastic Compute Cloud (EC2) is used to Create, manage, and monitor virtual servers in the cloud.

**Step 1 - Give the Instance Name**

**Step 2 - Choose the AMI (Amazon Machine Image) which is Operating System**

**Note:** Choose only Free tier eligible while Practice

Architecture Types will be shown only for specific AMI like Amazon Linux AWS. Below is the in-detail difference for architecture types

<img width="359" height="269" alt="Image" src="https://github.com/user-attachments/assets/f948042c-ebee-4fee-861d-76a016f4fef4" />

The dropdown in your image shows a choice between **64-bit (x86)** and **64-bit (Arm)** architectures.

**🔧 x86 (64-bit)**

Also called **x86-64** or **AMD64**.

Developed by Intel/AMD.

**Most common architecture** for desktops and laptops.

Used in most Windows PCs.

Compatible with traditional Windows software.

**🔋 Arm (64-bit)**

Based on **ARM architecture** (originally for mobile and low-power devices).

Common in smartphones, tablets, and newer laptops (like **Apple Silicon Macs** or some **Windows on ARM** devices).

More power-efficient, often used in devices where battery life matters.

**Step 3 - Choose the Instance Type**

**Note:** Choose only Free tier eligible while Practice

**Step 4 - Key Pair Login**

- Key pair is the used as a user authentication for developers to login the server
- There are 2 key pairs: Public key and Private Key
- Public key can be used for server reference
- Private key is for the developers who wants to login the server
- Whenever we create a key pair, private key will be downloaded in our local machine and we can use the same key for multiple servers

**Key pair type - RSA and ED25519**

Both Public and private keys are encrypted for RSA and ED25519 but the algorithm are different

**Private key file format - (.pem and .ppk)**

.pem file format is used with open SSH (Secured shell for Linux)

.ppk file format is used with PUTTY Tool

<img width="899" height="540" alt="Image" src="https://github.com/user-attachments/assets/aac88301-cd7d-412c-a0ce-90445fa19270" />

**Let's create both the key types:**

RSA and ED25519 Key par were created and private keys for both were downloaded in the local machine.

<img width="823" height="274" alt="Image" src="https://github.com/user-attachments/assets/3f6073d0-4b6b-4997-a12a-de2730b26610" />

Without changing network settings configure storage and advanced details, please click on launch instance

**Step 5: Wait for your instance to launch successfully**

<img width="940" height="71" alt="Image" src="https://github.com/user-attachments/assets/d5512b3d-6e22-4e98-9966-8ab0d62bcdaa" />

**Step 6: Edit your security group rules**

Below are the default inbound and outbound rules for security groups

<img width="808" height="312" alt="Image" src="https://github.com/user-attachments/assets/c7c9d39d-1ad4-4fb2-9582-31d1d5c967fb" />

**Now let us add more inbound rules**

<img width="940" height="263" alt="Image" src="https://github.com/user-attachments/assets/6ca2e2bd-c872-4295-914f-bd692416dcd6" />

**Note:** When there is no inbound rule in the security group it means everything is blocked and no login is possible

Outbound rule will be default as All traffic to give the response back to any request

<img width="940" height="141" alt="Image" src="https://github.com/user-attachments/assets/847ed146-8fb3-4650-b3e4-93f0c27e499c" />

**Step 7: Connect to the Server**

Here to connect to a public server we need Internet, public IP address, developer IP address, keypair (private key), Username(ec2-user) for AWS Linux Server and also secured shell For Linux (port 22)

**Methods to connect server**

- Command prompt
- Directly AWS console
- Third party tools like Putty, Vs code, MobaXterm and Gib bash

**Connect Server Through CMD**

**Open command prompt and give the below command**

**ssh -i "File path" ec-user@public IP**

**File path from the local where private key downloaded "C:\\Users\\Hima\\Downloads\\test key1.pem"**

**Public IP - 3.85.237.82**

**ssh -i "C:\\Users\\Hima\\Downloads\\test key1.pem" ec2-user@3.85.237.82**

**Test case 1: Given the wrong path**

<img width="940" height="184" alt="Image" src="https://github.com/user-attachments/assets/e0352762-df96-4331-9195-572c31e69d72" />

**Test case 2: Given the wrong public IP/Giving Private IP instead of Public IP**

<img width="940" height="91" alt="Image" src="https://github.com/user-attachments/assets/b392c246-b90d-448b-aaee-e7fc89b3c2e5" />

**Test case 3: Given the wrong private key**

<img width="940" height="148" alt="Image" src="https://github.com/user-attachments/assets/80371219-61fa-4dac-a4ee-d5749e361209" />

**Test case 4: Removed all inbound SG rules**

<img width="940" height="81" alt="Image" src="https://github.com/user-attachments/assets/98d3af3a-8a04-43bb-b583-549c0ae44b8d" />

**Test case 5: Adding one rule for HTTP port 80 with source as my IP address**

<img width="940" height="75" alt="Image" src="https://github.com/user-attachments/assets/e7cbc512-e14f-4e3e-bfb5-d89a4668f510" />

**Test Case 6: Wrong Username**

<img width="940" height="78" alt="Image" src="https://github.com/user-attachments/assets/6383067d-a901-44c0-ac31-970bef0aec87" />

**Test Case 7: SSH Server Misconfigured**

<img width="940" height="79" alt="Image" src="https://github.com/user-attachments/assets/7f99f196-14a8-4e67-be0f-84a020189217" />

**Test case 8: Adding one rule for SSH port 22 with source as my IP address (or) Adding one rule all traffic with source as anywhere IPV4**

<img width="940" height="373" alt="Image" src="https://github.com/user-attachments/assets/b05871a5-56ca-4a96-b8cb-63fb7432eeda" />

**Connect Server Through AWS Console**

**Note:** Private key is not required because it is already in the AWS login so no need of authorization again.

**Test case: Below is the common error for different test cases**

- No inbound SG Rule
- Adding type as http instead of ssh
- Adding type as ssh but source as My IP address

<img width="940" height="128" alt="Image" src="https://github.com/user-attachments/assets/8bea1850-8f2a-4fce-9b29-2506bc379a5f" />

**Test case: Below is the common successful connect for below test cases**

- Adding type as ssh with source as Any IP address
- Adding type as all traffic with source as Any IP address

<img width="940" height="326" alt="Image" src="https://github.com/user-attachments/assets/28cc200b-7320-4df4-af8c-888bbd6602bb" />

**Connect Server Through MobaXterm**

**Download and install the third-party tool in your local machine**

<img width="679" height="414" alt="Image" src="https://github.com/user-attachments/assets/80a528a7-71b6-41c0-acbb-d9bd57631b95" />

**Go to New Session > Choose session type as SSH**

**Remote Host as Public IP**

**Go to advance setting and upload the relevant Private key**

**Login as: ec2-user**

**Observations**

**Test case 1: Given remote host as Private IP instead of public IP**

**Test case 2: Given remote host as Private IP instead of public IP by uploading wrong Private key**

**Test case 3: Removed all inbound SG rules**

**Test case 4: Adding one rule for HTTP port 80 with source as my IP address (or) anywhere IP**

**NOTE:** For all the above 4 test cases - Error is same as connection timed out

<img width="940" height="351" alt="Image" src="https://github.com/user-attachments/assets/74ec45b9-4450-415e-8063-230a7e8099f2" />

**Test case 5: Given remote host as Public IP by uploading wrong Private key**

<img width="940" height="252" alt="Image" src="https://github.com/user-attachments/assets/fba4eb6c-9a7a-44c5-944f-581baef840b7" />

**Test Case 6: Wrong Username**

<img width="940" height="236" alt="Image" src="https://github.com/user-attachments/assets/699af712-8710-4510-a5d5-871af23c9926" />

**Test case 7: Adding one rule for SSH port 22 with source as my IP address (or) Adding one rule all traffic with source as anywhere IPV4**

<img width="940" height="586" alt="Image" src="https://github.com/user-attachments/assets/0ac33b26-fef4-429b-baa7-dc911ba57ae4" />

**Step 8: Navigate to the instance details page and change the instance state to Terminate**

<img width="940" height="60" alt="Image" src="https://github.com/user-attachments/assets/e7760a83-1aa3-486e-a196-d69c9403e456" />
