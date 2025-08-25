<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Install Active Directory
- Create a Domain Admin user within the domain
- Join "Client-1" to your domain
- Setup Remote Desktop for non-administrative users on "Client-1"

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Deploy a Virtual Network and VMs in Azure
First, log in to the Azure Portal and create a new Virtual Network (VNet) to host your lab environment. Then, deploy two Windows Server virtual machines: one will act as your Domain Controller (DC-1) and the other as a client workstation (Client-1). Assign static private IP addresses within the VNet, and make sure both VMs can communicate with each other.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install and Configure Active Directory on DC-1
Log in to DC-1 and install the Active Directory Domain Services (AD DS) role using Server Manager. Promote DC-1 to a Domain Controller and create a new forest, specifying a domain name (for example, mylab.local). After the promotion, restart DC-1 and log in using a domain account, such as mylab\labuser. This sets up the foundation for your domain environment.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create Domain Admins and Join Client VM
Using Active Directory Users and Computers (ADUC), create OUs such as “_EMPLOYEES” and “_ADMINS.” Add a new user for administrative tasks (e.g., jane_admin) and assign them to the Domain Admins group. Then, log in to Client-1 as a local administrator and join it to the domain. Verify in ADUC that Client-1 appears in the correct OU (for example, “_CLIENTS”). Optionally, configure Remote Desktop for domain users so non-admin accounts can log in to the client machine.
</p>
<br />
