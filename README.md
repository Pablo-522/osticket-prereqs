<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" height="75%" width="100%"alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This is my tutorial on the prerequisites and installation process for OsTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating System Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create Virtual Machine in Azure
- Install Web Platform Installer
- Install osTicket v1.15.8
- Install HeidiSQL

<h2>Installation Steps</h2>
<h3 align="center">Create Virutal Machine in Azure</h3>
<br />
<p>
<h3 align="center">The first step, we'll start by creating a Resource Group inside Azure.</h3>
<br />
</p>
<p>
	<img src="https://i.imgur.com/fGDNW6s.png" height="75%" width="100%" alt="Resource Group"/>
</p>
<p>
<h3 align="center">Now, we can create a Windows 10 Virtual Machine. The username and password,  can be anything however it is important to remember as we'll be using this info to remote in with our main computer. When creating the Virtual Machine, allow Azure to create a new Virtual Network:</h3>
<br />
</p>
<p>
	<img src="https://i.imgur.com/ZCpM5gv.png" height="75%" width="100%" alt="Windows Virutal Machine"/>
</p>
<br />
<br />
<h3 align="center">Next, we'll open our Remote Desktop Connection app on your computer and connect to your Virtual Machine that was created in Azure. If you're asked to sign into your main account (your computer) click on "More Options".</h3>
<br />
<p>
	<img src="https://i.imgur.com/1zaKYCE.png" height="75%" width="100%" alt="Remote Desktop"/>
</p>
<br />
<br />
<h3 align="center">Now we need to install / Enable IIS in Windows. Go to your Search Bar > Type "Control Panel" > Click "Programs" > "Turn Windows features on or off" > Scroll down to "Internet Information Services (IIS).</h3>
<br />
<p>
	<img src="https://i.imgur.com/P2B5nzO.png" height="75%" width="100%" alt="Enable IIS in Windows"/>
</p>
<br />
<br />
<h3 align="center">Download and install PHP Manager for IIS </h3>
<br />
<p>
	<img src="https://i.imgur.com/b7y5X5f.png" height="75%" width="100%" alt="Enable IIS in Windows"/>
</p>
<p>
  Download and install Rewrite Module
</p>
<p>
	<img src="https://i.imgur.com/FMf6LHA.png" height="75%" width="100%" alt="MySQL 5.5"/>
