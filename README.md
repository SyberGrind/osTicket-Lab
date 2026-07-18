<img width="588" height="330" alt="WhatsApp Image 2026-07-18 at 15 50 35 000" src="https://github.com/user-attachments/assets/d6498d6d-d046-4121-9f7c-dc6db7354b14" />


# osTicket Help Desk Deployment, Administration & Ticket Lifecycle Lab.

📌Project Overview

This project demonstrates the complete deployment, configuration, and administration of the osTicket Help Desk System on a Microsoft Azure Windows 11 Pro Virtual Machine using Internet Information Services (IIS), PHP, and MySQL.The lab begins by provisioning cloud infrastructure in Azure before installing and configuring all prerequisites required by osTicket. After deploying the application, the environment is configured with custom administrative roles, departments, teams, agents, users, and Service Level Agreements (SLAs). The project concludes by simulating a real-world IT support workflow where an end user submits a support ticket, a help desk administrator assigns it to the appropriate technician, and the assigned agent begins the troubleshooting process.The repository documents the entire deployment from infrastructure creation to ticket management using 146 fully documented screenshots, providing a complete end-to-end demonstration of help desk administration.

⸻

📊 Project Summary

| Category | Details |
|----------|---------|
| **Project** | Complete osTicket Help Desk Deployment, Administration & Ticket Lifecycle Lab |
| **Cloud Platform** | Microsoft Azure |
| **Operating System** | Windows 11 Pro Virtual Machine |
| **Web Server** | Internet Information Services (IIS) |
| **Help Desk Platform** | osTicket v1.15.8 |
| **Database** | MySQL Server 5.5 |
| **Programming Language** | PHP 7.3.8 |
| **Supporting Components** | PHP Manager, CGI, URL Rewrite Module, Microsoft Visual C++ Redistributable |
| **Administrative Tools** | IIS Manager, Windows Features, Remote Desktop (RDP), File Explorer, Microsoft Edge |
| **Key Tasks Completed** | Azure infrastructure deployment, Windows VM provisioning, IIS configuration, PHP integration, MySQL installation, osTicket deployment, Administrator configuration, Role management, Department creation, Team creation, Agent administration, User management, SLA configuration, Ticket creation, Ticket assignment, Ticket lifecycle validation |
| **Documentation** | 146 Step-by-Step Screenshots |
| **Project Status** | ✅ Completed |

⸻

🏗️🏢 Lab Architecture

```text
                         Microsoft Azure
                                │
                  Resource Group: Tickets
                                │
                      Windows 11 Pro VM
                                │
                    Remote Desktop (RDP)
                                │
        ┌─────────────────────────────────────────┐
        │ Internet Information Services (IIS)     │
        └──────────────────┬──────────────────────┘
                           │
                  PHP Manager + CGI Module
                           │
                     PHP 7.3.8 Runtime
                           │
                    osTicket v1.15.8
                           │
                  MySQL Server 5.5 Database
                           │
      ┌───────────────────────────────────────────────┐
      │           Help Desk Administration            │
      ├───────────────────────────────────────────────┤
      │ • Roles                                       │
      │ • Departments                                │
      │ • Teams                                      │
      │ • Agents                                     │
      │ • End Users                                  │
      │ • Service Level Agreements (SLAs)            │
      └──────────────────┬────────────────────────────┘
                         │
                  Ticket Submission
                         │
                  Ticket Assignment
                         │
                  Agent Investigation
                         │
                  Ticket Resolution
```

⸻

🎯 Objectives

* Deploy a Windows virtual machine in Microsoft Azure
* Configure Internet Information Services (IIS) for hosting PHP applications
* Install PHP and integrate it with IIS using PHP Manager
* Install and configure MySQL Server
* Deploy and configure the osTicket Help Desk application
* Create administrative roles with appropriate permissions
* Configure departments and teams
* Create help desk agents with different permission levels
* Register end users within the help desk system
* Configure Service Level Agreements (SLAs)
* Simulate a real-world support ticket lifecycle from submission to assignment
* Demonstrate enterprise help desk administration practices

⸻

🛠️ Technologies Used

* Microsoft Azure
* Windows 11 Pro
* Internet Information Services (IIS)
* osTicket v1.15.8
* PHP 7.3.8
* MySQL Server 5.5
* PHP Manager
* CGI
* URL Rewrite Module
* Remote Desktop Protocol (RDP)

⸻

🧠 Skills Demonstrated

* Microsoft Azure Administration
* Windows Administration
* IIS Web Server Configuration
* PHP Configuration
* MySQL Database Administration
* osTicket Deployment
* Help Desk Administration
* Role-Based Access Control (RBAC)
* User & Agent Management
* Service Level Agreement (SLA) Configuration
* Ticket Lifecycle Management
* Remote Desktop Administration
* IT Troubleshooting

⸻

## 🔹 Phase 1. Azure Infrastructure & VM Setup.
In this phase, I created the Azure environment required for the lab by provisioning a Resource Group and deploying a Windows 11 Pro virtual machine. After the deployment completed, I established a Remote Desktop connection and confirmed the virtual machine was ready for the osTicket installation.

⸻
>
<br>

* **Step 1: I launched the Azure Resource Group portal.**
<br>
<img width="1366" height="768" alt="Step 1  Launch of Resource Group Portal" src="https://github.com/user-attachments/assets/b1814483-62d5-4e5d-995c-3e511ae4fcd7" />
>
<br>

* **Step 2: I named the resource group Tickets and selected the East Asia region.**
<br>
<img width="1366" height="768" alt="Step 2  Naming the reasource group Tickets   Selecting Zone East Asia" src="https://github.com/user-attachments/assets/ac9dbd3c-7003-4c31-aa9b-3f67fed2c207" />
>
<br>

* **Step 3: I created the Azure Resource Group.**
<br>
<img width="1366" height="768" alt="Step 3  Creating Resource Group" src="https://github.com/user-attachments/assets/0f17410e-642c-44c7-8db5-b9bd806f4cd5" />
>
<br>

* **Step 4: Resource Group successfully provisioned.**
<br>
<img width="1366" height="768" alt="Step 4  Successfull Creation of Reasouce Group" src="https://github.com/user-attachments/assets/74deafc4-10bc-4c1f-8cf3-fd3b3df08480" />
>
<br>

* **Step 5: Navigating to the Virtual Machine creation portal.**
<br>
<img width="1366" height="768" alt="Step 5  Initialization of Virtual Machine Portal" src="https://github.com/user-attachments/assets/16276143-1d33-4d81-9b5c-0880a659ed07" />
>
<br>

