<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Microsoft Remote Desktop (RDP)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
</p>
<p>
Welcome to my first in-depth IT tutorial! To begin we will have to create a Virtual machine using the Microsoft Azure portal(portal.azure.com). We will be using a VM(virtual machine) which is a remote computer. We are using a VM in order to protect our physical machine just in case something malfunctions, and also have a clean slate computer to continually replicate the lab on. Create a resource group and title it "osTicket". Afterwards create a VM with 2-4 CPUs. In this example I will be using 2 CPUs.
  
 <img width="1359" height="630" alt="image" src="https://github.com/user-attachments/assets/9a6ee547-be20-4dce-9e35-65d926f5fbc0"/>
 
<p>Next simply connect to your newly created VM using RDP using the public IPv4 address. If you are a Mac user you will have to download Microsoft Remote Desktop(RDP). 
</p>
<img width="396" height="245" alt="image" src="https://github.com/user-attachments/assets/eae14a13-3e5a-4d18-aebb-61227aa9d144" />

</p>
Once you have connected to your virtual machine you will want to go to your control panel. Uninstall a program, then select, Turn Windows features on and off.
</p>  
<img width="1124" height="594" alt="image" src="https://github.com/user-attachments/assets/a3d00d97-ba9d-472c-8b27-255aace74dc4" />
</p>
<img width="1111" height="585" alt="image" src="https://github.com/user-attachments/assets/9a4ccdaf-161c-4513-a82c-51f5dec983b4" />
</p>
You will want to install / enable IIS in Windows with CGI and Common HTTP Features

World Wide Web Services -> Application Development Features -> [X] CGI [X] Common HTTP Features
<img width="644" height="536" alt="image" src="https://github.com/user-attachments/assets/9e3f7c84-4d48-4e0f-beb6-3ec5c019a310" />

<img width="640" height="536" alt="image" src="https://github.com/user-attachments/assets/5345e815-b859-4c6c-8806-ecd2db6f291d" />

NOTE Make sure all Common HTTP Features are checked.

To make sure the IIS is installed / enabled go to a browser of your choice and search for 127.0.0.1 It should look something like this.

<img width="1341" height="707" alt="image" src="https://github.com/user-attachments/assets/f67d140f-5a48-4c8d-ab31-bca0166c7c29" />
</p>

Now that the IIS is enabled, From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) Go through the install wizard and complete the install.
<img width="723" height="455" alt="image" src="https://github.com/user-attachments/assets/6fe81ba4-94e1-4db0-ae04-ccd81fa4cd48" />


Next from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
<img width="723" height="455" alt="image" src="https://github.com/user-attachments/assets/9e8486e3-a169-40fe-87e3-79dd1edc81a2" />

Create a folder in the C drive called PHP.

<img width="559" height="319" alt="image" src="https://github.com/user-attachments/assets/0f9f72dd-54cb-4322-bcdd-26f10934687e" />

From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP
<img width="1001" height="543" alt="image" src="https://github.com/user-attachments/assets/8d5c3bb7-c097-4c2b-baea-f1d594e10ad8" />

!! ATTENTION !! If this appears, choose to “Keep” the file:

From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

<img width="471" height="290" alt="image" src="https://github.com/user-attachments/assets/2829faca-ba31-486c-8184-f5699de91a9c" />
</p>
Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) Run the setup wizard: Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->
</p>
<img width="479" height="373" alt="image" src="https://github.com/user-attachments/assets/2a6835eb-78cb-477d-9737-844acdb085e7" />
</p>
Make the new root password: Password1
</p>
<img width="492" height="368" alt="image" src="https://github.com/user-attachments/assets/001534e4-5f3c-4771-b2b5-2e8140eb0fb1" />
</p>
Execute the process on the next page.
</p>
<img width="498" height="376" alt="image" src="https://github.com/user-attachments/assets/149246c3-ce9e-4972-b471-6547274c1fa7" />

Excellent. Now that you have enabled IIS we need to install Web Platform Installer. I have provided a link here: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
  That link will provide you with all of the material you need to download to get osTicket up and running. Simply click the link and install the Web Platform Installer
</p>
<img src="https://i.imgur.com/AxHCfQ6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
Once you have installed Web Installer Platform open it. From inside the application you are going to install MySQL 5.5 Afterwards install x86 version of PHP up until 7.3. There are some failed files such as C++ redistributable package as well as PHP 7.3.8 and PHP Manager for IIS those files can be found with the install link.
</p>
<img src="https://i.imgur.com/JJ8bZeJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
<p>
Next download osTicket. Then extract and copy the "upload" folder into c:\inetpub\wwwroot. Afterwards rename the folder to osTicket
</P>
<img src="https://i.imgur.com/TUGiSKi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
</p>
<p>
Open IIS Manager and restart the server. Once inside IIS manager go to Sites->Default->osTicket on the right, click "Browse*.80" from there your default browser should open osTicket webserver.
</p>
<img src="https://i.imgur.com/4AkTkV0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Go back into IIS manager and enable some extensions. To do this you have to go to Sites->Default->osTicket
Then double click on PHP manager. Click on "Disable or enable an extension" Enable "php_intl.dll" & "php_opcache.dll" then refresh the osTicket webserver and obsereve the changes "Intl Extension" should now be enabled. 
</p>
<img src="https://i.imgur.com/APZgUTT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Go back into c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php rename the file to c:\inetpub\wwwroot\osTicket\include\ost-config.php
Assign permissions to ost-config.php Disable inheritance->Removeall
New Permissions->Everyone->all
</p>
<img src="https://i.imgur.com/1nYaYGe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Afterwards continue setting up osTicket in the browser (click continue) then you will name the Helpdesk to your liking. Select a default email that will receive emails from customers who submit tickets. 
</p>
<img src="https://i.imgur.com/RmVk3q5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
<p>Continue Setting up osticket in the browser MySQL Database: osTicket MySQL Username: root MySQL Password: Password1 Click “Install Now!”
Congratulations, hopefully it is installed with no errors!
Clean up
Delete: C:\inetpub\wwwroot\osTicket\setup
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php)
