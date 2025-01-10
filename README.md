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

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- oSTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


<h2>Installation Steps</h2>
<h3>1) Creating a Virtual Machine</h3>
<p>
Start by searching and selecting the "Virtual Machines" in the search bar of Microsoft Azure (Make sure you select "Virtual Machines" not "Virtual Networks"). 
</p>

<p>
<img src="https://i.imgur.com/E8texzH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<br />
<h3>2) Setting up Resource Group</h3>

<p>
 After clicking on the "Virtual Machine Name", you can name it anything you like. For this tutorial, we’ll name ours "osticket-vm". Select "Create new Resource Group" and click on the virtual machine you just created, and name the resource group "osticket." Choose your region based on your location (e.g., "Central Canada" if you're in Canada).

Scroll down to find the "Image" option and select "Windows 10 Pro, Version 22H2, x64 Gen2." Ensure the virtual machine has at least 2 vCPUs and 16 GB of memory, which you can set in the "Size" option on the same page.

You don’t need to change any default settings on the following pages, but make sure the licensing box is checked on the first page. Once done, proceed to review and create the virtual machine. The system will automatically create a virtual network, so you don’t need to configure that..</p>

<p>
<img src="https://i.imgur.com/G2mmFrE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>3) Connecting to Remote Desktop</h3>

  <p> After all these steps are excecuted, you can then move on to connecting to your virtual machine using "Remote Desktop Connecion". Make sure to grab your "Public IP Adress". (You will find this by clicking on your virtual machine you just created. It should be near the top right of the screen). Make sure your virtual machines Public IP Adress is pasted properly in the Remote Desktop Connection.</p>
</p>

<p>
<img src="https://i.imgur.com/XhlWo4x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/kgPFpyr.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>

<h3>4) Downloading OsTicket</h3>

<p>
 After you have logged into your "Remote Desktop", you can then procceed to download the "OsTicket" File provided here https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD. simply copy this link and paste it into a browser on your Virtual machine. Download and unzip this folder to your desktop.</p>
 
  <p>
<img src="https://i.imgur.com/O6NDJSp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>5) Installing IIS</h3>

<p>
In your virtual machine, go to the bottom left in your windows search bar and type in "Control Panel". With this window open, go to "Uninstall Programs" Under "Programs".  
  <img src="https://i.imgur.com/6h7KEce.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
In the "Programs and Features" window on the left, select the "Turn Windows Features on or off" option.
  <img src="https://i.imgur.com/JVFGkJO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
In this window, click "Internet Information Services" -> "World Wide Web Services" -> "Application Development Features" -> Make sure "CGI" has a checkmark to the left of it. procceed to click ok at the bottom right and wait till the changes are installed.
</p>

<img src="https://i.imgur.com/BiHgIUb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h3>6) Installing Applications</h3>

<p>
After you have installed "IIS", you then open your "osticket" folder and procceed to install php manager. All the settings through this installation are fine to leave as is, so continue through the php manager installation portal.
  <img src="https://i.imgur.com/fddo2dU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>The same goes for the "rewrite_amd64" file in the osticket folder. Simply procceed through that installation portal as well.</p>

  <img src="https://i.imgur.com/ymvr1n0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>After "IIS", "PHP manager" and "rewrite_amd64" are installed, go into your file explorer in your windows shortcut bar on the bottom and in your "Windows (C:)" drive under "This PC" create a "PHP" folder. Once Created, go into your "osticket" folder and extract the "php-7.3.8-nts-Win32-VC15-x86" folder to your "PHP" folder you just created in your "C" drive.</p>

<img src="https://i.imgur.com/jpz5HFD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>Procceed to install these two files as well in the "osticket" folder: "mysql-5.5.62-win32" and "VC_redist.x86". For the "mysql-5.5.62-win32" folder, you will get to a screen that says "Choose Setup Type" select "Typical" and procceed with the rest of the installation.</p>

<img src="https://i.imgur.com/c7Me047.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/jaBVJRT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h3>7) Launching MySQL</h3>

<p>After you have installed "mysql-5.5.62-win32", at the last slide of the installation proccess it will tell you that "My SQL" will launch after installation. Make sure this is checked. Go through the installation proccess until you get to this screen. Choose "Standard Configuration" and procceed.
  
<img src="https://i.imgur.com/OPsmJeU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/></p>

<p> Continue untill you get to a slide that gives you two options, "Modify Security Settings" and "Create an Anonymous Account". Make sure to select "Modify Security Settings" and create a password (make sure to put the password somewhere safe because we will be coming back and using it in this tutorial). 
</p>

 <img src="https://i.imgur.com/JLWIg3w.png" height="60%" width="40%" alt="Disk Sanitization Steps"/>
<br />

<p>After you have created a password, click "Next", "Execute" and "Finish".</p>

<h3>8) Open IIS as an Admin and Registering New PHP</h3>

<p>Go to your search bar on the bottom left of your windows desktop and search for "Internet Information Services (IIS) Manager". Right-click and select "Run as Administrator".</p>

<img src="https://i.imgur.com/8B9O9hP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>Once you have ran IIS as administrator, you will be welcomed to their home screen. Within that home screen, you will see a "PHP Manager" file, click it. You will then be brought to the PHP manager screen. Click "Register New PHP Version" -> "Browse" (Which is This "..." on the right of the search file bar) -> "Windows (C:)" -> "PHP". Once you have clicked "PHP", select the "php.cgi" file within the "PHP" folder. After thats done simply press "OK".</p>

<img src="https://i.imgur.com/8JPpFxz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>After all these steps have been completed, we can then procceed to go back to the "Internet Information Services (IIS) Manager" tab and on the top left, if you right click it, you can select stop and procceed to wait for around a minute before clicking start.</p>

