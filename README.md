# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- OS Ticket Virtual Machine Creation
- Install / Enable IIS in Windows
- Install  web platform installer
- Install MySQL
- Install c++ Redistributable
- Configure permissions and install OS Ticket

<h2>Installation Steps</h2> 


<img src="https://i.imgur.com/JcX0ZvW.png" height="80%" width="80%" alt="OS Ticket Resource Group Creation"/>
</p>
<p>
Create a Resource Group
<img src="https://i.imgur.com/LIFBAtX.png" height="80%" width="80%" alt="OS Ticket VM Creation"/>
</p>
<p>

Create a Windows 10 Virtual Machine (VM) with 4 Virtual CPU's. When creating the VM, allow it to create a new Virtual Network (Vnet)


  
<img src="https://i.imgur.com/iILGtnJ.png" height="80%" width="80%" alt="Install IIS"/>
</p>
<p>
<img src="https://i.imgur.com/0DCZvHu.png" height="80%" width="80%" alt="Install IIS"/>
  
Install / Enable IIS in Windows WITH
CGI and Common HTTP Features
World Wide Web Services -> Application Development Features ->
[X] CGI
[X] Common HTTP Features
AND IIS Management Console
Internet Information Services -> Web Management Tools -> IIS Management Console
	[X] IIS Management Console


</p>
<br />

From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)

Create the directory C:\PHP

From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
</p>
<br />

<p>
<img src="https://i.imgur.com/3MrxnWG.png" height="80%" width="80%" alt="register PHP "/>
Open IIS as an Admin

Register PHP from within IIS

Reload IIS (Open IIS, Stop and Start the server)


<img src="https://i.imgur.com/ntv2wQp.png" height="80%" width="80%" alt="Configure Permissions Install OS Ticket "/>
</p>
<p>
Install osTicket v1.15.8
Download osTicket from the Installation Files Folder
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS 
(Open IIS, Stop and Start the server)
Go to sites -> Default -> osTicket
On the right, click “Browse *:80”
Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, observe the changes

<img src="https://i.imgur.com/BWU2e2k.png" height="80%" width="80%" alt="Configure Permissions Install OS Ticket "/>
</p>
<p>

<img src="https://i.imgur.com/kgipxsi.png" height="80%" width="80%" alt="Configure Permissions Install OS Ticket "/>
	
Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All
