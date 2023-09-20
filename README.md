<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
- Azure VM running Windows 10

<h2>Installation Steps</h2>


![iis](https://github.com/NickAumer/osticket-prereqs/assets/145170622/6f7a9814-52ea-4fd8-a32c-c78de9775d58)


<p>
Install/Enable IIS through windows features. To do this hit the windows key + r, in the run dialoge box type in control and press enter. Click on Programs and then Turn Windows features on or off. Check the boxes as shown above.
</p>
<br />

<p>
Download and install the following files from the Installation Files
1. PHP Manager for IIS
2. ReWrite Module
Now create the directory C:\PHP
Download PHP 3.7.8, right-click the .zip file and extract. Copy and paste the extracted folder to the directory we just created. The PHP folder should look as pictured below.

![Screen Shot 2023-09-15 at 10 56 46 PM](https://github.com/NickAumer/osticket-prereqs/assets/145170622/f03707f4-4b1d-4e28-bb99-08a527587ab9)


Download and install VC_redist and MySQL 5.5.62 from the installation files. 
**MySQL configuration**
- Typical Setup
- Post-install launch configuration wizard
- Standard Configuration
- Password 1

 Hit windows key and type in IIS, right-click and open as administrator. Go into the PHP manager and click Register new PHP and use the PHP directory we created earlier as the new PHP. Once that's done go back to the main IIS page and restart the server. Once restarted download osTicket from the installation folder. Extract via right click and this time we're going to go into the extracted directory and copy the upload folder to C:\initpub\wwwroot
 Once copied rename the upload folder to osTicket and restart the IIS server one more time. If done correctly you should see osTicket on the left panel of IIS under sites > default sites > osTicket. Select osTicket and then enter the PHP manager again, click “Enable or disable an extension" and enable the following 
 - php_imap.dll
 - php_intl.dll
 - php_opcache.dll

Now go to C:\inetpub\wwwroot\osTicket\include and rename ost-sampleconfig.php to ost-config.php
Change permissions to Allow Everyone > All


In IIS click osTicket under default sites and then on the right panel of IIS click browse :80 and click continue, this is where we will name it "Helpdesk,etc." and set the email for where customer e-mails will go.

The final download, download and install Heidi MySQL from the installation files. All thats left to do now is run MySQL and make a new session. Make sure you set the username and password of the session to match up to the MySQL Username and password settings in osTicket. Once the session is made make a new database via right-click and make sure this matches to what you set MySQL database in osTicket and click Install Now!

Assuming you had no errors you can use the following link to go to your help desk login http://localhost/osTicket/scp/login.php
and customers side would be http://localhost/osTicket/

For post-installation cleanup delete C:\inetpub\wwwroot\osTicket\setup
and set the C:\inetpub\wwwroot\osTicket\include\ost-config.php file to read-only permissions. That's it you've successfully installed osTicket.

## CONGRATS!
 
</p>
<br />
