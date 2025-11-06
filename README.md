<h2>Deployment and Configuration Steps</h2>

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy Active Directory in Azure](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines / Compute / Networking)
- Remote Desktop Protocol (RDP)
- Active Directory Domain Services
- PowerShell / Command Prompt

<h2>Operating Systems Used</h2>

- Windows Server 2022 (Domain Controller)
- Windows 10 (Client Machine)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create Resource Group and Virtual Network
- Create a Domain Controller VM (DC-1) and assign a static private IP
- Disable DC-1 firewall (for internal connectivity testing)
- Create Client-1 VM and configure DNS to point to DC-1
- Test connectivity between Client-1 and DC-1 using ping
- Verify DNS resolution with `ipconfig /all`

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="630" height="547" alt="image" src="https://github.com/user-attachments/assets/4c316122-f528-4799-9331-20d4de699b90" />
</p>
<p>
I started by creating a resource group and a virtual network in Azure. The resource group keeps all of the related components organized in one place, and the virtual network allows the virtual machines to communicate with each other privately in the cloud.
</p>
<br />

<p>
<img width="1534" height="932" alt="image" src="https://github.com/user-attachments/assets/9c78ddc9-51c9-4219-8670-43d2575b3255" />
</p>
<p>
I then created a Windows Server 2022 virtual machine and named it DC-1. This machine will act as the domain controller in the environment. After it was created, I set its private IP address to static. This is important because the client machine needs to always be able to reach the domain controller at the same address. If the IP changed whenever the VM restarted, the client would fail to communicate with it.
</p>
<br />

<p>
<img width="1047" height="782" alt="image" src="https://github.com/user-attachments/assets/c238827c-32b5-461c-ac55-581df69055e3" />
</p>
<p>
Next, I logged into DC-1 using Remote Desktop. I went into the Windows Firewall settings and disabled the firewall for testing purposes. This step ensures that basic network communication, like ping, works between the two virtual machines. In a real production environment, the firewall would stay on and specific rules would be configured instead.
</p>
<br />

<p>
<img width="795" height="888" alt="image" src="https://github.com/user-attachments/assets/b0439c04-ad27-45a5-9a2c-64e3bbf530c6" />
</p>
<p>
Then I changed its DNS server settings so that it pointed to DC-1's private IP address. This is necessary because Active Directory depends on DNS to locate and communicate with the domain controller.
</p>
<br />

<p>
<img width="799" height="885" alt="image" src="https://github.com/user-attachments/assets/5c747fde-e31b-4669-b980-460e9d8fd3fc" />
</p>
<p>
After updating Client-1's DNS settings, I restarted the virtual machine from the Azure portal so that the network changes would apply correctly.</p>
<br />
<img width="858" height="729" alt="image" src="https://github.com/user-attachments/assets/54923f7f-ef4d-494f-b89e-01e26b18a171" />
</p>
<p>
When Client-1 came back online, I logged in and tested the connection by pinging DC-1's private IP address. The ping was successful, which showed that network communication was working. Finally, I ran "ipconfig /all" on Client-1 to confirm that its DNS server was now set to DC-1's IP address, which verified that the setup was correct.