</p>
<br />
<p>
  Create PHP Directory (C:\PHP
</p>
  <p>
	<img src="https://i.imgur.com/HTYGMBA.png" height="75%" width="100%" alt="Credentials"/>
</p>
<p>
  From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
</p>
<p>
	<img src="https://i.imgur.com/FMf6LHA.png" height="75%" width="100%" alt="PHP"/>
</p>
<p>
  Fix any failures if required. 
</p>
<p>
  Install Microsoft Visual C++ 2009 Redistributable Package (if necessary).
</p>

<br />
<br />
<h3 align="center">Install osTicket v1.15.8</h3>
<br />
<p>
  Download osTicket (download from within lab files: link).
</p>
<p>
	Extract and copy the “upload” folder INTO c:\inetpub\wwwroot:
</p>
	<img src="https://i.imgur.com/MAGJcBS.png" height="75%" width="100%" alt="PHP Manager"/>	
<p>
	Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”:
</p>
<p>
	<img src="https://i.imgur.com/UF9RJWb.png" height="75%" width="100%" alt="rename to osTicket"/>
</p>
<br />
<br />
<h3 align="center">Reload IIS (Open IIS, Stop and Start the server)</h3>
<br />
<p>
	Go to sites -> Default -> osTicket:
</p>
<p>
	<img src="https://i.imgur.com/Lnd8dwz.png" height="75%" width="100%" alt="default osTicket"/>
</p>
<p>
	On the right, click “Browse *:80”:
</p>
<p>
	<img src="https://i.imgur.com/HYKCtz8.png" height="75%" width="100%" alt="port 80"/>
</p>
<br />
<br />
<h3 align="center">Enable Extensions in IIS: Note that some extensions are not enabled</h3>
<br />
<p>
	Go back to IIS, sites -> Default -> osTicket.
</p>
<p>
	Double-click PHP Manager:
</p>
<p>
	<img src="https://i.imgur.com/h1OSwP4.png" height="75%" width="100%" alt="PHP Manager"/>
</p>
<p>
	Click “Enable or disable an extension”.
</p>
<p>
	Enable: php_imap.dll.
</p>
<p>
	Enable: php_intl.dll.
</p>
<p>
	Enable: php_opcache.dll:
</p>
<p>
	<img src="https://i.imgur.com/T4eIu5n.png" height="75%" width="100%" alt="enablephpsettings"/>
</p>
<br />
<br />
<h3 align="center">Refresh the osTicket site in your browser, observe the changes</h3>
<br />
<p>
	<img src="https://i.imgur.com/teBdqwo.png" height="75%" width="100%" alt="osTicket change"/>
</p>
<br />
<br />
<h3 align="center">Rename</h3>
<br />
<p>
	From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php.
</p>
<p>
	To: C:\inetpub\wwwroot\osTicket\include\ost-config.php:
</p>
<p>
	<img src="https://i.imgur.com/9dziUQ2.png" height="75%" width="100%" alt="ost-config"/>
</p>
<br />
<br />
<h3 align="center">Assign Permissions: ost-config.php</h3>
<br />
<p>
	Disable inheritance -> Remove All:
</p>
<p>
	<img src="https://i.imgur.com/zCH9C1t.png" height="75%" width="100%" alt="disable inheritance"/>
</p>
<p>
	New Permissions -> Everyone -> All:
</p>
<p>
	<img src="https://i.imgur.com/8fwZcjC.png" height="75%" width="100%" alt="new permissions"/>
</p>
<p>
	<img src="https://i.imgur.com/vfqh6Oo.png" height="75%" width="100%" alt="new permissions - all"/>
</p>
<br />
<br />
<h3 align="center">Continue Setting up osTicket in the browser (click Continue)</h3>
<br />
<p>
	Name Helpdesk.
</p>
<p>
	Default email (receives email from customers):
</p>
<p>
	<img src="https://i.imgur.com/teBdqwo.png" height="75%" width="100%" alt="continue osTicket setup"/>
</p>
<br />
<br />
<h3 align="center">Download and Install HeidiSQL</h3>
<br />
<p>
	<img src="https://i.imgur.com/sLgaVMe.png" height="75%" width="100%" alt="download HeidiSQL"/>
</p>
<p>
	Create a new session, root/Password1.
</p>
<p>
	Connect to the session:
</p>
<p>
	<img src="https://i.imgur.com/1VMhCjt.png" height="75%" width="100%" alt="create sessions"/>
</p>
<p>
	Create a database called “osTicket”:
</p>
<p>
	<img src="https://i.imgur.com/NgVOxVy.png" height="75%" width="100%" alt="create database"/>
</p>
<br />
<br />
<h3 align="center">Continue Setting up osTicket in the browser</h3>
<br />
<p>MySQL Database: osTicket</p>
<p>
	MySQL Username: root
</p>
<p>
	MySQL Password: Password1:
</p>
<p>
	<img src="https://i.imgur.com/hDjoXVg.png" height="75%" width="100%" alt="setting up osTicket cont'd"/>
</p>
<p>Click “Install Now!”</p>
<p>And there we go! It should be up and running with no errors!</hp>
<p>
	<img src="https://i.imgur.com/wj2Paps.png" height="75%" width="100%" alt="installation complete"/>
</p>
<br />
<br />
<h3 align="center">Clean up</h3>
<br />
<p>
	Delete: C:\inetpub\wwwroot\osTicket\setup:
</p>
<p>
	<img src="https://i.imgur.com/QG9tLQw.png" height="75%" width="100%" alt="clean up"/>
</p>
<p>
	Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php:
</p>
<p>
	<img src="https://i.imgur.com/uTn7HNT.png" height="75%" width="100%" alt="permissions"/>
</p>
<br />
<br />
<h3 align="center">Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php)</h3>
<br />
<p>
	<img src="https://i.imgur.com/mJVaOvB.png" height="75%" width="100%" alt="admin panel"/>
</p>
<br />
<br />
<p>
	And there you have it! I hope this tutorial helped you with installing osTicket.
</p>
<p>
	And now we can practice having your own mock help desk locally to prepare you for a postion in a help desk or IT support position.
</p>
