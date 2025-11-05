<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-Premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Video Demonstration</h2>
- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Protocol (RDP)
- Active Directory Domain Services (AD DS)
- PowerShell

<h2>Operating Systems Used</h2>
- Windows Server 2022 (Domain Controller)
- Windows 10 (Client)

<h2>High-Level Deployment and Configuration Steps</h2>
- Step 1: Create Resource Group
- Step 2: Create Virtual Network and Subnet
- Step 3: Deploy Domain Controller VM (DC-1)
- Step 4: Deploy Client VM (Client-1)
- Step 5: Configure static IP and DNS settings
- Step 6: Test connectivity and verify settings

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="REPLACE_WITH_RESOURCE_GROUP_IMAGE_URL" height="80%" width="80%" alt="Azure Resource Group"/>
</p>
<p>
<b>Step 1:</b> Create a Resource Group in your desired Azure region.
</p>
<br />

<p>
<img src="REPLACE_WITH_VNET_IMAGE_URL" height="80%" width="80%" alt="Azure Virtual Network"/>
</p>
<p>
<b>Step 2:</b> Create a Virtual Network (VNet) and Subnet to host DC-1 and Client-1.
</p>
<br />

<p>
<img src="REPLACE_WITH_DC_VM_IMAGE_URL" height="80%" width="80%" alt="Domain Controller VM"/>
</p>
<p>
<b>Step 3:</b> Create the Domain Controller VM (DC-1) <br>
- OS: Windows Server 2022 <br>
- Username: labuser <br>
- Password: Cyberlab123! <br>
- Set NIC private IP to static <br>
- Disable Windows Firewall (for testing connectivity)
</p>
<br />

<p>
<img src="REPLACE_WITH_CLIENT_VM_IMAGE_URL" height="80%" width="80%" alt="Client VM"/>
</p>
<p>
<b>Step 4:</b> Create the Client VM (Client-1) <br>
- OS: Windows 10 <br>
- Username: labuser <br>
- Password: Cyberlab123! <br>
- Attach to same region and VNet as DC-1 <br>
- Set Client DNS to DC-1 private IP <br>
- Restart VM from Azure Portal
</p>
<br />

<p>
<img src="REPLACE_WITH_PING_IMAGE_URL" height="80%" width="80%" alt="Ping DC from Client"/>
</p>
<p>
<b>Step 5:</b> Test Connectivity <br>
- Log in to Client-1 <br>
- Open PowerShell and run <b>ping DC-1 private IP</b> (ensure success)
</p>
<br />

<p>
<img src="REPLACE_WITH_IPCONFIG_IMAGE_URL" height="80%" width="80%" alt="ipconfig /all Output"/>
</p>
<p>
<b>Step 6:</b> Verify DNS Settings <br>
- Run <b>ipconfig /all</b> on Client-1 <br>
- Confirm DNS shows DC-1’s private IP address
</p>
<br />

<p>
<b>Step 7:</b> Lab Completion Notes <br>
- Do not delete VMs; they will be used for upcoming labs <br>
- To save costs, stop/turn off VMs in Azure Portal when not in use
</p>
