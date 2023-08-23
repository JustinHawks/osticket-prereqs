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

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- PHP Manager for IIS
- Rewrite Module
- PHP 7.3.8
- VC_redist.x86
- MySQL 5.5.62
- HeidiSQL

<h2>Installation Steps</h2>

1. Begin deploying a Virtual Machine in Microsoft Azure. Name the resource group "RG_osTIcket". Name the virtual machine "VM-osTicket".

![01_sel_rggroup_name_vm](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/7ce2fef3-fdef-4aa4-8358-3e311b7a4141)

2. Set the image of the VM to Windows 10 Pro, version 22H2. Select a size with a minimum of (2) vcpus and 16 GiB memory.
   
![02_sel_os_size](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/8ed6d864-e617-4120-835d-4f9b54eed3c4)

3. Create a username and password for the VM.

![03_un_pw](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/67f8b4a8-f031-4f39-8cc8-b87f16594b69)

4. Check the Windows 10/11 licensing confirmation.

![04_oslicensing](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/556abb3d-0ff8-4ecb-bcd9-4fb8be19b8f2)

5. Go over the Virtual Network, Subnet, and public IP settings. In this case, the default settings that Azure generates will work Click "Review + create".

![05_vm-networking](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/0764ecec-7ff6-4b4d-83e4-54ee1e0ed746)

6. If the VM deploys successfully, you will see this information on your screen.
   
![06_createvm_complete](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/12a03cc6-d00d-47af-80d3-bd6f0d18fd79)

7. To remote into the VM, find and copy the Public IP Address in the Overview section.
   
![07_vm_pub_ip](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/57fc8f85-4262-498e-b8d4-fc75668df2fb)

8. Run "Remote Desktop Connection" on the local PC. Paste the public IP address of the VM and click "Connect".
    
![08_rdc_vm](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/3a92ab60-ef2a-4488-a212-2855a796026f)

9. To log into the VM, click "Use a different account".

![09_dif_acct](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/923383c0-1fb4-4e5f-9f89-21962799b8cf)

10. Enter the username and password that was created for the VM (see step 3)

![10_vmlogin](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/a2e43b36-7dbe-4cbf-93f3-6a0cc4e81ce0)

11. Click "Yes" to connect anyway.

![11_yes](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/72566728-497a-467b-ab04-2fddf117b8b8)

12. To enable CGI, run IIS (Internet Information Services) in the VM. Go to Internet Information Services > World Wide Web Services > Application Development Features > CGI. Check the box to enable.

![12_IIS](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/80483023-1ced-498e-a9a3-923afc63f770)

13. To test that the VM is connected to IIS, open an internet browser and search for 127.0.0.1. The IIS homepage will appear if there is a connection.

![13_test_IIS](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/4dca8158-a62f-485d-9c5e-5f1ecce6c593)

14. Download and install "PHP Manager for IIS".
    
![14_install_PHPManagerforISS](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/a1563498-1e0e-4b4f-8851-00e308440b7f)

15. Download and install "IIS URL Rewrite Module 2"

![15_install_rewritemodule](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/7160bc7e-c17c-43c9-acb9-f02d54322520)

16. Create a directory called "PHP" on the C:\ drive.

![16_create_dir_php](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/b2af7c9c-0ac4-4fde-a008-fbded07c9664)

17. Download "PHP 7.3.8". Extract contents into C:\PHP.

![17_extractPHP](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/7f5a2c90-27c5-413a-835c-af21b7af6c8a)

18. Download and install "Microsoft Visual C++ 2015-2022 Redistributable".
    
![18_install_VCredist](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/e8e7a7c2-8e03-4694-b9c4-07079cb7f05a)

19. Download and install "MySQL Server".

![19_MySQL](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/77785612-71ad-4eff-823c-195c8b5338ce)

20. Set up a new root password for the MySQL Server Instance.

![20_MySQL_security](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/c02548f4-7cb4-45a1-b931-89905ac96852)

21. Open IIS as an admin. Select "PHP Manager"

![21_IISManager](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/c328a733-d414-4f1b-98d8-570ec10b96e0)

22. Select the file called "php-cgi"

![23_IIS_phpcgi](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/d9cb4547-d757-4bce-87ae-ac00a60208f3)

23. Restart the server.

![24_IIS_restart](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/385354e9-2dd4-4f5d-91e9-26eca70c9f1a)

24. Download "osTicket". Extract and copy the "upload" folder to C:\inetpub\wwwroot. Within C:\inetpub\wwwroot, rename the "upload" folder to "osTicket".
    
