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

- Windows 11</b> (52H2-PRO)

<h2>List of Prerequisites</h2>

- Microsoft Azure account
- Windows 11 Virtual Machine
- Remote Desktop Client
- Internet Information Services (IIS)
- <a href="https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0">osTicket Installation Files Package</a>

<h2>Step 1 – Download osTicke</h2>

- Download osTicket Installation Files Package
- Extract the files to the default path
<img width="1144" height="730" alt="step1" src="https://github.com/user-attachments/assets/5f1e1f02-8b42-4101-bb8d-77c5df1ae34d" />

<h2>Step 2 – Enable IIS</h2>

- Press Win + R
- Type "optionalfeatures"
- Enable "Internet Information Services"
- Enable Internet Information Services -> World Wide Services -> Application Development Features -> CGI
  
<img width="689" height="700" alt="step2" src="https://github.com/user-attachments/assets/b958c399-0517-4d71-b69b-47c7f8bbbbaf" />

- Click OK
- Restart Computer

<h2>Step 3 – Install PHPManager & Rewrite</h2>

- Open osTicket-Installation-Files
- Run PHPManagerForIIS
- Complete the wizard
- Run rewrite_amd64_en-US
- Complete installation
<img width="1128" height="634" alt="step3" src="https://github.com/user-attachments/assets/9dc75170-4171-4625-b4a5-eb09ea67ab88" />

<h2>Step 4 – Create PHP Directory</h2>

- Navigate to C:\
- Create a folder named PHP
<img width="1139" height="729" alt="step4" src="https://github.com/user-attachments/assets/701875d4-8a93-44ba-8662-afd5c78a9fc2" />

- Extract php-7.3.8-nts-Win32-VC15-x86.zip to C:\PHP
<img width="1114" height="830" alt="step5" src="https://github.com/user-attachments/assets/c6b5e04c-86e7-4ddf-ba92-334faac4b358" />
(PHP 7.3.8 is used for osTicket compatibility in this lab and is not recommended for production.)

<h2>Step 5 – Install Dependencies</h2>

<img width="1082" height="626" alt="step6" src="https://github.com/user-attachments/assets/8247f2fe-4f77-4fd1-86ed-0ffc9a064aa4" />

- Run VC_redist.x86.exe
- Install MySQL 5.6.62
    - Setup Type: Typical
    - Configuration: Standard
    - Run as Windows Service
    - Root password: root (lab only)
    
<img width="497" height="388" alt="step6-2" src="https://github.com/user-attachments/assets/672976b9-fe42-4fe7-aeb0-040f4867d7f1" />

<img width="501" height="378" alt="step6-4" src="https://github.com/user-attachments/assets/e6a08e94-e0d3-4990-82a0-815d9602dc14" />

<h2>Step 6 – Configure PHP in IIS</h2>

- Open IIS Manager as Administrator
- Open PHP Manager
- Register PHP version: C:\PHP\php-cgi.exe
- Restart IIS (Stop then start server)
  
<img width="1224" height="743" alt="step7-2" src="https://github.com/user-attachments/assets/534bb507-5dc3-48ff-a2d9-4da6b6188029" />

<img width="481" height="350" alt="step7-3" src="https://github.com/user-attachments/assets/11b01ede-5a84-47d3-9d24-5bfed478bf99" />

<img width="457" height="384" alt="step7-4" src="https://github.com/user-attachments/assets/22d5a9ad-bfd6-42a6-934b-1c8f12677e40" />

<h2>Step 7 – Deploy osTicket</h2>

- Extract osTicket-v1.15.8
- Copy the upload folder to: C:\inetpub\wwwroot
- Rename upload → osTicket
- Restart IIS
- In IIS Connections-> ServerName -> Sites - Default WebSite -> osTicket select Browse *:80(http)  
<img width="1423" height="746" alt="step9" src="https://github.com/user-attachments/assets/3523f6a0-8b28-4768-8738-90b3df65cbc2" />

- You should now be able to see this webpage
<img width="821" height="743" alt="step9-2" src="https://github.com/user-attachments/assets/6a1865c0-2fc8-4bff-b905-643e7e12f690" />

<h2>Step 8 – Enable PHP Extensions</h2>

- In IIS → osTicket → PHP Manager → Extensions: Enable:
    - php_imap.dll
    - php_intl.dll
    - php_opcache.dll
 <img width="362" height="707" alt="step9-5" src="https://github.com/user-attachments/assets/06de298b-6977-4686-8f9d-62e41684b645" />

<img width="470" height="407" alt="step9-4" src="https://github.com/user-attachments/assets/aef05e6e-b528-4385-a12f-fb1c57c7ea4b" />
<img width="491" height="260" alt="step9-3" src="https://github.com/user-attachments/assets/a164539e-7f7f-4d3e-8c6d-95038cc1ee42" />


- Refresh the browser

<img width="828" height="740" alt="step9-6" src="https://github.com/user-attachments/assets/21bdd287-6996-4c3c-a1c8-6f51a8967cf2" />


