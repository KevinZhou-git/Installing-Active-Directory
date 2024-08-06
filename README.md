![image](https://github.com/user-attachments/assets/3a9e2e2d-8cd5-4c41-be9c-9f3cb1d4d270)
# Installing Active Directory using Microsoft Azure
This guide will showcase how to install and configure Microsoft Active Directory using virtual machines that were deployed in the cloud via Microsoft Azure. We will be configuring one virtual machine with Windows Server 2022 and running Active Directory on it, while we will create another virtual machine as a Windows 10 client that will be joined to the domain controller to simualate a production machine in a business environment.

## Technologies Used
- Microsoft Azure
- Remote Desktop
- Active Directory Domain Services

## Operating Systems Used
- Windows Server 2022
- Windows 10

## Setting the Domain Controller's IP from Dynamic to Static
- Click on the virtual machine that we installed Windows Server 2022 on.
- Click on Settings -> Network Settings -> Network Interface.
- Click on IP Configurations -> ipconfig1 -> toggle to "Static" and click "Save".
![image](https://github.com/user-attachments/assets/6261ac5c-2d4c-42f5-bc00-4d66aa95ca13)
![image](https://github.com/user-attachments/assets/cc233cd1-2cb9-41ac-823b-1b27bd485175)
![image](https://github.com/user-attachments/assets/75b70122-f24e-4449-99f9-0296e0dc2fef)

## Configuring the Client DNS Settings
- Copy the Private IP Address from our Domain Controller.
- Click on the virtual machine that we installed Windows 10 on.
- Click on Settings -> Network Settings -> Network Interface.
- Click on Settings -> DNS servers -> Custom -> input the IP address we copied earlier and save.
- Restart the virtual machine.
![image](https://github.com/user-attachments/assets/e5b5a9f5-a8db-441c-96a1-48fbfb549721)
![image](https://github.com/user-attachments/assets/73628ba3-220d-47d8-ac7b-ec98ccf6f010)
![image](https://github.com/user-attachments/assets/dd1b6444-2a0a-4c22-9d3e-1fcbcf52690c)

## Logging into the Domain Controller and Configuring Active Directory
- Connect to the Domain Controller using Remote Desktop. Use the login credentials made when creating the virtual machine earlier.
- Click "Add roles and features"
- Click "next" until "server roles". Check "Active Directory Domain Services"
- Click next -> add features -> next -> install. 
![image](https://github.com/user-attachments/assets/be4a757d-ee57-497a-b786-64085b0c721b)
![image](https://github.com/user-attachments/assets/83353a8d-c492-4cbc-8dd9-4be7f4a2b0e3)


## Promoting the Server to a Domain Controller
- Click the hazard icon at the top right, and "promote this server to a domain controller".
- Click "Add a new forest" and give it a domain name as well as a password.
- Click "next" on the following prompts and install.
- The domain controller will lose connection now.
![image](https://github.com/user-attachments/assets/81bfdf88-5156-4333-a9a8-c966b348b75a)
![image](https://github.com/user-attachments/assets/1f9dfacf-529b-4c59-b587-44749a8aba61)
![image](https://github.com/user-attachments/assets/63479ff2-75bb-4b72-af74-3f61858cac3a)

## Test out the Login to the Domain Controller
- Use the the new credentials to try and login.
- Login: mydomain.com/yourusername
- Password: passwordyoumade

- Congratulations you have installed Active Directory using Microsoft Azure virtual machines.
