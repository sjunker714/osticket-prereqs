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

1) The first step I am going to take is to create a new VM within Azure. ***View the video above.
   - I open Azure, go to the Resource Group tab, and select Create a new Resource Group. I am going to use my subscription. (This could be any subscription; in the real world, many companies separate by department or by location)
   - Name the Resource group. Select Create at the bottom of the page.
2) Open the Virtual Machines tab and select Create.
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
   -  Finally, click Review and create at the bottom, and then click Create at the bottom of the next window.
  The VM is created!


<h2>osTicket installation steps<h2>
1) I open the VM I just created using Remote Desktop. Enter the credentials I set up in the VM creation step.
