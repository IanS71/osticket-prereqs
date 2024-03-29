<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. This demonstration starts after creating a virtual machine in Microsoft Azure and connecting through remote desktop.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- PHP Manager for IIS zip
- Rewrite Module zip 
- PHP 7.3.8 zip file
- VC_redist.x86.exe. zip 
- MySQL 5.5.62 file
- osTicket-v1.15.8.zipz
- HeidiSQL

<h2>Installation Step 1 - Internet Information Services  (IIS)</h2>

<p>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1095988353998000148/image.png"/>
</p>
<p>
My first step is to open the application "Turn Windows Features on and off" to enable Internet Information Services and CGI.
<p>
<h2>Multi-file installation</h2>
<p>

From the pre-requisite installation files, I downloaded PHP Manager for IIS and Rewrite Module. I created the directory C:\PHP and unzipped the contents of PHP 7.3.8 inside. Now I can continue to successfully install VC_redist.x86.exe and MySQL 5.5.62.
<br />
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1095996534698541177/image.png"/>
<p>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1095990942491750481/image.png"/>
<p>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1095995114838577242/image.png"/>
<p>
</p>
I downloaded and ran a typical SQL installation. For this demonstration, I'll use root as my username and a simple password. Execute MySQL Server Instance Configuration and close.
<p>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1095997028431052848/image.png"/>
</p>
<p>
<h2>PHP IIS registration</h2>
<p>
The next step is to open up Internet Information Services as an "Administrator". Open the PHP and register the C:\PHP folder that was set up prior. Reload and restart the server to apply the change that was made. 
</p>
<br />

<p>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1095998038218113034/image.png"/>
</p>
<h2>osTicket installation</h2>
<p>
I will download and install the osTicket Zip file. Extract and copy the upload folder into the c:\inetpub\wwwroot and rename it to "osTicket".
</p>
<br />

<img src="https://cdn.discordapp.com/attachments/858652485262639115/1095999344915779606/image.png"/>
<p>
</p>
<br />

Now osTicket should be recognized by Windows, I'll open up IIS and scroll down to the osTicket folder and hit "browse 80" on the right.
<p>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1096000241678950400/image.png"/>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1096000426433843320/image.png"/>
<p>
To smoothen out the osTicket experience, I enabled these extensions inside of the IIS application:
</p>
 - php_imap.dll
 - php_intl.dll
 - php_opcache 
<p>
</p>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1096000849957900318/image.png"/>
<p>
<p>
</p>
 I renamed: > C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php To: > C:\inetpub\wwwroot\osTicket\include\ost-config.php and configured the properties. I made sure to disable all inheritances and add a permission named "Everyone" for ease of installation. 
<p>
</p>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1096002299027017788/image.png"/>
<p>
<h2>HeidiSQL</h2>
</p>
I downloaded and installed HeidiSQL. For this demonstration, I'll use the username "root" and a simple password. Now to create a database called "osTicket"
<p>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1096003610598441000/image.png"/>
<p>
<p>

I browsed the helpdesk local page to continue the setup and plugged in my made-up credentials. I used the HeidiSQL database credentials to fill out the Database settings portion.
<p>
<img src="https://cdn.discordapp.com/attachments/858652485262639115/1096003887871311912/image.png"/>
<p>
<h2>Completion and cleanup steps</h2>
<p>
Congratulations, the setup for osTicket is complete. For the final clean up I deleted the osTicket's "setup" file and changed "ost-config" back to read only in permissions.

<img src="https://cdn.discordapp.com/attachments/858652485262639115/1096004142331338792/image.png"/>
