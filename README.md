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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Install/ Enable Internet and Information Services (IIS) with CGI and common HTTP features
- Download and install PHP Manager for IIS
- Download and install the Rewrite Module
- Download PHP 7.3.8
- Download and install VC_redist.x86.exe
- Download and install MySQL 5.5.62
- Install osTicket v1.15.8
- Download and install HeidiSQL
- Configured permissions and installed osTicket

<h2>Installation Steps</h2>

Step 1: Create a resource group in Azure

![image](https://github.com/user-attachments/assets/2aa40b7e-0854-4fc1-9a69-aafb2cdcdba3)



Step 2: Create a Windows 10 Pro Virtual Machine (VM)

- Select the Resource group that was created
- VM name: VM-osTicket
- Select US East or US West region
- For Availability options, select 'No infrastructure redundancy required'
- For Security type select 'Standard'
- Image: Windows 10 Pro
- Size: 2 or 4 Virtual CPUs (vcpus)
- Choose your username and password
- Check the box for Licensing
- Click Review + Create

![image](https://github.com/user-attachments/assets/f1a077bc-ef3b-47dd-8a11-187f0bf5d15e)
![image](https://github.com/user-attachments/assets/c3705967-c33c-4180-8fee-6f644e997b69)
![image](https://github.com/user-attachments/assets/2c5edd52-9b04-47b8-ac6a-1509e27caf2f)



Step 3: Open Remote Desktop Connection App

- Copy and paste the Public IP Address into the Remote Desktop Connection (Wait until the VM finished deploying)
- Click 'Connect'
- Log in with the credentials created during the virtual machine configuration process.
- Select 'Yes' to connect to you VM

![image](https://github.com/user-attachments/assets/10dc140d-ab93-44bd-b9a2-50f29655fe0e)

![image](https://github.com/user-attachments/assets/9fbe25f6-097d-4623-8589-590fb303a0a2)

![image](https://github.com/user-attachments/assets/7666ab74-955b-45a6-8a64-4a7f38ce4da0)



Step 4: Install/Enable IIS in Windows with CGI and Common HTTP features

- Right click on the "start/windows" icon, click run, and enter "control"
- Click on 'Programs'
- Click the blue hyperlink that says 'Turn Windows features on or off"
- Select Internet Information Services (IIS) -> World Wide Web Services -> Application Development Features (click the plus sign to [X] CGI) -> Common HTTP Features (click the plus sign to [X] all.)
- Click 'Ok'

![image](https://github.com/user-attachments/assets/aa138aac-509a-4eaa-a2e6-58643ee7c7c7)



Step 5: Open the Installation files page here -> (https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

- Download and isntall PHP Manager for IIS
- Download and install Rewrite Module
- Download and install PHP 7.3.8
- Download and install VC_redist.x86.exe.
- Download and install MySQL 5.5.62

![image](https://github.com/user-attachments/assets/5a9cf519-4c2b-4459-b3fb-08b85e5ba05b)


Note: When PHP 7.3.8 is finished downloading, create a folder on Windows (C:) and name it 'PHP'-> right click the PHP 7.3.8 file -> Extract all -> Browse -> This PC -> Windows (C:) -> PHP -> Select Folder -> Extract

![image](https://github.com/user-attachments/assets/75da7783-2d2e-4a5b-821c-a76c1a44a598)


Note: When downloading MySQL, choose 'Typical' as your set up type -> continue installation and set up credentials -> select 'Standard Configuration' -> select next -> choose your password (the username will automatically be 'root') -> Execute and finish

![image](https://github.com/user-attachments/assets/883c6fd1-d5df-449f-b45d-0377d21134ee)



Step 6: Open IIS as an Admin

- Click start and type in IIS in the seach bar -> right click on IIS app and click 'Run as administrator'
- Register PHP from within the IIS app
- Click on PHP Manager
- Select blue hyperlink that says 'Register new PHP version'
- Click on PHP Manager -> Register new PHP version -> This PC -> PHP -> php-cgi -> open -> click 'Ok'
- Go back to the home page in the IIS app and click "Restart"

![image](https://github.com/user-attachments/assets/cb1ac83e-3876-412c-aef6-8d32b7bcee8f)

![image](https://github.com/user-attachments/assets/6c482c20-9f65-45e0-9880-d7afa642861a)

![image](https://github.com/user-attachments/assets/89b109e3-048a-405e-82e1-8805e18c51fc)



Step 7: Download and install osTicket v1.15.8

- When the osTicket file has downloaded, open the osTicket file
- Once inside the folder, open another File Explorer (the yellow folder on the taskbar) and go to This PC -> Windows (C:) -> inetpub -> wwwroot
- Once inside the wwwroot folder, drag the "upload" folder within the "wwwroot" folder
- Right click the 'upload' witin the wwwroot folder and rename it "osTicket

![image](https://github.com/user-attachments/assets/964ac7a6-f23f-4795-85c7-b7232472ea22)




Step 8: Go back to IIS app

- Click 'Restart'
- Go to Sites (left margin) -> Default Website -> osTicket ->  click "Browse *:80" (blue hyperlink on in the right margin)
- Webpage to osTicket should open

- ![image](https://github.com/user-attachments/assets/7dffd78e-60f0-4937-adc3-a43646fcaf8c)

- ![image](https://github.com/user-attachments/assets/5a12fda6-e015-40a4-8fe9-e098db574823)


Note: If the webpage gives you an error, something was done wrong



Step 9: Enable extentions

- Go back to IIS app -> Sites -> Default Website -> osTicket
- Double click on PHP Manager
- Click the blue hyperlink that says 'Enable or Disable an extension'
- Enable (right click each to enable): php_imap.dll, php_intl.dll, and php_opcache.dll
- Refresh osTicket webpage in order to review the enabled extentions


![image](https://github.com/user-attachments/assets/0b59570a-c930-4872-a6c1-112b0b19ba8a)

![image](https://github.com/user-attachments/assets/dc0bb727-40d3-4ab2-ad51-f71da12e3b2f)

![image](https://github.com/user-attachments/assets/c11f6479-8138-4daa-8fdd-af89865643a8)

![image](https://github.com/user-attachments/assets/a092b1bb-b711-4c85-9572-faa3c237d60f)



Step 10: Rename ost-sampleconfig.php

- Go to the wwwroot folder in File Explorer
- Click on osTicket -> include-> scroll to find 'ost-sampleconfig.php' and rename it 'ost-config.php' (simply remove the word 'sample')
- Right click ost-config.php -> click Properties -> click Security (tab at the top) -> click Advanced -> click Disable inheritance -> click pop up hyperlink that says 'Remove all inherited permissions-> click Add -> Select Principle -> type 'Everyone' in the object name field -> click Ok -> click 'Full Controll' -> click ok -> click Apply and then Ok


![image](https://github.com/user-attachments/assets/7ea2f178-2e7e-477f-9468-16973cfda20b)



Step 11: Continue Setting up Osticket (click 'Continue' at the bottom

- Help Desk Name: Tammy Help Desk
- Email: tammy@helper.com (Receives email from customers)
- Name: Tammy
- Last name: Hooker
- Email address: tammy@gmail.com (can be any mail address)
- Username: tammyh
- Password: Choose your ownn
- Download and install HeidiSQL
- Open HeidiSQL will
- Click 'New' at the bottom left,
- Enter root password that was created when we downloaded MySQL
- Connect to the session
- Create a database called 'osTicket' in Heidi SQL -> right click where it says 'Unnamed' in bold -> Create New -> Database -> type 'osTicket' in the Name field
- Continue on to the Database Settings on the osTicket webpage:
  - MySQL Database: enter 'osTicket' (database we just created in HeidiSQL)
  - MySQL Username: root
  - MySQL Password: Password that was created when we downloaded MySQL
  - Click 'Install Now!'


![image](https://github.com/user-attachments/assets/194d4123-f66f-4bff-bee0-d7ab6a9485d6)

![image](https://github.com/user-attachments/assets/5e9fb72a-f22e-4b14-a7bd-9f5e993f6a4c)

![image](https://github.com/user-attachments/assets/0527d033-ae07-46f0-8af9-74754881a201)

![image](https://github.com/user-attachments/assets/8cd69cb6-ceff-48c3-8060-4f0b459e2d90)



Congratulations, osTicket has been installed successfully!


![image](https://github.com/user-attachments/assets/5da4a6cf-ca01-406c-9cc0-22564ffbf592)




Step 12: Clean up

- Go to Files Explorer
- Go to Windoows (C)-> inetpub -> wwwroot -> osTicket -> setup (right click and delete)
- Set Permissions to 'Read' only: Go to Windoows (C)-> inetpub -> wwwroot -> osTicket -> include -> ost-config.php -> right click and go to Properties -> Security -> Advanced -> Double click 'Everyone' -> deselect 'Full control' , 'Modify' , and 'Write' -> click 'Ok' and Apply




Step 12: Test your osTicket log in credentials

- Click on http://localhost/osTicket/scp under 'Your Staff Control Panel'
- Enter log in credentials
- Congrats, you have successfully logged into osTicket!




![image](https://github.com/user-attachments/assets/b4f5bb98-8bd8-421c-add2-a2a16f117081)




- 




  
