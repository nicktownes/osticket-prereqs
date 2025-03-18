<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ###

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Install/Enable IIS (Internet Information Services) in Windows w/CGI
- Install Web-Platform Installer
- Install MySQL and setup username & password
- Install C++ redistributable
- Configure permissions and install osTicket

<h2>Installation Steps</h2>

<p>
<img src="https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2014/07/new-IIS-hero.png?q=50&fit=crop&w=1140&h=&dpr=1.5" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Download the osTicket-Installation-Files.zip and unzip it onto your desktop.

- Install / Enable IIS in Windows WITH CGI
    World Wide Web Services -> Application Development Features -> [X] CGI

- From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

- From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

- Create the directory C:\PHP

- From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

- From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

- From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
    Typical Setup ->
    Launch Configuration Wizard (after install) ->
    Standard Configuration ->
</p>
<br />

<p>
<img src="https://help.intrexx.com/intrexx/silent/en-us/Content/D-Resources/Dialog/webplatform-installer-2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Open IIS as an Admin

- Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Reload IIS (Open IIS, Stop and Start the server)

- Install osTicket v1.15.8
    From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
    Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

- Reload IIS (Open IIS, Stop and Start the server)

- Go to sites -> Default -> osTicket
      On the right, click “Browse *:80”

*Note that some extensions are not enabled

- Go back to IIS, sites -> Default -> osTicket
    Double-click PHP Manager
    Click “Enable or disable an extension”
    Enable: php_imap.dll
    Enable: php_intl.dll
    Enable: php_opcache.dll
    Refresh the osTicket site in your browser, observe the changes

- Rename: ost-config.php
    From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
    To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<br />

<p>
<img src="https://www.rosehosting.com/blog/wp-content/uploads/2022/04/install-osticket-on-almalinux.webp" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Assign Permissions: ost-config.php
    Disable inheritance -> Remove All

- Continue Setting up osTicket in the browser (click Continue)
   Add email to recieve ticket request
  
- From the “osTicket-Installation-Files” folder, install HeidiSQL.
    Open Heidi SQL
    Create a new session
    Connect to the session
    Create a database called “osTicket”

- Continue Setting up osTicket in the browser

- Browse to your help desk login page: http://localhost/osTicket/scp/login.php

- End Users osTicket URL:
    http://localhost/osTicket/ 
</p>
<br />
