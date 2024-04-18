
<img width="950" alt="Screenshot 2024-04-17 at 11 02 17 AM" src="https://github.com/BAHIIZI/My-Project/assets/164538571/3a38134c-aa35-4b6e-adcd-f6b82063d163">


<p align="center">

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This project outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [How to Deploy on-premises Active Directory within Azure Compute][
](https://drive.google.com/file/d/14BVYK5MIZwo5T-mQINSW7SfbO_uqqOPP/view?usp=share_link)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

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
Creating Windows server named "DC-1" and Windows 10 named "Client-1" in Azure. Change the IP address of DC-1 from dynamic to static so that it does not change. While creating "Client-1" make sure the Virtual Network of both machines is the same. 
  
![image](https://github.com/BAHIIZI/My-Project/assets/164538571/2bde0349-ad2b-4f18-a70d-8621e3c4db24)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/39fe3e5b-dabf-4ef7-a652-afacfa4a1075)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/e3549006-0b0e-4f40-aef1-f2ad893e8520)
</p>
<br />

Install active directory domain services. Open Server manager and add roles and features. check Active Directory Domain Services and features will be added. At the top right corner click promote this server to a domain controller, add a new forest and then install after all prerequisite checks have passed successfully. 
<p>
  
![image](https://github.com/BAHIIZI/My-Project/assets/164538571/0a67410a-e2b0-4dde-b233-88ee7cbed0b7)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/2e2e8707-8cf9-4eaf-a5d0-fa63dd33e412)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/125f8d4c-99ae-4e39-824b-906428e32cd0)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/af1042f6-8b77-4468-a5af-86b675ebace3)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/e2756082-5e72-4dba-8a37-3cb262cd7e1f)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/cc44ef99-d6da-4dd4-95b1-cf24741e40d8)
  

Create an Admin "mike_admin" and loginto DC-1 as an Admin.
<p>
  
![image](https://github.com/BAHIIZI/My-Project/assets/164538571/a7b47ce1-96c8-4366-bdf6-162faf5f3468)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/bd3db9b2-1467-4e77-8c41-496fac516dff)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/2e3ad680-4303-4159-a4ef-6f49d7db9022)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/2ca1bf2a-f470-454d-94da-e9acac9f0de5)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/14e37240-4264-4161-ae33-fd39786d229c)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/98bd8da8-a77f-40fc-b7de-0765f154f6e7)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/9fd4a7c4-47e0-4198-9be4-2006944e652e)

![image](https://github.com/BAHIIZI/My-Project/assets/164538571/861f111c-abdd-4aac-a7a7-4179a9721f8b)
</p>
<p>

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
