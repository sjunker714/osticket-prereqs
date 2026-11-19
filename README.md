<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of osTicket, an open-source help desk ticketing system.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to create a VM with Azure](https://www.youtube.com/watch?v=USBFyDUkviw&t=8s)

- ### [YouTube: How to Install osTicket with Prerequisites](https://www.youtube.com/watch?v=5z-nGB86tYQ)

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
- MYSQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD

<h2>Virtual Machine Creation/h2>

01) The first step I am going to take is to create a new VM within Azure. ***View the video above.
      - I open Azure, go to the Resource Group tab, and select Create a new Resource Group. I am going to use my subscription. (This could be any subscription; in the real world, many companies separate by department or by location)
      - Name the Resource group. Select Create at the bottom of the page.
02) Open the Virtual Machines tab and select Create.
      - I start by making sure I am in the correct subscription for the Resource Group I just created.
      - Select the Resource Group I just created.
      - Name the VM
      - I am going to select East US 2 for the region. (This can be any region; I typically use this one)
      - For the image, I am going to go with Windows 11 Pro. Any size will work for this lab.
      - The next step is creating the admin account login. This can be anything; I am going to use something simple for the lab so I can remember it easily.
      - I am going to leave the inbound ports alone for this lab.
      - I have to select (I confirm) for the licensing, or else it will not let the VM be created.
      - Select Next to move to the next window.
      - Click Next again to go to networking.
      - Click  Next again, as I do not need to adjust anything here.
      - Finally, click Review and create at the bottom, and then click Create at the bottom of the next window.
  The VM is created!


<h2>osTicket installation steps<h2>
   
01) I open the VM I just created using Remote Desktop. Enter the credentials I set up in the VM creation step.
02) I open the link to the download files. This is a compiled folder with everything needed to download osTicket. 
https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD
03) Save the folder to the desktop so it can be easily accessed.
04) Once it is on the desktop, I click "Extract All" (right-click, Extract All) and extract to the desktop. (This will create a new folder on the desktop)
      - I can now delete the original download .zip folder.
05) I now need to turn on Internet Information Services (IIS) and CGI
      - "Turn Windows features on or off": Find Internet Information Services and expand the folder. 
      - "World Wide Web Services": Expand this folder.
      - "CGI": Check the box and select OK
06) Now I need to install the PHP Manager from the osTicket-installation-files folder.
      - Double-click the program
      - Select "Next"
      - Select "I Agree"
      - Select "Install"
07) The next program I need to install is rewrite_amd64_en-US from the osTicket-installation-files folder.
      - Double-click, accept the terms
      - Select "Next" until I get to select "Install". 
08) Next, I need to create a folder in the "C:" drive called "PHP".
      - Open File Explorer, go to This PC
      - Select Windows "C:"
      - Right-click, select "New folder"
      - Name it "PHP".
09) The next step is to unzip the php-7.3.8-nts-Win32-VC15-x86 folder.
      - Right-click "Extract All" and I am going to extract this to the folder I just created, C:/PHP.
10) After that is finished, I am going to download VC_redist_x86 from my osTicket-installation-files folder.
      - Double-click, check the box to agree to the terms, and  click "Install".
11) Once completed, I am going to download mysql-5.5.62-win32 from my osTicket-installation-files folder.
      - Double-click, "Next", check the box to agree to the terms, "Next", select Typical setup, "Next", "Install", "Finish".
      - This opens up a second window; I am going to select a Standard Configuration, then click "Next". 
      - The name will be MySQL, and I will click "Next".
      - Set the password for your SQL account, and select "Next". 
      - In the next window, I am going to select "Execute" and "Finish" once it is completed.
12) The next step is to open IIS as an ADMIN and register the new PHP.
      - Go to the Start menu, then type IIS. Right-click and select "Run as administrator".
      - Double-click PHP Manager, then click "Register new PHP version", browse to C:/PHP that we created, and select the file php-cgi.
      - Restart IIS Manager. Right-click on osTicket on the right-hand side and select "Stop"; right-click osTicket after a few seconds and select "Start". 
13) Once that is restarted, the next step is to extract the osTicket-v1.15.8 folder in the osTicket-installation-files folder. 
      - Right-click "Extract All". This will extract it inside the osTicket-installation-files folder. 
14) Once extracted, I need to move the "upload" folder to C:\inetpub\wwwroot. Then rename the folder to "osTicket".
15) Once the "osTicket" folder is created, I am going to restart IIS Manager again, as I did before.
16) After the restart, I am going to start osTicket within IIS.
      - "Sites"
      - "osTicket"
      - "Browse *:80 (http)" on the left-hand side of the window.
17) Now I need to enable "php_imap.dll," "php_intl.dll", and "php_opcache.dll"
      - Back in IIS select "osTicket"
      - Select "PHP Manager"
      - "Enable or disable an extension"
      - Find "php_imap.dll," "php_intl.dll", and "php_opcache.dll"
      - Right-click and select "Enable" for each one.