<img src="https://i.imgur.com/ayQDTM0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h3>9) OsTicket Installation</h3>

<p>Once you have completed step 8, you can then open up your "OsTicket Installation File" again and procceed to unzip the compressed osticket folder within the "OsTicket Installation File" folder. Click the "OsTicket" file you just unzipped and you will see an "upload" file in there. Now make sure to open another file explorer by right clicking your folder icon on the bottom of your windows taskbar and clicking "File Explorer". Paste "c:\inetpub\wwwroot" into your quick access bar on the top of your file explorer tab. You will know you have done this right when you see two "iisstart" files in the folder. Click while holding "CTRL" and drag the "upload" file into your "Osticket" folder with the two "iisstart" files. Next, Rename your "upload" file to "osTicket". </p>

<img src="https://i.imgur.com/b6r1o6A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>Once you have completed this you can open up your "Internet Information Services (IIS) Manager" tab and stop the server, wait a minute, then start it again.</p>

<img src="https://i.imgur.com/ayQDTM0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h3>10) Installing Extensions</h3>

<p>Once we have completed osTicket Installation we can now move onto step 10. In step 8, we opened up "Internet Information Services (IIS) Manager" as administrator. We will do this part of the step again. Once we have this open, on the top left within this application you will see and arrow, click that and it will lead you to "Application Pools" and "Sites", click the down arrow on "Sites" and you will see "Default Web Site". Click the down arrow on that and select "osTicket". You will then see at the bottom of this tab "Enable or disable an extension". Proceed to click that and enable "php_imap.dll", "php_intl.dll", and "php_opcache.dll" by right clicking and selecting "Enable".  </p>

<img src="https://i.imgur.com/JOel3zb.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/OqQ8tzH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

<p>You will know you have done the steps correctly when you click on this browser "http://localhost/osTicket/setup/" and everything has a checkmark beside it except "APCu Extension" and  
"Zend OPcache Extension".
</p>

<p>
<img src="https://i.imgur.com/U0AiEq0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3> 11) Renaming Ost file</h3>

<p>
After finishing step 10 correctly, you can then procceed to open another file explorer and pasting this path into the quick access bar- "C:\inetpub\wwwroot\osTicket\include". You will find a file in here called "ost-sampleconfig.php". Rename this file to "ost-config.php" . After renaming the file, right click that file and select "Properties" Then "Security" -> "Advanced", "Disable Inheritance" and "Remove all inherited permissions".
</p>

<p>Next add a new permission by clicking "add" under permission entries</p>

<img src="https://i.imgur.com/NhpANgv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>Go to "Select Principle"</p>

<img src="https://i.imgur.com/aDFMw4J.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>Then above the advanced button, give permission to the admins of your company and press ok but, in this tutorial, I will be giving permission to "everyone"</p>

<img src="https://i.imgur.com/oSBN2wB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>Make sure to select what permissions your employees/admins should have. In this tutorial, I will be selecting "Full Control".</p>

<img src="https://i.imgur.com/H4xlPjU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>Once all this is done, you can make sure to press "apply" and then "ok" on the bottom right of the "permissions entries" tab and then "ok" for the last tab.</p>

<img src="https://i.imgur.com/QUcZ2PJ.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

<h3> 12) Creating OsTicket Login Info</h3>

<p> After you have succesfully given admin permissions, you can then jump back onto the OsTicket Installer browser here "http://localhost/osTicket/setup/" to create your help desk account. (Note - When you are creating the "Admin User" Account make sure the email is different from the "Help Desk User" email).</p>

<h3> 13) Setting up HeidiSQL</h3>

<p>When you have completed the "Help Desk" and "Admin User" accounts, you will see a third column called "Database Settings". For this section we will have to go back to the "Os-Ticket Installation" folder to install the "HeidiSQL" file. </p>

<img src="https://i.imgur.com/vZwaUxl.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

<p>Procceed through the installation proccess until you get to the end where you need to make sure that the "Launch HeidiSQL" option has been checked.</p>

<img src="https://i.imgur.com/Wg2UZWR.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

<p>Once you press "Finish", the HeidiSQL App will laucnh and you will be prompt with an updates page. You can press skip to get to the next part.</p>

<p>On the "Heidi Session Manager" page on the bottom left you will see a "New" button. Click this button and type in the password we saved in step 7 (told you we would be coming back to it). Once you have punched in the password, you can click the "Open" button on the bottom of this page. </p>

<img src="https://i.imgur.com/zIlqQ7K.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

<p>This will then bring you to a page called "Unnamed". On this page you will need to right click the "Unnamed" button on the top left -> "Create New" -> Then "Database" </p>

<img src="https://i.imgur.com/X0a7wRq.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

<p>In order for this file to properly register in the database, you will need to make sure that the "Name" is "osTicket". When you have properly typed "osTicket" into the name text box, you can then click "Ok"</p>

<img src="https://i.imgur.com/RDwefUe.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

<p>Once this is done, you can then go back to the "Database Settings" Column on the "Os-Ticket Installer" browser and Type in your "MySQL Database" (osTicket), Username and password (password from step 7). Once you have typed everything in correctly you can click "Install" and you have finally installed everything you need for os-ticket to work on your remote desktop!</p>

<img src="https://i.imgur.com/M7SEqAZ.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

<h4>Congratulations!</h4>

<h3>Admin User Link/End-User Link</h3>

<p> This link will direct you to the "Admin User" login where you can login using your admin password created earlier: "http://localhost/osTicket/scp/login.php". This next link will be for End-Users: "http://localhost/osTicket/"</p>

<br />
