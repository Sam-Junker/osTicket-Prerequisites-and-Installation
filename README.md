<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11</b> (21H2)

<h2>List of Prerequisites</h2>

- Windows VM
- IIS
- SQL database
- Required PHP Extensions
- Item 5

<h2>Creating VM for osTicket download</h2>
First step is to create a resource group in Azure. To do this we open azure and go to the resource groups tab, and then select the +Create button. The window below will come up and you can create your group name making sure you have the correct subscription selected then select "Create" 
<p>
<p> 
<img width="662" height="471" alt="osTicket-1-resource group" src="https://github.com/user-attachments/assets/9ced6679-8888-44e4-9474-4266d11c74f2" />
</p>
<p>
From here you will need to create the Virtual Machine "VM." The steps to do this are:
  1) Open the VM tab in Azure.<p>
  2)"create"<p>
  3) Select Subscription and Resource Group<p>
  4) create VM name and select region. (I am using East US 2)<p>
  5) select the image ( I am using Windows 11 Pro) and select a Size.<p>
  6) setup username and password<p>
  
<img width="532" height="742" alt="osTicket-2-VM" src="https://github.com/user-attachments/assets/11f4e437-f1b3-4a49-9edb-0cd2a668e8aa" />
</p>
<p>
1) From here, Open the VM through "remote desktop connections" </p>
2) For this you will need the Public IP address of the VM we just created. </p>
3) In Azure open the VM tab and select the VM we created and under "networking" we can find the Public IP address. </p>
4) Once we have the IP address open remote desktop connections (home search bar type in Remote desktop) and enter in the IP address. The username and password will be the ones set earlier when we created the VM.</p>

<img width="550" height="310" alt="osTicket-3-remote desktop" src="https://github.com/user-attachments/assets/20fe35d6-8bb6-42a2-b1ee-0caf0fe8cc4a" />
</p>
<p>
<h2>Downloading of osTicket</h2>
</p>
Many of these steps are specific to osTicket, it uses sever specific files and its own SQL database. These can all be found on their website in the downloads.</p>
</p>

<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket Part 1](https://youtu.be/5z-nGB86tYQ)  </p>
1) Download the .zip file provided for osTicket. If there is not one provided it is available on the osTicket website.</p>
2) place the .zip folder on the desktop and right click select expand all.</p>
3) Remove the .zip folder as we will not need it any more.</p>
4) enable IIS with CGI. Control panel, (turn windows features on or off, check boxes for Internet Information Services, and CGI)</p>
5) Next we need to install the PHP manager from the installation folder.</p>
6) install the rewrite module from the installation folder</p>
7) Create "PHP" folder inside the C drive on the computer.</p>
8) Extract "php-7.3.8-nts-Win32-VC15-x86" to C:\PHP.</p>
9) Install "VC_redist.x86" from the installation folder</p>
10) Install "mysql-5.5.62-win32" from the installation folder</p>
11) Open IIS as admin and register php inside IIS.</p>
12) Install osTicket "osTicket-v1.15.8" from installation folder.</p>
13) Open osTicket from IIS, "sites" "default web sites" "osTicket" select browse*:80(http) on right side menu.</p>
14) Go back into IIS with osTicket site selected open PHP manager. Then select enable or disable an extension. Then enable Enable:</p>
  php_imap.dll</p>
  Enable: php_intl.dll</p>
  Enable: php_opcache.dll</p>
15) Rename "ost-sampleconfig.php" in "C:\inetpub\wwwroot\osTicket\include" to "ost-config.php"</p>
16) Once the name is changed the security will need changed to allow read and write access to the correct users. (right click, properties, security, advanced, "list group or user" apply)</p>
17) Next setup the helpdesk name and admin user on web browser. </p>
<img width="965" height="976" alt="osTicket-4-account setup" src="https://github.com/user-attachments/assets/f1011d97-bb1b-4ab8-8f23-2d162ab3fed5" />

18) Now we will download Heidi from the install folder. This is the database that osTicket will use. Once downloaded create the database "osTicket" using the credentials from MySQL user we created earlier. </p>
19) enter this database information into the web browser setup and press install now.</p>

Congratulations! you have now installed and setup osTicket!</p>
  
  