* **Step 6: Virtual Machine deployment wizard initialized.**
<br>
<img width="1366" height="768" alt="Step 6  Virtual Machine Creation Portal successfully launched" src="https://github.com/user-attachments/assets/69413075-aaf0-4983-ba3b-43d220dd37b2" />
>
<br>

* **Step 7: Selecting Windows 11 Pro image and appropriate instance size.**
<br>
<img width="1366" height="768" alt="Step 7  Virtual Machine Creation Portal  Seleted Windows 11 Pro as iamge   size" src="https://github.com/user-attachments/assets/ec78d081-3b9d-40fb-a37d-42ea93856298" />
<br>

* **Step 8: Proceeding through VM configuration settings.**
<br>
* <img width="1366" height="768" alt="Step 8  Virtual Machine Creation Porta" src="https://github.com/user-attachments/assets/2342c060-7a10-4f17-abce-f3c5ec74906a" />
>
<br>

* **Step 9: Setting deployment scope: Resource Group "Tickets", VM name "osTicketVM", and East Asia region.**
<br>
<img width="1366" height="768" alt="Step 9  Virtual Machine Creation Portal - Adding Credentials Resource Group Tickets, Name osTicketVM   Zone East Asia" src="https://github.com/user-attachments/assets/829a2573-9212-4714-9d4b-822d0071fd6b" />
>
<br>

* **Step 10: Defining administrative credentials and security settings for `osTicketVM`.**
<br>
<img width="984" height="1600" alt="Step 10  Credentilas such as password   name for osTicketVM" src="https://github.com/user-attachments/assets/d029d83b-9985-4495-92a2-477a2d488bfb" />
>
<br>

* **Step 11: Finalizing VM deployment parameters.**
<br>
<img width="1366" height="768" alt="Step 11  Adding final credentilas for Tickets VM creation" src="https://github.com/user-attachments/assets/98ec3b83-6d80-4353-965b-3c89e3e96dd2" />
>
<br>

* **Step 12: Reviewing and confirming deployment for `osTicketVM`.**
<br>
<img width="1366" height="768" alt="Step 12  Confirming Creation of Tickets VM" src="https://github.com/user-attachments/assets/cc5dc99d-0dac-4d1d-9805-e42f06a9731b" />
>
<br>

* **Step 13: Virtual Machine deployment successfully completed.**
<br>
* <img width="1366" height="768" alt="Step 13  Successful Creation of osTicketVM" src="https://github.com/user-attachments/assets/9d965b7c-8555-4d20-bcd6-5f6de780da7f" />
>
<br>

* **Step 14: Retrieving the Public IP address for Remote Desktop Connection.**
<br>
* <img width="1366" height="768" alt="Step 14  Copying public IP Address of osTicketVM on Remote Desktop Connection" src="https://github.com/user-attachments/assets/686fd7c1-691a-4d7f-b3c3-19de6e1fa19d" />
>
<br>

* **Step 15: Establishing RDP connection with IP `40.81.28.195` and username "Tickets".**
<br>
<img width="1366" height="768" alt="Step 15  Adding credentials Public IP address 40 81 28 195   name Tickets to launch osTicketVM" src="https://github.com/user-attachments/assets/261dba99-2d52-4a92-ad47-8b0c029c4b12" />
>
<br>

* **Step 16: Authenticating RDP session with administrative password.**
<br>
<img width="1366" height="768" alt="Step 16  Adding last credential password to launch osTicketVM" src="https://github.com/user-attachments/assets/55b1fffd-3577-497c-b29f-cd39b301318b" />
>
<br>

* **Step 17: Remote Desktop session successfully established.**
<br>
<img width="1366" height="768" alt="Step 17  Successful launch of osTicketVM" src="https://github.com/user-attachments/assets/1ab828e6-1f60-4369-9284-c66bb3ea2962" />
>
<br>

* **Step 18: Verifying active RDP session via Windows interface.**
<br>
<img width="1366" height="768" alt="Step 18  Confirming I am in osTicketVM again by clicking windows key" src="https://github.com/user-attachments/assets/b587a0ed-b734-45df-817b-ac4a5a372f13" />
>
<br>

⸻

## 🔹 Phase 2. Server Prerequisites, IIS, PHP, MySQL Environment & Web Server Configuration.
In this phase, I downloaded and extracted the osTicket installation files, then configured Internet Information Services (IIS) by enabling the CGI feature. After completing the configuration, I verified that the IIS web server was functioning correctly by accessing the local web server through the loopback address.

⸻
>
<br>

* **Step 19: Opening Microsoft Edge to download the osTicket source files.**
<br>  
<img width="1366" height="768" alt="Step 19  Opening Microsoft Edge to download osTicket Installation file" src="https://github.com/user-attachments/assets/059f8668-66c1-435e-a542-5acdd17f8815" />
>
<br>

* **Step 20: Accessing the osTicket download page.**
<br>  
<img width="1366" height="768" alt="Step 20  Successful lauch of page to download osTicket installation file" src="https://github.com/user-attachments/assets/e4a6daf9-616a-44f5-b207-b1fddb01d26a" />
>
<br>

* **Step 21: osTicket installation package successfully downloaded.**
<br> 
<img width="1366" height="768" alt="Step 21  Successful downlaod of osTicket installation file to download folder" src="https://github.com/user-attachments/assets/3c425a1e-3b54-4ac7-b130-bdc8b8650508" />
>
<br>

* **Step 22: Moving the installation package to the Desktop for easier access.**
<br> 
<img width="1366" height="768" alt="Step 22  Moved osTicket installation file to Desktop folder" src="https://github.com/user-attachments/assets/97df4693-0b6e-4e81-ae12-223fd888d245" />
>
<br>

* **Step 23: Verifying installation file location on the Desktop.**
<br>  
<img width="1366" height="768" alt="Step 23  Confirmation osTicket installation file is in the Desktop folder page" src="https://github.com/user-attachments/assets/6acfa64c-428e-4cba-a4e0-0110823da746" />
>
<br>

* **Step 24: Initializing extraction of the osTicket archive.**
<br>  
<img width="1366" height="768" alt="Step 24  Extracting osTicket installation files" src="https://github.com/user-attachments/assets/fce2ca08-b22b-4114-848c-2edd07c7f22c" />
>
<br>

* **Step 25: Defining target path for extraction to the Desktop.**
<br>
<img width="1366" height="768" alt="Step 25  Extracting the files to desktop" src="https://github.com/user-attachments/assets/be914c0e-21a7-4f3a-abe4-031644ddeebc" />
>
<br>

