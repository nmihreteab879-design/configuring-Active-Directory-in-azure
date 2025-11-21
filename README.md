<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" width="150"/>
</p>


Active Directory Deployment  
This part of the lab shows how I installed Active Directory, created the domain structure, set up admin accounts, and joined a workstation to the domain. Each section includes what screenshot to place, *why the step actually matters*, and the IT skills it demonstrates.


Installing Active Directory on DC-1  
<img width="785" height="564" alt="image" src="https://github.com/user-attachments/assets/e402d1ee-2c2a-495e-a278-2f09742a56d5" />


Why this matters:  
This step turns a normal Windows Server into the central identity system for the entire network. Every login, permission, computer object, and security policy depends on the domain controller being set up correctly.


Skills demonstrated:  
• Installing AD DS  
• Creating a new domain/forest  
• Promoting a server to a domain controller  


Creating Admin and Employee OUs  
(Insert screenshot: ADUC showing _EMPLOYEES and _ADMINS)


Why this matters:  
Without organization, companies with hundreds or thousands of users become impossible to manage. OUs keep accounts structured so policies, permissions, and security rules can be applied cleanly.


Skills demonstrated:  
• Designing and organizing OUs  
• Structuring user accounts for long-term management  
• Understanding how AD separates groups of users  

Creating a Domain Admin Account (jane_admin)  
(Insert screenshot: jane_admin user properties + Domain Admins group membership)


Why this matters:  
Administrators should not use the built-in Administrator account day-to-day. Creating a proper domain admin account follows real-world security best practices and prevents misuse of privileged access.


Skills demonstrated:  
• Creating domain users  
• Assigning admin privileges through groups  
• Logging in with proper elevated credentials  


Joining Client-1 to the Domain  
(Insert screenshot: domain join window + ADUC showing Client-1)


Why this matters:  
Joining a machine to the domain gives IT full control over it—policies, updates, authentication, and security. If this step isn’t done correctly, users can’t log in or receive company policies.


Skills demonstrated:  
• Joining Windows devices to a domain  
• Configuring DNS for domain communication  
• Verifying computer objects in ADUC  
• Moving devices into proper OUs  


Allowing Remote Desktop for Domain Users  
(Insert screenshot: RDP settings showing Domain Users allowed)


Why this matters:  
Companies often require remote access for employees. Setting this correctly ensures users can connect without giving them full admin privileges, which keeps the environment secure.


Skills demonstrated:  
• Configuring local RDP permissions  
• Managing domain user access on client machines  
• Understanding device-level access control  

Bulk User Creation with PowerShell  
(Insert screenshot: script in PowerShell ISE + created users in _EMPLOYEES)

Why this matters:
