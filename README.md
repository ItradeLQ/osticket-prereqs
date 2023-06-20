
</p>
<br />
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

- Azure Tenant 
- Subscription
- Resourse group 
- Virtual Machine
- Virtual Network
- Subnet

<h2>Installation Steps</h2>

<p>
<a href="https://imgur.com/nC6D8XS"><img src="https://i.imgur.com/nC6D8XS.png" title="source: imgur.com" /></a>
  
<a href="https://imgur.com/xatqD5Z"><img src="https://i.imgur.com/xatqD5Z.png" title="source: imgur.com" /></a>
</p>
<p>
Next, create a Resource Group and Virtual Machine in Azure 
</p>
<br />

<p>
<a href="https://imgur.com/u3GO7tj"><img src="https://i.imgur.com/u3GO7tj.png" title="source: imgur.com" /></a>
  

</p>
<p>
Both Resoruce Group and Virtual Machine should be created in the same region. In the image selection box select the windows 10 virtual machine with 4 vCPUs | 16 GiB. Make a username and password which will be used to connect the remote desktop in the following steps. When creating a virtual machine, allow it to create a new virtual network (Vnet).
</p>
<br />
<p>
<a href="https://imgur.com/F9bqCqb"><img src="https://i.imgur.com/F9bqCqb.png" title="source: imgur.com" /></a>
</p>
<p>
Now that the virtual machine has been created, copy the public IP address of the virtual machine and open the remote desktop. Here you will paste the public IP address and then enter your username and password from the previous step.
</p>
<br />

<p>
<a href="https://imgur.com/yHZumJf"><img src="https://i.imgur.com/yHZumJf.png" title="source: imgur.com" /></a>
</p>
<p>
Now that you are in, you have to Install and enable Internet Information Services(IIS). This is a web server that runs on the windows operating system. To do this click start and go to the control panel>programs>turn windows features on or off. Turn on IIS and expand it, then go to the world wide web Service and expand it> expand the application developer> CGI (because CGI is what lets us install the PHP manager) 
</p>
<br />

<p>
<a href="https://imgur.com/Oy7oAJQ"><img src="https://i.imgur.com/Oy7oAJQ.png?1" title="source: imgur.com" /></a>
</p>
<p>
This is the Installation File.
</p>
<br />

<p>
<a href="https://imgur.com/EjaT9Jf"><img src="https://i.imgur.com/EjaT9Jf.png?1" title="source: imgur.com" /></a>
</p>
<p>
From the installation file download the PHP manager for IIS. 
In osTicket PHP is the back-end web programming language.
</p>
<br />

<p>
<a href="https://imgur.com/UQ90VD7"><img src="https://i.imgur.com/UQ90VD7.png" title="source: imgur.com" /></a>
</p>
<p>
From the installation file download the rewrite module.
</p>
<br />

<p>
<a href="https://imgur.com/83U8Maw"><img src="https://i.imgur.com/83U8Maw.png" title="source: imgur.com" /></a>
</p>
<p>
Create the directory C:\PHP. Go to windows explorer> Windows (C:)>create a new folder> name PHP. 
</p>
<br />

<p>
<a href="https://imgur.com/v52TKvC"><img src="https://i.imgur.com/v52TKvC.png" title="source: imgur.com" /></a>
</p>
<p>
From the Installation file download PHP 7.3.8 and unzip the content into C:\PHP.
Extract the downloaded file>Windows (C:)>PHP folder>Extract all.
</p>
<br />

<p>
<img src="https://i.imgur.com/XGawRaH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the installation file download VC redistX86.exe.
</p>
<br />

<p>
<img src="https://i.imgur.com/dFSffoX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Q3MpuUD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Installation file download MYSQL.5.5.62.
  
Open it and agree. Select the typical setup and install. Make sure that the box is marked before Installing.  
  
Select the standard configuration> user name is root and password is Password1> execute>finish.
</p>
<br />

<p>
<a href="https://imgur.com/NT9f5UY"><img src="https://i.imgur.com/NT9f5UY.png" title="source: imgur.com" /></a>
</p>
<p>
Open IIS as an administrator
</p>
<br />

<p>
<img src="https://i.imgur.com/UdjtoZd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/JRxIs2M.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Register PHP from within IIS. To do this, go to PHP manager>register new PHP version>click the --- on the right>C drive>PHP>Php-cgi>ok.
</p>
<br />

<p>
<img src="https://i.imgur.com/vxkHX7l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now reload IIS. Select the vmosTicket and click restart.
</p>
<br />

<p>
<img src="https://i.imgur.com/gBIAb3e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/2MWizjq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


Download the osTicket from the Installation file folder. Extract and copy “upload” folder to c:\inetpub\wwwroot Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”