* **Step 26: Extraction process completed successfully.**
<br>
<img width="1366" height="768" alt="Step 26  Successfull extraction of files" src="https://github.com/user-attachments/assets/e2c6407a-24c7-4869-97b3-468ef9ef12bf" />
>
<br>

* **Step 27: Accessing the Windows Control Panel via the search bar.**
<br>
<img width="1366" height="768" alt="Step 27  Went to the search bar to look for Control Panel to launch it" src="https://github.com/user-attachments/assets/2135f233-7715-4080-bb85-92b19ffd9e6e" />
>
<br>

* **Step 28: Control Panel interface launched.**
<br>
<img width="1366" height="768" alt="Step 28  Successful lauch of Control Panel" src="https://github.com/user-attachments/assets/a6a7c898-461b-4290-a45b-651eb1173508" />
>
<br>

* **Step 29: Navigating to the "Programs and Features" management console.**
<br>
<img width="1366" height="768" alt="Step 29  Navigated to Programs on Control Panel to Launch it" src="https://github.com/user-attachments/assets/a89216f3-87ae-442e-811a-1cbfe7d7d3f3" />
>
<br>

* **Step 30: Programs console opened successfully.**
<br>
<img width="1366" height="768" alt="Step 30  Successful launch of Programs on Control Panel" src="https://github.com/user-attachments/assets/bda684c3-d1da-4155-b339-9686bdb893b5" />
>
<br>

* **Step 31: Accessing "Turn Windows features on or off" to configure IIS.**
<br>
<img width="1366" height="768" alt="Step 31  Launched Windows features to set up CGI" src="https://github.com/user-attachments/assets/f1ed8114-bc29-4f49-8b62-1b0b109d0183" />
>
<br>

* **Step 32: Locating Internet Information Services in the features list.**
<br> 
<img width="1366" height="768" alt="Step 32  Scrolled to down Internet Information Services to open it on Windows Features" src="https://github.com/user-attachments/assets/7097e0e6-7a93-4b1b-86ae-ec4844b24ae5" />
>
<br>

* **Step 33: Expanding IIS to access Application Development Features.**
<br>
<img width="1366" height="768" alt="Step 33  Expanded the Internet Information Services folder to navigate to Application Developement Features" src="https://github.com/user-attachments/assets/b98f1e5c-3d59-4771-9e1f-7c7503c3eeb0" />
>
<br>

* **Step 34: Navigating to the CGI sub-feature.**
<br>
<img width="1366" height="768" alt="Step 34  Expanded Application Developement Features to locate CGI" src="https://github.com/user-attachments/assets/2ef8d23b-1fcb-40fa-a80c-397b9dcc1ead" />
>
<br>

* **Step 35: Enabling and installing the CGI module.**
<br>
<img width="1366" height="768" alt="Step 35  Clicked on CGI to download it on Windows Features within the Application Development Features" src="https://github.com/user-attachments/assets/85171e09-58a3-4938-bb09-ceab86ae2b44" />
>
<br>

* **Step 36: CGI module installation confirmed.**
<br>
<img width="1366" height="768" alt="Step 36  Successful download of CGI" src="https://github.com/user-attachments/assets/969c01c3-b1bf-4593-ac71-f260cf0a8cb4" />
>
<br>

* **Step 37: Launching Microsoft Edge to verify the IIS web server.**
<br>
<img width="1366" height="768" alt="Step 37  Launch of  Microsoft Edge to intiate IIS - Internet Information Services" src="https://github.com/user-attachments/assets/11aad997-f197-4242-97e2-155f52d71a94" />
>
<br>

* **Step 38: Verifying IIS functionality by accessing the local loopback address `127.0.0.1`.**
<br>
<img width="1366" height="768" alt="Step 38  Prompted loop back address 127 0 0 1 to Successfully launch IIS - Internet Information Services" src="https://github.com/user-attachments/assets/778320da-7375-4132-aeab-0ef38ab3425c" />
>
<br>

⸻

## 🔹 Phase 3. PHP & Database Setup.
In this phase, I installed and configured the core software required by osTicket, including PHP, URL Rewrite, Microsoft Visual C++ Redistributable, and MySQL Server. I then integrated PHP with IIS using PHP Manager and restarted the web server to apply the new configuration.

⸻
>
<br>

* **Step 39: Accessing the installation directory to run the PHP installer.**
<br>
<img width="1366" height="768" alt="Step 39  Navigated back to osTicket Installation Files to install PHP" src="https://github.com/user-attachments/assets/c50674a2-7e73-421f-8cf8-c98c8953d60d" />
>
<br>

* **Step 40: Locating the PHP executable for installation.**
<br>
<img width="1366" height="768" alt="Step 40  Opened the installation file to locate PHP for installation" src="https://github.com/user-attachments/assets/37f95c80-86d4-432d-97f6-cbcdf69897a0" />
>
<br>

* **Step 41: Running the PHP setup wizard.**
<br>
* <img width="1366" height="768" alt="Step 41  Setting up PHP to install it" src="https://github.com/user-attachments/assets/765cb693-bf34-4b02-9b9b-5196933fa8ba" />
>
<br>

* **Step 42: PHP installed successfully.**
<br>
<img width="1366" height="768" alt="Step 42  Successful installation of PHP" src="https://github.com/user-attachments/assets/7a39abb0-9a60-4f64-8d7c-14a76aef6691" />
>
<br>

* **Step 43: Accessing the installation directory to run the URL Rewrite Module installer.**
<br>
<img width="1366" height="768" alt="Step 43  Navigated back to osTicket Installation Files to Launch  REWRITE MODULE  to Install it" src="https://github.com/user-attachments/assets/6697eb5e-0cb2-4c8c-bb27-e23c41f08815" />
>
<br>

* **Step 44: Running the URL Rewrite Module setup wizard.**
<br>
<img width="1366" height="768" alt="Step 44  REWRITE Module Setup for Installation" src="https://github.com/user-attachments/assets/52f4e301-47e4-4242-9926-a8700d3cae9b" />
>
<br>

* **Step 45: URL Rewrite Module installed successfully.**
<br>
<img width="1366" height="768" alt="Step 45  Successfull Installation of REWRITE MODULE" src="https://github.com/user-attachments/assets/50a5c791-7275-40cd-b1ed-5e9149db3456" />
>
<br>

* **Step 46: Accessing the C: drive to prepare the PHP directory.**
<br>
* <img width="1366" height="768" alt="Step 46  Navigating to my Windows C drive to create PHP folder" src="https://github.com/user-attachments/assets/e254d51a-14e5-44f1-842e-f1b714026b6a" />
>
<br>

