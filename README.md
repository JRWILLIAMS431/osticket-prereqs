# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. Join me 🤝<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://youtu.be/0UJkX3_qazQ)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- Installation Files https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Task 1 Create Resource Group and Virtual Machine
- Task 2 Upload and Install files
- Task 3 Create osTicket Account 
- Task 4 Login
- *Bonus Cleaning🧹

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/XPGPUe3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First, we are going to Create a Resource Group and Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs. Once this is done we are going to log into the Virtual machine using the Microsoft remote desktop application.
 
  * I am working on a macbook💻. 

</p>
<br />

<p>
<img src="https://i.imgur.com/gsmMAym.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step two may prove to be the most difficult portion of the lab and I suggest referring to the video linked above to follow along with the intricacies of downloading and installing these files. That being said we will be running IIS (Internet Information Services) as an administrator to enable CGI. Once this is done we will download and install each of the files and applications from the Installation Files list. One of the most important of these being the PHP manager. Create a new file in the windows directory C:\PHP. 

At that point the installation steps go as follows: 

  Download PHP 7.3.8 and unzip the contents into C:\PHP

  Download and install VC_redist.x86.exe.

  Download and install MySQL 5.5.62 
* Typical Setup 
* Launch Configuration Wizard (after install) 
* Standard Configuration 
* Username - root
* Password - Password1

Open IIS as an Admin

Register PHP from within IIS

Reload IIS (Open IIS, Stop and Start the server)

Install osTicket v1.15.8
Download osTicket from the Installation Files Folder
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Some of the extensions will be disabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, observe the changes

Rename: ost-sampleconfig.php file to ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

</p>
<br />

<p>
<img src="https://i.imgur.com/FoeGRR0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue creating osTicket by creating an agent/admin account login. Once this is completed we are going to create a SQL databse in Heidi SQL. 
Follow the instructions below:

  Download and install HeidiSQL.

  Open Heidi SQL

  Create a new session, root/Password1

  Connect to the session

  Create a database called “osTicket”

  Enter this database information into your account login 
  
  Use the root username and Password1 from the SQL installation portion

  Click “Install Now!”

</p>
<br />

<p>
<img src="https://i.imgur.com/rUWsJGl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once created, your osTicket account should have all of the neccasary files uploaded and enabled to run properly. Now browse to your helpdesk login page and attempt to login to the account.   
</p>
<br />

<p>
<img src="https://i.imgur.com/6u4Vg3F.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Congratulations, you have successfully logged into your osTicket portal. Now we will finish with a bit of cleanup🧹. 

  Delete: C:\inetpub\wwwroot\osTicket\setup

  Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
  
  * ( logout out of the virtual machine and delete the resource group if you want to avoid any unwanted charges to your Azure account)

</p>
<br />