Now open another file explorer next to the first. Go to the download folder and copy the upload folder and paste it into c:\inetpub\wwwroot and let it install. Next, rename the folder to osTicket.

  

</p>
<br />

<p>
<img src="https://i.imgur.com/nsSdVnB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Reload the IIS again and then go to sites>Default>osTicket
  
On the right click Browse*:80(http) in the top right of IIS Manager
</p>
<br />

<p>
<a href="https://imgur.com/rp0fWBd"><img src="https://i.imgur.com/rp0fWBd.png" title="source: imgur.com" /></a>
</p>
<p>
If you can see this page, it means the installational process is successful

</p>
<br />

<p>
<a href="https://imgur.com/WLkGDwh"><img src="https://i.imgur.com/WLkGDwh.png" title="source: imgur.com" /></a>
</p>
<p>

Go back to the IIS>sites>Default>osTicket. Double click the PHP manager>enable or disable extension to enable the following extensions.

  
Enable: php_imap.dll
  
  
Enable: php_intl.dll
  
  
Enable: php_opcache.dll
  
  
Refresh the osTicket site in your browser and observe the changes.

</p>
<br />

<p>
<a href="https://imgur.com/lsWwloQ"><img src="https://i.imgur.com/lsWwloQ.png" title="source: imgur.com" /></a>
</p>
<p>

Rename ost-sampleconfig.php to ost-config.php, from: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

  
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

  
</p>
<br />

<p>
<a href="https://imgur.com/T4OqSnm"><img src="https://i.imgur.com/T4OqSnm.png" title="source: imgur.com" /></a>
</p>
<p>

Assign permission to ost-config.php, go to properties>security, and disable inheritance>remove all.

</p>
<br />

<p>
<OS TICKET INSTALL BASIC INSTALLATION IMAGE NEEDED>
</p>
<p>

Click continue in the osTicket browser to continue settings.
  
Name Helpdesk (Kenronishe Help Desk)
  
  
Default email (receives an email from customers)kenronishe@helper.com
  
Set the username and password for logging into OsTicket. 

  
</p>
<br />

<p>
<a href="https://imgur.com/1FRfs6k"><img src="https://i.imgur.com/1FRfs6k.png" title="source: imgur.com" /></a>
</p>
<p>
Download and Install the HeidiSQL from the Installation folder.
</p>
<br />

<p>
<a href="https://imgur.com/gys0POC"><img src="https://i.imgur.com/gys0POC.png" title="source: imgur.com" /></a>
</p>
<p>

Create a new session, root with Password1, and connect to it.
  
</p>
<br />

<p>
<a href="https://imgur.com/UHZJyR0"><img src="https://i.imgur.com/UHZJyR0.png" title="source: imgur.com" /></a>
</p>
<p>
Create a new database called osTicket.
  
Right-click to the unnamed>create new>database> name it osTicket.
</p>
<br />

<p>
<INSERT MISSING IMAGE FOR ADMIN USER OSTICKET>
</p>
<p>
Go to the osTicket page and type root in MYSQL username, Password1 in MYSQL Password, and osTicket in MYSQL Database and click to Install now.
  
</p>
<br />

<p>
<a href="https://imgur.com/s8E3in1"><img src="https://i.imgur.com/s8E3in1.png" title="source: imgur.com" /></a>
</p>
<p>

Congratulations, your setup has been completed successfully!
  
</p>
<br />

<p>
<a href="https://imgur.com/LWV413n"><img src="https://i.imgur.com/LWV413n.png" title="source: imgur.com" /></a>
</p>
<p>
Before we you finish there are some things that need cleaning up.


We need to delete the setup folder. Go to C:\inetpub\wwwroot\osTicket\setup.

  
  
</p>
<br />

<p>
<a href="https://imgur.com/G8NeHF0"><img src="https://i.imgur.com/G8NeHF0.png" title="source: imgur.com" /></a>
</p>
<p>


Go to C:\inetpub\wwwroot\osTicket\include\ost-config.php>properties>security>advanced>everyone>EDIT>and unchecked everything and just leave it to read and execute.

  
</p>
<br />

<p>
<a href="https://imgur.com/KQRFpn1"><img src="https://i.imgur.com/KQRFpn1.png" title="source: imgur.com" /></a>
</p>
<p>
Now you can log in with your username and password. The configuration used: Username: Kenronishe and PW: Password1.
</p>
<br />

<p>
<a href="https://imgur.com/YmcpCaD"><img src="https://i.imgur.com/YmcpCaD.png" title="source: imgur.com" /></a>
</p>
<p>
Congratulation, you have completed this tutorial and are inside of your osTicket setup!
</p>
<br />