* **Step 47: Creating the `C:\PHP` directory.**
<br>
<img width="1366" height="768" alt="Step 47  Creating a folder of PHP in Windows C drive" src="https://github.com/user-attachments/assets/8831f893-4380-4e3c-95ca-263667fab2ac" />
>
<br>

* **Step 48: PHP directory created successfully.**
<br>
<img width="1366" height="768" alt="Step 48  Successful creation of PHP folder" src="https://github.com/user-attachments/assets/c6b8b9bc-0173-4064-a24b-20b0360b66b5" />
>
<br>

* **Step 49: Initiating the copy of PHP binaries to the `C:\PHP` directory.**
<br>
* <img width="1366" height="768" alt="Step 49  Opening osTicket Installation File to extract PHP 738 files to PHP folder in Windows C drive" src="https://github.com/user-attachments/assets/d918c245-fe39-4afd-a073-122948137bd0" />
>
<br>

* **Step 50: Extracting PHP binaries to `C:\PHP`.**
<br>
<img width="1366" height="768" alt="Step 50  Extracting PHP 738 files to PHP folder in Windows C drive" src="https://github.com/user-attachments/assets/f654cecf-c002-49ba-a4b1-7f0e465467ba" />
>
<br>

* **Step 51: PHP binaries extraction complete.**
<br>
<img width="1366" height="768" alt="Step 51  Successful extraction PHP 738 files to PHP folder in Windows C drive" src="https://github.com/user-attachments/assets/99c695a5-dfbc-4c54-b425-af0585b4634d" />
>
<br>

* **Step 52: Verifying PHP binary files in the `C:\PHP` directory.**
<br>
<img width="1366" height="768" alt="Step 52  Confirmation PHP 738 files are in PHP folder in Windows C drive" src="https://github.com/user-attachments/assets/69d5ab03-8bc7-4be7-b873-f1c990f53c81" />
>
<br>

* **Step 53: Running the Microsoft Visual C++ Redistributable installer.**
<br>
<img width="1366" height="768" alt="Step 53  Navigation back to osTicket Installation File to install Microsoft Visual C" src="https://github.com/user-attachments/assets/83ee7e03-bf10-49e6-8851-8dcca3274914" />
>
<br>

* **Step 54: Executing the Visual C++ installation wizard.**
<br>
<img width="1366" height="768" alt="Step 54  Installation of Microsoft Visual C" src="https://github.com/user-attachments/assets/5ca12ffc-78e7-4d47-9780-462b061cec2d" />
>
<br>

* **Step 55: Visual C++ installation confirmed.**
<br>
<img width="1366" height="768" alt="Step 55  Successful Installation of Microsoft Visual C" src="https://github.com/user-attachments/assets/d0680b8d-abc2-4a3f-8544-c69dcbeec754" />
>
<br>

* **Step 56: Launching the MySQL installation wizard.**
<br>
<img width="1366" height="768" alt="Step 56  Navigation back to osTicket Installation File to Install MYSQL" src="https://github.com/user-attachments/assets/dffe5ab6-62b8-4b0c-909a-e1ca54a19edc" />
>
<br>

* **Step 57: I Launched the MySQL Server 5.5 Installation Wizard.**
<br>
<img width="1366" height="768" alt="Step 57   Installing  MYSQL" src="https://github.com/user-attachments/assets/3f7ef130-9e78-4e3b-93f0-4a0bfb105785" />
>
<br>

* **Step 58: I Began Installing MySQL Server 5.5 .**
<br>
<img width="1366" height="768" alt="Step 58  Installing MYSQL" src="https://github.com/user-attachments/assets/a6a13244-a3fb-47bb-9e86-5c637909fbb1" />
>
<br>

* **Step 59: I Configured the MySQL Server 5.5 Instalation Settings.**
<br>
<img width="1366" height="768" alt="Step 59  Installing MYSQL" src="https://github.com/user-attachments/assets/0cb41f92-e8e7-48ee-aead-840541b42f34" />
>
<br>

* **Step 60: Configured the MySQL Root Password .**
<br>
<img width="1366" height="768" alt="Step 60  Defining MYSQL password to Install MYSQL" src="https://github.com/user-attachments/assets/ccc1bcaf-4c8f-46a6-a52b-91b85812c5a5" />
>
<br>

* **Step 61: Accessing Internet Information Services (IIS) Manager.**
<br>
<img width="1366" height="768" alt="Step 61  Navigating to the search bar launch to ISS" src="https://github.com/user-attachments/assets/22f92b47-3588-41c2-ae4e-a5b667a7c6c6" />
>
<br>

* **Step 62: Launching PHP Manager within IIS.**
<br>
<img width="1366" height="768" alt="Step 62  Successful launch of IIS - Navigating to within ISS to launch PHP Manager" src="https://github.com/user-attachments/assets/b358045a-3496-4a9a-8170-b1415300a0dd" />
>
<br>

* **Step 63: PHP Manager successfully loaded.**
<br>
<img width="1366" height="768" alt="Step 63  PHP manager launched" src="https://github.com/user-attachments/assets/eb5738c1-daa5-4c36-8b67-7e474f4cfe6c" />
>
<br>

* **Step 64: Linking PHP Manager to the PHP binary path.**
<br>
<img width="1366" height="768" alt="Step 64  Configuring PHP Manager by using PHP files within PHP Folder" src="https://github.com/user-attachments/assets/795e451d-14f8-4606-a177-8ea2adc8905b" />
>
<br>

* **Step 65: Configuring PHP Manager to use the PHP-CGI executable.**
<br>
<img width="1366" height="768" alt="Step 65  Configuring PHP Manager by using PHP files within PHP Folder Selecting PHP CGI" src="https://github.com/user-attachments/assets/a72d3ac9-4eb3-4ec6-bd50-2e6d3bacd8de" />
>
<br>

* **Step 66: Confirming PHP-CGI configuration settings.**
<br>
<img width="1366" height="768" alt="Step 66  Configuring PHP Manager by using PHP files within PHP Folder Selecting PHP CGI" src="https://github.com/user-attachments/assets/8e60ba59-2a90-495b-85f4-092c60c8b09e" />
>
<br>

* **Step 67: Prompting an IIS service restart to apply PHP configurations.**
<br>
<img width="1366" height="768" alt="Step 67  Prompt to Restart IIS to update PHP Manager Settings" src="https://github.com/user-attachments/assets/6a569ee4-c607-4904-96a3-09c6d3263913" />
>
<br>

