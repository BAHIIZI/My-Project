
<img width="950" alt="Screenshot 2024-04-17 at 11 02 17 AM" src="https://github.com/BAHIIZI/My-Project/assets/164538571/3a38134c-aa35-4b6e-adcd-f6b82063d163">


<p align="center">

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This project outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create two virtual machines (Windows server and windows 10 machine) in Azure.
- Install Active Directory Domain Services.
- Create an admin in Active Directory.
- Join Virtual machine ("Client-1") to the Domain ("kaba.com").

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

Joining "Client-1" to "DC-1", you have to make sure that the DNS of "Client-1" is the same as DC-1 IP address. The image below shows the DNS of Client-1 which is clearly different and i have to change it to 10.0.0.4 which is the IP address of DC-1.

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/57711bdf-714c-46cc-8b1a-1b86ac96c6cf)

Go to Client-1 in Azure, and select network settings.

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/7d2fa0f4-da45-450e-843c-16f3ecd306c2)

Click on the network interface and you will see DNS Servers.

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/9e2750fa-6c08-4269-9f45-bb8f1c477024)

Click DNS Servers and select custom. 

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/799a932e-5032-450b-b69f-e9607f27c7c2)

Enter DC-1 IP address just like in the diagram below.

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/8b886635-2e68-4fd2-926c-ed954dd3669d)

Then restart Client-1 in Azure and then log back as the original user.

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/165a37b6-e0a5-426b-99e0-de6c6211fa98)

As soon as Client-1 opens, go to command prompt and type "ipconfig /all" command to check if the changes to the DNS were made.

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/1c2ddc52-e8e8-4b9f-b24b-646c237c2320)

After confirming DNS, go to systems setting and click 'rename this computer' and then you will have to fill in the domain, then an option box will show requiring to enter a user name and password of an admin user that has access to DC-1. Client one will automatically restart.

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/5ab879d0-a8b0-4a7a-bd85-1f723f7b671b)

You can now try logging back into client-1 as an Admin. The image below shows that I have been able to loginto Client-1 successfully as an Admin.

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/504ead81-b3a3-4944-b659-d74d0f013172)