![25_uploadfolder_cinetpubroot](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/22ac2f50-e485-447d-befb-607580746ccb)

![26_renameupload_osTIcket](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/9ac0c535-a63c-4e54-b0d1-9e3eb5dab36e)

25.  In the IIS connections menu navigate VM-osTicket > Sites > Default Web Site > osTicket. Test that the osTicket installer is connected to the server by clicking "Browse *:80 (HTTP) in the Manage Folder menu.

![27_ISS_sites_Default_osTIcket_browse80](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/c2afd327-1af6-4fa3-bb30-8d0ef2e8de91)

26. The osTicket installer interface will appear. There are more prerequisites that need to be enabled before continuing the installation.

![28_showsextenstionsneeded](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/5dab1fd5-acd9-4c4f-9c27-ddada4db54a4)

27.  Go back to ISS > VM-osTicket > Sites > Default Web Site > osTicket. Double-click the PHP manager in the middle window. Click “Enable or disable an extension”. Enable: php_imap.dll. Enable: php_intl.dll. Enable: php_opcache.dll. Refresh the osTicket site in your browser and observe the changes.

![29_ISS_enablephpextensions](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/bae857bd-3860-414d-8be7-a98afbdbc440)

28. In the File Explorer navigate to C:\inetpub\wwwroot\osTicket\include. Rename the file "ost-sampleconfig.php" to "ost-config.php"

![30_rename_ostconfig php](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/651b8c5e-d62e-49e8-9fd8-e2a3c5881990)

29. Right-click "ost-config.php" and navigate to the advanced security settings. Disable inheritance -> Remove All
New Permissions -> Everyone -> All

![31_ostconfig_disableinheritance](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/4e08bc4e-c759-45c0-a756-7dc428290d4f)
![32_setpermissions_everyone](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/9949ed7f-1fa4-4f7a-9042-5c4286feecea)
![33_fullcontrol](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/b78e7fee-7648-41d5-a5bb-54a06164b78a)

30. Go back to the browser and click continue in the osTicket installer. Enter a name and default email for the Helpdesk. Enter credentials for the admin user osTicket.
    
![34_osticket_credentials](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/3b4979f5-04fb-4d1c-877a-267d26cf7728)

31. Download and install "HeidiSQL".
    
![35_install_HeidiSQL](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/21e8093d-e545-45a7-adfd-bc33114b1c0a)

32. Create a new session. Name the User, "root". Create a password.
    
![36_new_credentials](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/3b6cbb83-6ff5-4f13-9b10-1a4736772b85)

33. Create a new database called "osTicket". Enter the name and password for the MySQL Instance set in step 20.
    
![37_connectiontoMySQLserver](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/e15d99c7-5b4f-4230-86bd-f2d06fc53d41)
![38_create_database_osticket](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/845106cc-414d-48b4-984a-80041afde2c0)
![39_enter_database_settings_credentials_installosticket](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/c5c95750-4f5e-4d3a-b60c-606619564b6f)

34. Go back to the browser and continue installing osTicket. Enter the MySQL credentials. MySQL Database: osTicket, MySQL Username: root, MySQL Password: Password1. Click "Install Now!"

![40_osticket_installed](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/3630f4f5-72f6-4017-935a-d19d0e1c0728)

35. There will be no errors if the installation was successful.
![40_osticket_installed](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/58ef2b7d-839c-4180-b296-2471beba9b06)

36. Access the osTicket Help Desk login page for Admins and Agents: http://localhost/osTicket/scp/login.php.
37. Access the os TIcket login page for End Users: http://localhost/osTicket/ 

![42_testosticket_admin_user_portals](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/22bf29c0-d901-4b7b-9118-e301d9a7b7b5)

38. To clean up the security settings for osTicket, go to the File Explorer and navigate to C:\inetpub\wwwroot\osTicket. Delete the "setup" folder. Navigate to C:\inetpub\wwwroot\osTicket\include\. Set Permissions to “Read” only: for the file called "ost-config.php"

![41_cleanup_readonly_ostconfig](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/68edd350-572e-4a6c-a243-6dd9fbe8a4a6)

39. Congratulations! You have successfully installed osTicket! Log in to the help desk to begin the post-installation setup!

![43_login_admin](https://github.com/JustinHawks/osticket-prereqs/assets/88342524/91fe335e-6a33-4f52-8b8b-3cb7f441d392)







    