* **Step 68: IIS restart completed successfully.**
<br>
<img width="1366" height="768" alt="Step 68  Successful Restart of IIS to update PHP Manager Settings" src="https://github.com/user-attachments/assets/7a2c5fea-5ada-4097-bf2d-cd124d24f85a" />
>
<br>

⸻

## 🔹 Phase 4. osTicket Deployment & Initial Configuration.
In this phase, I deployed the osTicket application by extracting the installation files, copying them to the IIS web directory, and configuring the required PHP extensions. I then completed the web-based installation wizard and successfully logged into the osTicket Administrator Control Panel.

⸻
>
<br>

* **Step 69: Accessing the osTicket source files for final deployment.**
<br>
<img width="1366" height="768" alt="Step 69  Navigating to osTicket Installation to extract osTicket v1 15 8 files within osTicket v1 15 8" src="https://github.com/user-attachments/assets/dfb257e6-19d0-43c1-bc11-cf202ab085c6" />
>
<br>

* **Step 70: Locating the `v1.15.8` directory.**
<br>
<img width="1366" height="768" alt="Step 70  Successful launch of osTicket Installation to extract osTicket v1 15 8 files within osTicket v1 15 8" src="https://github.com/user-attachments/assets/f40447e5-ceff-4adf-93eb-3c86371aa3cf" />
>
<br>

* **Step 71: Extracting osTicket application files.**
<br>
<img width="1366" height="768" alt="Step 71  Extracting osTicket v1 15 8 files within osTicket v1 15 8 folder" src="https://github.com/user-attachments/assets/c57642ca-33ef-4a1d-9c7b-981f575e0086" />

* **Step 72: Extracting source code to the project directory.**
<br>
<img width="1366" height="768" alt="Step 72  Extracting osTicket v1 15 8 files within osTicket v1 15 8 folder process" src="https://github.com/user-attachments/assets/cd7ed8c5-88a6-4d59-94e6-787a1f11d636" />
>
<br>

* **Step 73: Extraction completed successfully.**
<br>
<img width="1366" height="768" alt="Step 73  Successful extraction osTicket v1 15 8 files" src="https://github.com/user-attachments/assets/b417f743-00b4-45ad-92e7-b49bc8f0e22a" />
>
<br>

* **Step 74: Accessing the upload directory in the osTicket source files.**
<br>
<img width="1366" height="768" alt="Step 74  Successful launch of osTicket v1 15 8 folder to copy upload file" src="https://github.com/user-attachments/assets/fef89e61-45cd-416f-ac57-e9c477919cb7" />
>
<br>

* **Step 75: Copying the contents of the upload folder.**
<br>
<img width="1366" height="768" alt="Step 75  Copying upload file" src="https://github.com/user-attachments/assets/7fd57588-0ebe-4a2b-9d08-52521d0af4a6" />
>
<br>

