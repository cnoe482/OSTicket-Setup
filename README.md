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

<h2>Step 1</h2>

- Download osTicket Installation Files Package
- Extract the files to the default path
<img width="1144" height="730" alt="step1" src="https://github.com/user-attachments/assets/5f1e1f02-8b42-4101-bb8d-77c5df1ae34d" />

<h2>Step 2</h2>

- Press Win + R
- Type "optionalfeatures"
- Enable "Internet Information Services"
- Enable Internet Information Services -> World Wide Services -> Application Development Features -> CGI
  
<img width="689" height="700" alt="step2" src="https://github.com/user-attachments/assets/b958c399-0517-4d71-b69b-47c7f8bbbbaf" />

- Click OK
- Restart Computer

<h2>Step 3</h2>

- Open osTicket-Installation-Files
- Run PHPManagerForIIS
- Complete the wizard
- Run rewrite_amd64_en-US
- Complete installation
<img width="1128" height="634" alt="step3" src="https://github.com/user-attachments/assets/9dc75170-4171-4625-b4a5-eb09ea67ab88" />

<h2>Step 4</h2>

- Navigate to C:\
- Create a folder named PHP
<img width="1139" height="729" alt="step4" src="https://github.com/user-attachments/assets/701875d4-8a93-44ba-8662-afd5c78a9fc2" />

- Extract php-7.3.8-nts-Win32-VC15-x86.zip to C:\PHP
<img width="1114" height="830" alt="step5" src="https://github.com/user-attachments/assets/c6b5e04c-86e7-4ddf-ba92-334faac4b358" />
(PHP 7.3.8 is used for osTicket compatibility in this lab and is not recommended for production.)


