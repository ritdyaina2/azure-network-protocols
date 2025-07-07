<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Created two virtual machines in the same virtual network
- Set up a Network Security Group (NSG) to control traffic
- Added inbound and outbound rules in the NSG
- Attached the NSG to a virtual machine

<h2>Actions and Observations</h2>

<h2>NSG Overview</h2>

Step 1 - Two virtual machines were created in Azure and placed in the same virtual network to allow communication between them.
<p>
  
![cap](https://github.com/user-attachments/assets/9ceb42ef-20c6-4e39-9bac-6afaa5bc9c75)
</p>
<br />


<h2> Assigning the NSG to the VM</h2>

Step 2 -This shows the Network Security Group attached to the VM's network interface, where traffic rules are applied.

<p>
  
![ping](https://github.com/user-attachments/assets/fa62c5b1-016f-413c-a83e-c2911a3e3e3a)

</p>
<br />


<h2>Creating a Deny ICMP Rule</h2>

Step 3 -A custom inbound rule was created to block ICMP traffic. The rule uses protocol-specific filtering and a high priority to override default allow rules.
<p>
  
![Screenshot 2025-06-19 161848](https://github.com/user-attachments/assets/ae4ffec0-f553-44fc-990f-b8832affca88)


</p>
<br />
<h2> Ping Test</h2>
Step 4 - A ping test was performed after applying a custom Deny-ICMP rule in the Network Security Group. The request was blocked, confirming that the security rule is working as intended.

<p>
  
  ![Screenshot 2025-06-20 170847](https://github.com/user-attachments/assets/22408bed-1dcb-4890-97d2-2dcf49d353b5)

<br />