* **Step 76: Deploying application files to `C:\inetpub\wwwroot\`.**
<br>
<img width="1366" height="768" alt="Step 76  Paste of upload file to wwwroot folder Within C Drive" src="https://github.com/user-attachments/assets/e8c5ae33-0ff0-42fb-8fd2-a0437a4a15c1" />
>
<br>

* **Step 77: Renaming the directory to "osTicket" for easier web access.**
<br>
<img width="1366" height="768" alt="Step 77  Renaming upload file to osTicket in wwwroot within Windows C drive" src="https://github.com/user-attachments/assets/b1dfe4de-d67f-4f94-abee-cc6fd73f060b" />
>
<br>

* **Step 78: Restarting IIS to register the new application.**
<br>
<img width="1366" height="768" alt="Step 78  Launch of IIS to restart it to update settings" src="https://github.com/user-attachments/assets/b84a4e76-a4f7-4935-a3fe-1cf62be7b340" />
>
<br>

* **Step 79: IIS services successfully restarted.**
<br>
<img width="1366" height="768" alt="Step 79  Successful Restart of ISS" src="https://github.com/user-attachments/assets/1cb6eb6c-b843-4d98-9651-978ea3d76890" />
>
<br>

* **Step 80: Verifying the Application Pool settings for the site.**
<br>
<img width="1366" height="768" alt="Step 80  Navigating to Application Pools in IIS" src="https://github.com/user-attachments/assets/33162206-7a56-4585-91d5-15305711fa4d" />
>
<br>

* **Step 81: Navigating to the Default Web Site within IIS Manager.**
<br>
<img width="1366" height="768" alt="Step 81  Navigating to Sites in IIS" src="https://github.com/user-attachments/assets/f7e05e15-961b-425f-b1b9-51db44735e4e" />
>
<br>

* **Step 82: Launching the default web site to initiate the osTicket web-based installer.**
<br>
<img width="1366" height="768" alt="Step 82  Navigating to Default Web Site to launch SEMI installed osTicket" src="https://github.com/user-attachments/assets/8227b9b1-c20b-4c83-933b-d77837e37e71" />
>
<br>

* **Step 83: osTicket installer landing page displayed.**
<br>
<img width="1366" height="768" alt="Step 83  Successful launch of SEMI installed osTicket" src="https://github.com/user-attachments/assets/4efb0e0e-13d7-4f41-bfe1-05c4c04418d3" />
>
<br>

* **Step 84: Navigating to the osTicket directory in IIS to manage PHP extensions.**
<br>
<img width="1366" height="768" alt="Step 84  Navigating to osTicket folder within ISS for authetication in PHP Manager" src="https://github.com/user-attachments/assets/662a00b2-f1a2-4180-a046-879cdb490f68" />
>
<br>

* **Step 85: Launching Authentication management.**
<br>
<img width="1366" height="768" alt="Step 85  Prompt to launch Authetication in PHP manager" src="https://github.com/user-attachments/assets/2837d722-56c4-4d64-a2a3-487ed43d14fe" />
>
<br>

* **Step 86: Accessing PHP extension management.**
<br>
<img width="1366" height="768" alt="Step 86   Successful launch of Authetication in PHP manager to start process of to enable some PHP extentions" src="https://github.com/user-attachments/assets/a10156ed-1a9b-4728-96e9-41198c4661f7" />
>
<br>

* **Step 87: Viewing available PHP extensions.**
<br>
<img width="1366" height="768" alt="Step 87  Prompt to launch of PHP Extention to enable PHP extentions" src="https://github.com/user-attachments/assets/7bf3474f-40b2-4274-8104-4dc059d4e69d" />
>
<br>

* **Step 88: Initiating configuration of required extensions.**
<br>
<img width="1366" height="768" alt="Step 88  Launch of PHP Extention to enable PHP extentions" src="https://github.com/user-attachments/assets/8100f860-26bf-4076-95e0-278966791abc" />
>
<br>

* **Step 89: Enabling the `php_intl.dll` extension.**
<br>
<img width="1366" height="768" alt="Step 89  Enabling PHP dil withing PHP Extentions" src="https://github.com/user-attachments/assets/bb2f3c11-0540-4e21-a578-2aaeca7a7aa2" />
>
<br>

* **Step 90: Enabling the `php_opcache.dll` extension.**
<br>
<img width="1366" height="768" alt="Step 90  Enabling php opcache dill within PHP Extentions" src="https://github.com/user-attachments/assets/6ac71d2f-2c27-4d8d-bedb-8413ed6631b5" />
>
<br>

* **Step 91: Refreshing the osTicket installation page.**
<br>
<img width="1366" height="768" alt="Step 91  Navigated back SEM installed osTicket" src="https://github.com/user-attachments/assets/1c27f8c3-544f-467e-8790-c5015932e775" />
>
<br>

* **Step 92: Modifying file permissions for `ost-sampleconfig.php` to allow renaming/writing.**
<br>
<img width="1366" height="768" alt="Step 92  Navigation to ost sampleconfig php to alter its properties in the osTicket Folder within Windows C drive" src="https://github.com/user-attachments/assets/26e30bff-0cdb-4e19-a89d-e69d566d5a4f" />
>
<br>

* **Step 93: Updating security properties to grant "Everyone" modify access.**
<br>
<img width="1366" height="768" alt="Step 93  ost sampleconfig php security properties altered to everyone" src="https://github.com/user-attachments/assets/a2eeebba-5274-40a3-a1ad-040332d681a2" />
>
<br>

* **Step 94: Viewing the System Settings section of the osTicket installation wizard (Page 1).**
<br>
<img width="1366" height="768" alt="Step 94  1st Blank Credentials page of osTicket to complete intallation" src="https://github.com/user-attachments/assets/8cfdc618-744d-40b5-8452-12f32b0569ea" />
>
<br>

* **Step 95: Viewing the Administrator and Database configuration section (Page 2).**
<br>
<img width="1366" height="768" alt="Step 95  2nd Blank Credentials page of osTicket to complete intallation" src="https://github.com/user-attachments/assets/4f8bd677-8a73-4f42-8ca4-19e8ccc765b0" />
>
<br>

* **Step 96: Reviewing the complete osTicket installation form before configuration (Page 3).**
<br>
<img width="1366" height="768" alt="Step 96  3rd Blank Credentials page of osTicket to complete intallation" src="https://github.com/user-attachments/assets/2f05896e-b6c8-4eb4-8054-c9a7644d3a4a" />
>
<br>

* **Step 97: Reviewing the installation credentials prepared for the osTicket deployment.**
<br>
<img width="1047" height="1600" alt="Step 97  Credentials sheet for osTicket installation" src="https://github.com/user-attachments/assets/24d0e66a-adbe-4853-b5a5-16e583112035" />
>
<br>

* **Step 98: Configuring the System Settings for the osTicket installation.**
<br>
<img width="1366" height="768" alt="Step 98  Defining credentials for 1st page to intall osTicket" src="https://github.com/user-attachments/assets/87190d88-6566-4e1e-a76b-038bc31dbbfe" />
>
<br>

* **Step 99: Configuring the Administrator account and MySQL database settings.**
<br>
<img width="1366" height="768" alt="Step 99  Defining credentials for 2nd page to intall osTicket" src="https://github.com/user-attachments/assets/2ba40533-5624-4edd-9c5b-4e046c769a63" />
>
<br>

* **Step 100: Completing the final installation configuration before deploying osTicket.**
<br>
<img width="1366" height="768" alt="Step 100  Defining credentials for 3rd page to intall osTicket" src="https://github.com/user-attachments/assets/0bc7bff9-4bf3-42fe-bdbb-f7f15b8d749f" />
>
<br>

* **Step 101: osTicket install.**
<br>
<img width="1366" height="768" alt="Step 101  Successful complete installation of osTicket" src="https://github.com/user-attachments/assets/b0fb2c7d-1617-4705-a7a8-ade41677a482" />
>
<br>

* **Step 102: Inputting administrative credentials to access the portal.**
<br>
<img width="1366" height="768" alt="Step 102  Adding credentials to log in osTicket application" src="https://github.com/user-attachments/assets/94457eb4-a17c-4dfa-9fb9-7e90b889bff4" />
>
<br>

* **Step 103: Successful login to the osTicket Admin Panel.**
<br>
<img width="1366" height="768" alt="Step 103  Successful login to osTicket" src="https://github.com/user-attachments/assets/98ecbead-6c70-4443-9f8d-dae61183cff0" />
>
<br>

⸻

## 🔹 Phase 5. User Creation, Management & Ticket Resolution Testing.
In this phase, I configured the osTicket environment by creating roles, departments, teams, agents, users, and SLA policies. To validate the deployment, I submitted a support ticket, assigned it to an agent, and completed the ticket resolution workflow from submission to documented resolution.

⸻
>
<br>

* **Step 104: Navigating to the Admin Panel to manage Roles.**
<br>
<img width="1366" height="768" alt="Step 104  Navigated to admin panel to start process of adding a role" src="https://github.com/user-attachments/assets/d8766949-adcd-47bc-acaf-ea6a7006c332" />
>
<br>

* **Step 105: Accessing the Role management portal.**
<br>
<img width="1366" height="768" alt="Step 105  Navigated to role portal to view existing roles and to add new role" src="https://github.com/user-attachments/assets/ebe412d5-d0c0-4711-b47e-fc3c5aa4dfd6" />
>
<br>

* **Step 106: Creating a new custom role: "Supreme Admin".**
<br>
<img width="1366" height="768" alt="Step 106  Naming name role Supreme Admin" src="https://github.com/user-attachments/assets/4dc965ef-99b5-4911-a3f7-07ac617fe5e5" />
>
<br>

* **Step 107: Configuring ticket permissions for "Supreme Admin".**
<br>
<img width="1366" height="768" alt="Step 107  Viewing current permissions for tickets of Supreme Admin Role" src="https://github.com/user-attachments/assets/3fda39a9-d059-4bf0-aea0-f77157ca956d" />
>
<br>

* **Step 108: Defining granular access levels for ticket management.**
<br>
<img width="1366" height="768" alt="Step 109  Viewing  permissions for tasks of Supreme Admin Role" src="https://github.com/user-attachments/assets/0a0c2c65-9d96-4506-a1f5-22cd00dee03a" />
>
<br>

* **Step 109: Configuring task management permissions.**
<br>
<img width="1366" height="768" alt="Step 110  Viewing  permissions for knowledgebase of Supreme Admin Role" src="https://github.com/user-attachments/assets/d3dbc389-1c2b-4fc8-868d-e9ed65461a53" />
>
<br>

* **Step 110: Setting Knowledgebase access permissions.**
<br>
<img width="1366" height="768" alt="Step 111  Supreme Role Added Successfully" src="https://github.com/user-attachments/assets/7d20f883-4d80-41a3-b465-8b9d5518595d" />

* **Step 111: "Supreme Admin" role successfully created.**
<br>
<img width="1366" height="768" alt="Step 112  Adding a department in osTicket" src="https://github.com/user-attachments/assets/1f7da84a-979f-4fb6-84f1-057f89cc907c" />
>
<br>

* **Step 112: Navigating to Department management.**
<br>
* <img width="1366" height="768" alt="Step 112  Adding a department in osTicket" src="https://github.com/user-attachments/assets/a4401a34-cdf6-4451-9cf7-07b347f00efa" />
>
<br>

* **Step 113: Defining attributes for the new "SysAdmins" department.**
<br>
<img width="1366" height="768" alt="Step 113  Define Credentials of new department" src="https://github.com/user-attachments/assets/756a13b5-7e44-4f89-b470-188c02511536" />
>
<br>

* **Step 114: "SysAdmins" department created successfully.**
<br>
<img width="1366" height="768" alt="Step 114  SysAdmins Department Successfully Created" src="https://github.com/user-attachments/assets/da26ec14-cef9-4a20-b4de-0bd9ac9c8cac" />
>
<br>

* **Step 115: Accessing Team management - Creating a New Team in osTicket.**
<br>
<img width="1366" height="768" alt="Step 115  Creating a team on osTicket" src="https://github.com/user-attachments/assets/0de4dad8-ae85-41bc-a2c6-d348b29a49f8" />
>
<br>

* **Step 116: Configuring the Online Sales Team.**
<br>
<img width="1366" height="768" alt="Step 116  Defining credentials of team being created" src="https://github.com/user-attachments/assets/6bc54c35-2737-4e9a-9dd6-3cf5912b1992" />
>
<br>

* **Step 117: Online Sales Team Successfully Created.**
<br>
<img width="1366" height="768" alt="Step 117  SysAdmins Team Successfully created" src="https://github.com/user-attachments/assets/472d30d8-0429-4943-b792-9a4954e8835e" />
>
<br>

* **Step 118: Accessing the Agent Directory.**
<br>
<img width="1366" height="768" alt="Step 118  Viewing existing agents" src="https://github.com/user-attachments/assets/ae9b1343-4865-48e6-ba40-0dacb774d22a" />
>
<br>

* **Step 119: Initiating the creation of a new agent: "Muneni Sigana".**
<br>
* <img width="1366" height="768" alt="Step 119  Adding new agent Muneni Sigana" src="https://github.com/user-attachments/assets/f189dfe5-9ae4-4f91-8eb5-c2edd8933ab6" />
>
<br>

* **Step 120: Assigning the "Supreme Admin" role and "SysAdmins" department to Muneni.**
<br>
<img width="1366" height="768" alt="Step 120  Giving Muneni Supreme Admin Role   Adding them to the SysAdmin Department" src="https://github.com/user-attachments/assets/80d426ab-2bb5-4b6b-af14-4c3b62fd9181" />
>
<br>

* **Step 121: Granting full administrative permissions to Muneni.**
<br>
<img width="1366" height="768" alt="Step 121  Giving Muneni all permissions" src="https://github.com/user-attachments/assets/92ab72a5-125e-4cf3-915b-98a74ea9e0dc" />
>
<br>

* **Step 122: Assigning Muneni to the "Online Sales" team.**
<br>
<img width="1366" height="768" alt="Step 122  Adding Muneni to Online Sales Team" src="https://github.com/user-attachments/assets/e15010a0-6886-4152-b01d-cce132ac81a9" />
>
<br>

* **Step 123: Agent "Muneni Sigana" account successfully provisioned.**
<br>
<img width="1366" height="768" alt="Step 123  Agent Muneni Sigana Successfully created" src="https://github.com/user-attachments/assets/e43dfaa0-33a9-44ff-a8fe-b3803c9ccb5e" />
>
<br>

* **Step 124: Reviewing the updated Agent Directory.**
<br>
<img width="1366" height="768" alt="Step 124  Viewing list of agents" src="https://github.com/user-attachments/assets/50f49f99-1eb0-4b15-9226-6c3cfdc03061" />
>
<br>

* **Step 125: Initiating the creation of a new agent: "Tshidi Bosiu Thaba".**
<br>
* <img width="1366" height="768" alt="Step 125  Creating Agent Tshidi Bosiu Thaba" src="https://github.com/user-attachments/assets/f7ed6c20-52c0-4cd3-bbf1-84bceab4e68d" />
>
<br>

* **Step 126: Assigning "View Only" role and "Support" department to Tshidi.**
<br>
<img width="1366" height="768" alt="Step 126  Giving Tshidi Bosiu Thaba View only role and adding them to the Support Department" src="https://github.com/user-attachments/assets/49f0a26f-7a33-48e6-8710-3153e17f7fc2" />
>
<br>

* **Step 127: Setting appropriate access permissions for Tshidi.**
<br>
<img width="1366" height="768" alt="Step 127   Giving Tshidi Bosiu Thaba all permissions" src="https://github.com/user-attachments/assets/d2847b7c-4b83-41cf-99d1-f490fecaec44" />
>
<br>

* **Step 128: Agent "Tshidi Bosiu Thaba" account successfully provisioned.**
<br>
<img width="1366" height="768" alt="Step 128  Agent Tshidi Bosiu Thaba Successfully created" src="https://github.com/user-attachments/assets/fa6298fc-992b-4d0d-9e59-6fb195e81972" />
>
<br>

* **Step 129: Verifying the full list of active agents.**
<br>
<img width="1366" height="768" alt="Step 129  Viewing list of Agents" src="https://github.com/user-attachments/assets/265b811a-ed64-48aa-a3e0-28e222618317" />
>
<br>

* **Step 130: Accessing the User Directory to manage end-users.**
<br>
<img width="1366" height="768" alt="Step 130  Navigated to User Directory to create users" src="https://github.com/user-attachments/assets/d8ac2348-2bb2-48fa-a68d-389e6dd799b7" />
>
<br>

* **Step 131: Configuring details for user "Andile Mngxitama".**
<br>
<img width="1366" height="768" alt="Step 131  Defining details of user Andile Mngxitama" src="https://github.com/user-attachments/assets/98076f3a-78ac-4a1f-a33d-e914e3fbd7fd" />
>
<br>

* **Step 132: User "Andile Mngxitama" successfully registered.**
<br>
<img width="1366" height="768" alt="Step 132  User Andile Mngxitama successfully created" src="https://github.com/user-attachments/assets/12fda3b0-4aad-4cd5-808d-e37766439fc4" />
>
<br>

* **Step 133: Configuring details for user "Mubuyiseni Ndlozi".**
<br>
<img width="1366" height="768" alt="Step 133  Defining details of user Mubuyiseni Ndlozi" src="https://github.com/user-attachments/assets/d89ab79d-5b66-4771-9ff3-67d5cdf907c3" />
>
<br>

* **Step 134: User "Mubuyiseni Ndlozi" successfully registered.**
<br>
<img width="1366" height="768" alt="Step 134  User Muyiseni Ndlozi successfully created" src="https://github.com/user-attachments/assets/2f51c01b-d556-479f-b9a7-3090c444f12d" />
>
<br>

* **Step 135: Verifying the user directory list - Viewing the List of Created Users.**
<br>
<img width="1366" height="768" alt="Step 135  Viewing list of users I created" src="https://github.com/user-attachments/assets/e0740b7a-b4fc-4bae-b809-9b68941d206d" />
>
<br>

* **Step 136: Accessing the Service Level Agreement (SLA) management portal.**
<br>
<img width="1366" height="768" alt="Step 136  Navigating to Service Level Agreement portal to Create SLAs" src="https://github.com/user-attachments/assets/7f4a4763-534b-4913-a6c8-a57ee0913c91" />
>
<br>

* **Step 137: SLA policy created successfully.**
<br>
<img width="1366" height="768" alt="Step 137  SLA successfully created" src="https://github.com/user-attachments/assets/529cb921-9eda-45f8-97bb-bd163d48f898" />
>
<br>

* **Step 138: Navigating to the Support Centre to simulate a ticket submission.**
<br>
<img width="1366" height="768" alt="Step 138  Navigating to Support Centre to lodge a ticket" src="https://github.com/user-attachments/assets/69c2bb40-e45c-4b58-88f3-e32f4baf1575" />
>
<br>

* **Step 139: Submitting a ticket as "Andile Mngxitama".**
<br>
<img width="1366" height="768" alt="Step 139  Lodging a ticket with user Andile Mngxitama" src="https://github.com/user-attachments/assets/c96f811f-8b8d-4618-88e6-41da1374281d" />
>
<br>

* **Step 140: Ticket successfully submitted to the queue.**
<br>
<img width="1366" height="768" alt="Step 140  Ticket successfully lodged by user Andile Mngxitama" src="https://github.com/user-attachments/assets/dd70a5e2-2413-441e-9929-2c3d2ac58938" />
>
<br>

* **Step 141: Siyolo Kamisa Opens the Ticket to Review the User's Issue "Andile Mngxitama".**
<br>
<img width="1366" height="768" alt="Step 141  Siyolo Kamisa recieves notification user Andile Mngxitama has lodged a ticket" src="https://github.com/user-attachments/assets/4ead3474-ed6d-404b-b3d4-9644e4f52af2" />
>
<br>

* **Step 142: Siyolo Kamisa reviewing the ticket details submitted by Andile Mngxitama.**
<br>
<img width="1366" height="768" alt="Step 142  Siyolo Kamisa opens ticket to see issue user Andile Mngxitama has" src="https://github.com/user-attachments/assets/ac843084-1a5f-4281-a935-3705ccf6a0eb" />
>
<br>

* **Step 143: Siyolo Kamisa escalating/assigning the ticket to agent "Tshidi Bosiu".**
<br>
<img width="1366" height="768" alt="Step 143  Siyolo Kamisa assigns ticket to Tshidi Bosiu" src="https://github.com/user-attachments/assets/890e2b04-789a-4d9b-b5e1-9f4c10748f3a" />
>
<br>

* **Step 144: Ticket Successfully Assigned to Tshidi Bosiu.**
<br>
* <img width="1366" height="768" alt="Step 144  Ticket successfully assigned to Tshidi Bosiu" src="https://github.com/user-attachments/assets/785286cf-bd22-4f8c-9a2b-36d13d23ee40" />
>
<br>

* **Step 145: Tshidi Bosiu logs in to resolve the assigned ticket.**
<br>
<img width="1366" height="768" alt="Step 145  Tshidi Bosiu logs in to resolve ticket" src="https://github.com/user-attachments/assets/22f2e9fc-3087-4b4c-ac64-110fc8d01094" />
>
<br>

* **Step 146: Tshidi Bosiu Reviews the Assigned Ticket.**
<br>
<img width="1366" height="768" alt="Step 146  Tshidi Bosiu notes down ticket" src="https://github.com/user-attachments/assets/cc8a44f8-45df-4df0-be80-4ac617674969" />
>
<br>

⸻

🌍 Real World Relevance

This project reflects the responsibilities commonly performed by IT Support Specialists, Help Desk Technicians, Desktop Support Engineers, and System Administrators working in enterprise environments.The skills demonstrated throughout this lab include deploying cloud infrastructure, configuring web servers, managing databases, administering user accounts, implementing role-based permissions, configuring Service Level Agreements, and managing the complete lifecycle of support tickets.These are practical tasks regularly performed in organizations that use help desk platforms such as osTicket, ServiceNow, Jira Service Management, Freshservice, or Zendesk, making this project directly applicable to real-world IT support operations.

🏁Conclusion

This lab successfully demonstrates the complete deployment and administration of an enterprise help desk environment using osTicket on Microsoft Azure. Starting with cloud infrastructure provisioning, the project progresses through web server configuration, PHP integration, database deployment, application installation, and administrative setup before validating the environment through a complete ticket management workflow.By documenting 146 individual implementation steps, this project showcases practical experience with cloud infrastructure, Windows administration, IIS, PHP, MySQL, and enterprise help desk operations. It highlights the technical and administrative skills required to deploy, manage, and support a modern ticketing system, providing a strong portfolio project for IT Support, Help Desk, Desktop Support, and Junior System Administrator roles.
