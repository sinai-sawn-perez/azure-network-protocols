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

- Create Virtual Machines in Azure
- Install Wireshark on Windows 10 Machine
- Observe Traffic using Wireshark
- Configure a Firewall in Azure

<h2>Actions and Observations</h2>

<p>
<img src="https://github.com/user-attachments/assets/19e55a88-e556-44d3-9c64-ed53b2a26df0" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating both VMs (Virtual Machines) in Azure, log into the Windows 10 machine then install Wireshark. When the installation is complete, open Wireshark and begin packet capture - set a filter to only observe ICMP traffic. Then retrieve the private IP address for the Ubuntu VM and ping it from the Windows 10 VM using Powershell. In the image above, notice that in the Powershell window 4 packets of information were sent from the Windows 10 VM to the Ubuntu VM successfully.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/fe4986cf-fced-4262-8201-ca8d0c67e2e1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Windows VM ping a public website, such as Google, using command line or PowerShell. Observe the ICMP traffic in Wireshark.
</p>

<p>
<img src="https://github.com/user-attachments/assets/0a5e1df4-bd6a-4399-b3e5-baf24c1fc455" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Using Wireshark filter to moniter DHCP traffic. In PowerShell issue your VM a new IP address and observe the resulting network traffic.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/e1094451-e70a-4c5f-8714-d933980f8a21" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the Windows VM, filter for SSH traffic using Wireshark. Open PowerShell and "SSH into" the Ubuntu VM using its private IP address. Type commands and observe the SSH traffic in Wireshark.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/3a4ce878-36c3-4ff6-873f-0a84186a5842" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Initiate a perpetual ping sending from the Windows 10 VM to the Ubuntu VM. Filter for ICMP in Wireshark to observe the traffic. In Azure, open the Network Security Groups for the Ubuntu VM and disable inbound ICMP traffic. Then return to Wireshark on the Windows 10 VM and observe the perpetual ping activity.
</p>
