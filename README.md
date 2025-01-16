# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Installation</h1>
This tutorial outlines the installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)



<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/a9a45fd3-612e-484d-9c75-67d17495c67e)

In order to install OS Ticket system, you will first need to create a VM (virtual machine). In the resource line, type in a group to put it under. You can use whatever you like. Then name the VM and create a user and password. Be sure to write this down and remember for later. Also make sure the size has at least 2 vcpus. Lastly make sure the image is Windows 10 otherwise it will not run. Finally check the licensing box at the bottom and click create. 

![image](https://github.com/user-attachments/assets/aca8038e-82a9-4722-bda2-09774ec54156)

<p>
To use the VM you need to pull up Remote desktop and copy the public IP address and paste it to the Remote Desktop. Also make sure you put in the credentials (user name and password) you created earlier. Then click connect, then yes and it should load the VM, might take a bit. Once its loaded say no to all the icons on the screen and click accept. ALso you DON'T need to sync your data since this is just a practice desktop to play around with. You will end up deleting it once your finished.
</p>
<br />

<p>
  
![image](https://github.com/user-attachments/assets/e67e6acc-5b73-4d10-944b-a2169ff9cb68)

</p>
<p>
To download os ticket you will need to go to osticket.com and click the self-hosted tab on the top, then make sure you click the free version to download and choose you language. Just keep clicking next until the download starts. After that open the file that downloaded in the upper right hand corner. After that, go to control panel, click programs, uninstall programs, turn windows features on or off. Look for Internet Information Services (IIS), check the bos and click the plus icon, world wide web services, application development features, find CGI, check the box and click ok
</p>
<br />

![image](https://github.com/user-attachments/assets/e43434cb-ba1e-4095-818e-4980e11ea92b)
From the os ticket folder, install both PHP manager and rewrite_amd64_en_US. Next you will need to create a new folder on the C: drive and name it PHP, once that is created go ahead and unzip or extract the php.7.3.8 folder and make sure it goes to the new folder on the C: drive, browse if you need to. Go ahead and install VC_redist.x86 and mysql, click typical, keep clicking next until you reach the root password. Make sure you use root for both (VERY IMPORTANT), click execute and finish

![image](https://github.com/user-attachments/assets/144fec46-6aca-45a4-80df-a8b4177a5dcc)
Opem IIS as an admin (right click and run as administrator), open PHP manager, click register new PHP version, click the three dots and find the C:PHP folder that was created earlier, click php-cgi and ok. Go back to the IIS home page and on the right side click stop than start.

![image](https://github.com/user-attachments/assets/c6216aba-4981-4107-ac4e-52fe17224cd6)
From the osticket install folder, extract the osTIcket-v1.15.8 and type in the following exactly c:\inetpup\wwwwroot, click next and it might take awhile to download. Once it has finished, rename the upload folder in the wwwwroot to osTicket (check for spelling and capitalize the T, also make sure there is no spaces). Next open IIS in the left column, click the down arrow, then again for sites, then for default web site. Click osTicket and look on the right column click browse.80 and it should open in the web browser. Go back to PHP manager under IIS, click PHP extentions click enable/disable and extension, then enable the following php_imap, php_intel, and finally php_opcache. Refresh the site and you should notice that all but the last two have a green check mark next to them

![image](https://github.com/user-attachments/assets/72297f3a-438e-43ae-88bd-3e67c7efdcf8)
Go to C: > inetpub > wwwroot > osticket > include and scroll down and find ost-sampleconfig.php and rename it ost-config.php (just erase the sample part). Next right click that same file and click properties, security tab, click advanced, disable inheritance, removea all permissions. NOTE THAT THIS IS ONLY FOR PRACTICE AND SHOULD NOT BE USED IF YOU PLAN ON MAKING YOUR OWN FOR A BUSINESS. Then click add, select principal, type everyone, click check names, select the full control box, hit apply, and lastly ok. The final thing you need to do is install HeidiSQL on the os ticket file folder, open HeidiSQL and create a new root session (located at the bottom). Just click next until you see it. Make sure you use root for both user and password otherwise it will not work. Connect to the session, right click the dolphin icon and create new database then type in osTicket (this is also very important)


![image](https://github.com/user-attachments/assets/973158ce-ed19-4247-a8e9-546f627ffe55)
If done correctly once you click on continue on the OsTicket site it should look like this. If so just fill in the information. Remember your SQL user and password are root and you will need to create two emails, they do not need to be actual emails just type whatever you like
