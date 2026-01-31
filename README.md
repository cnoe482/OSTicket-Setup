<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11</b> (22H2-PRO)

<h2>List of Prerequisites</h2>

- Microsoft Azure account
- Windows 11 Virtual Machine
- Remote Desktop Client
- Internet Information Services (IIS)
- <a href="https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0">osTicket Installation Files Package</a>

<h2>Step 0 – Setting up VM Environment</h2>
- Specs for Azure VM used in Lab
        - OS: Windows 11 Pro
        - Size: Standard D2s v3 (2 vcpus, 8 GiB memory)
        - Purpose: Host IIS + MySQL + osTicket
- Full Setup tutorial here
        - [AzureVM-Setup](https://github.com/cnoe482/VM-Setup)

<h2>Step 1 – Download osTicket</h2>

- Download osTicket Installation Files Package
- Extract the files to the default path (Right Click the downloaded File → Extract)

<img width="1144" height="730" alt="step1" src="https://github.com/user-attachments/assets/5f1e1f02-8b42-4101-bb8d-77c5df1ae34d" />

<h2>Step 2 – Enable IIS</h2>

- Press Win + R
- Type "optionalfeatures"
- Enable "Internet Information Services"
- Enable Internet Information Services → World Wide Web Services → Application Development Features → CGI
- Click OK
- Restart Computer

<img width="688" height="697" alt="step2" src="https://github.com/user-attachments/assets/e820601f-38ab-479e-a59e-aa22ac08664a" />


<h2>Step 3 – Install PHPManager & Rewrite</h2>

- Open osTicket-Installation-Files
- Run PHPManagerForIIS
        - Complete the Setup Wizard Prompts
- Run rewrite_amd64_en-US
        - Complete installation

<img width="1128" height="634" alt="step3" src="https://github.com/user-attachments/assets/9dc75170-4171-4625-b4a5-eb09ea67ab88" />

<h2>Step 4 – Create PHP Directory</h2>

- Navigate to C:\ (This PC → Local Disk(C:))
- Create a folder named PHP (Right Click File Explorer → New → Folder)
- Return to osTicket-Installation-Files
- Extract php-7.3.8-nts-Win32-VC15-x86.zip to the folder we just made → C:\PHP

<img width="1139" height="729" alt="step4" src="https://github.com/user-attachments/assets/701875d4-8a93-44ba-8662-afd5c78a9fc2" />

<img width="1114" height="830" alt="step4-2" src="https://github.com/user-attachments/assets/c6b5e04c-86e7-4ddf-ba92-334faac4b358" />

<h2>Step 5 – Install Dependencies</h2>

- Open osTicket-Installation-Files
- Run VC_redist.x86.exe
- Run MySQL 5.6.62
    - Setup Type: Typical
    - Configuration: Standard
    - Run as Windows Service
    - Root password: root (lab only)
 
<img width="1082" height="626" alt="step5" src="https://github.com/user-attachments/assets/8247f2fe-4f77-4fd1-86ed-0ffc9a064aa4" />
    
<img width="497" height="388" alt="step5-2" src="https://github.com/user-attachments/assets/672976b9-fe42-4fe7-aeb0-040f4867d7f1" />

<img width="501" height="378" alt="step5-3" src="https://github.com/user-attachments/assets/e6a08e94-e0d3-4990-82a0-815d9602dc14" />

<h2>Step 6 – Configure PHP in IIS</h2>

- Open IIS Manager (Always open as Administrator)
        - Windows search bar type "IIS"
        - Right Click Internet Information Services Manager
        - Click run as Administrator 
- In IIS open PHP Manager
- Register PHP version: C:\PHP\php-cgi.exe
- Restart IIS
        - Right Click Server name or use the side bar on the right
        - Select Stop
        - Select Start
  
<img width="1224" height="743" alt="step6" src="https://github.com/user-attachments/assets/534bb507-5dc3-48ff-a2d9-4da6b6188029" />

<img width="481" height="350" alt="step6-2" src="https://github.com/user-attachments/assets/11b01ede-5a84-47d3-9d24-5bfed478bf99" />

<img width="457" height="384" alt="step6-3" src="https://github.com/user-attachments/assets/22d5a9ad-bfd6-42a6-934b-1c8f12677e40" />

<h2>Step 7 – Deploy osTicket</h2>

- Open osTicket-Installation-Files
- Extract osTicket-v1.15.8 to default path
- Copy the upload folder to → C:\inetpub\wwwroot
- Rename upload → osTicket
- Restart IIS
- In IIS Connections→ ServerName → Sites - Default WebSite → osTicket select Browse *:80(http)  

You should now be able to see this webpage
<img width="1423" height="746" alt="step7" src="https://github.com/user-attachments/assets/3523f6a0-8b28-4768-8738-90b3df65cbc2" />

<img width="821" height="743" alt="step7-2" src="https://github.com/user-attachments/assets/6a1865c0-2fc8-4bff-b905-643e7e12f690" />

<h2>Step 8 – Enable PHP Extensions</h2>

- In IIS → osTicket → PHP Manager → Extensions: Enable the following
    - php_imap.dll
    - php_intl.dll
    - php_opcache.dll
- Refresh the browser
      
<img width="566" height="300" alt="step8" src="https://github.com/user-attachments/assets/a164539e-7f7f-4d3e-8c6d-95038cc1ee42" />

<img width="347" height="350" alt="step8-2" src="https://github.com/user-attachments/assets/aef05e6e-b528-4385-a12f-fb1c57c7ea4b" />

<img width="362" height="707" alt="step8-3" src="https://github.com/user-attachments/assets/06de298b-6977-4686-8f9d-62e41684b645" />

<img width="828" height="740" alt="step8-4" src="https://github.com/user-attachments/assets/21bdd287-6996-4c3c-a1c8-6f51a8967cf2" />

<h2>Step 9 – Configure ost-config.php</h2>

- In C:\inetpub\wwwroot\osTicket\include
    - Rename: ost-sampleconfig.php → ost-config.php
- Right Click ost-config.php → Properties → Security settings → Advanced
    - Disable inheritance
    - Click Add
    - Grant Everyone – Full Control
 
<img width="954" height="626" alt="step9" src="https://github.com/user-attachments/assets/65c20887-ad4e-4ca3-8549-f9cab6171cda" />

<img width="1174" height="521" alt="step9-2" src="https://github.com/user-attachments/assets/28065eb6-2e1b-4956-9d4c-1e2708832494" />

<img width="757" height="511" alt="step9-3" src="https://github.com/user-attachments/assets/4bc285bf-f3e6-4983-9378-f64c52d0f8ff" />

<img width="913" height="609" alt="step9-4" src="https://github.com/user-attachments/assets/82ac1685-0136-443a-8670-b75bb7656702" />

<h2>Step 10 – Web-Based Setup</h2>

- Click Continue on osTicket setup page
- Fill in: with whatever information you wish:
    - System Settings
    - Admin User
- Database Settings: Use the listed information
    - Database: osTicket
    - Username: root
    - Password: root

 <img width="801" height="631" alt="step10" src="https://github.com/user-attachments/assets/70d452be-28a8-4c23-a71e-3f349b676101" />

<img width="822" height="434" alt="step10-1" src="https://github.com/user-attachments/assets/207969b9-cbaa-4765-88ff-79594635ef1e" />

<h2>Step 11 – Install HeidiSQL</h2>

- Open osTicket-Installation-Files
- Run HeidiSQL_12.3.0.6589_Setup
- Launch HeidiSQL
- Create a new session:
    - Username: root
    - Password: root
 
<img width="933" height="592" alt="step11" src="https://github.com/user-attachments/assets/dc21640e-f90a-46cb-b6e6-740b3685a062" />

<img width="685" height="485" alt="step11-2" src="https://github.com/user-attachments/assets/3967d148-d95c-4d68-91e8-f0b1a4df14f6" />

<img width="971" height="866" alt="step11-3" src="https://github.com/user-attachments/assets/80a7f51e-2ac7-4016-b2ae-4f261674b53d" />

<h2>Step 12 – Cleanup & Security</h2>

- Delete: C:\inetpub\wwwroot\osTicket\setup
- Restrict permissions on ost-config.php 
    - Return to Advanced Security Setting for ost-config.php
    - For "Everyone": remove Full Control and only grant Read access 

<img width="920" height="592" alt="step12" src="https://github.com/user-attachments/assets/d0dd7542-0b61-4ec8-8f64-d6b468802ac4" />

<h2>Step 13 – Congratulations</h2>

<img width="756" height="590" alt="Screenshot 2026-01-28 181304" src="https://github.com/user-attachments/assets/89e09e89-6b0e-449a-bde4-556ac7c33fd1" />


