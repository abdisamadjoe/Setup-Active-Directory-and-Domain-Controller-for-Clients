# Active Directory & User Management with PowerShell (Homelab) Walkthrough

  <img src="https://github.com/user-attachments/assets/f594a2ef-64b6-483c-8476-8585356d4226" height="80%" width="80%" alt=""/>

## Description
This project involves setting up a home lab using Oracle VirtualBox to create a network environment with Windows 10 and Windows Server 2019. The lab will utilize Active Directory (AD) for user management, leveraging PowerShell to automate the creation of random users. This setup aims to provide hands-on experience in managing AD, enhancing skills in Windows Server administration, and scripting with PowerShell. Users will learn how to configure AD, implement user policies, and generate user accounts efficiently through PowerShell commands.

## Languages and Utilities Used

- **PowerShell**

## Environments Used 

- **Windows 10**
- **Windows Server 2019**
- **Oracle VirtualBox**

## Requirements
Before we dive in, make sure you have:
- **Oracle VirtualBox**
- **Windows 10 ISO**
- **Windows Server 2019 ISO**

## Step-by-Step Instructions

### Step 1: Set Up Your Environment
Start by installing Oracle VirtualBox on your host machine. This software will allow you to create and manage virtual machines.

### Step 2: Install Windows Server
1. Open VirtualBox and create a new VM:
   - Click on **New** and select **Windows Server 2019** as the version.
   - Allocate memory and disk space as per your requirements.
2. Mount the Windows Server ISO you obtained earlier.
3. Start the VM and follow the installation prompts to install Windows Server.

   **Screenshot**: (Capture the process of creating the VM and the Windows Server installation.)

### Step 3: Add Guest Additions
1. Once the Windows Server installation is complete, install the Guest Additions to improve performance:
   - Go to the VirtualBox menu and select **Devices > Insert Guest Additions CD Image**.
2. Change the server's hostname:
   - Go to **Server Manager > Local Server** and find the **Computer Name** section. Click on **Change**.
3. Set a static IP address on the internal network:
   - Navigate to **Network and Sharing Center**, select **Change adapter settings**, right-click on the network adapter, and select **Properties**. Configure the IP address.

   **Screenshot**: (Show the process of adding Guest Additions, changing hostname, and setting static IP.)

  <img src="https://github.com/user-attachments/assets/73df22f2-7e24-455b-933f-cd51a69a0959" height="80%" width="80%" alt=""/>


<img src="https://github.com/user-attachments/assets/947165b2-e80a-4bcd-8e48-0fd037a4b7c8" height="80%" width="80%" alt=""/>


<img src="https://github.com/user-attachments/assets/9983f264-f5bf-45e4-bde2-3eb4fe916383" height="80%" width="80%" alt=""/>










### Step 4: Configure Server Roles
1. Open **Server Manager**. You will see a dashboard with server information.
2. Click on **Add roles and features** to open the wizard.
3. Select **Role-based or feature-based installation** and choose your server from the server pool.
4. Install the following roles:
   - **DHCP Server**
   - **Routing**

   **Screenshot**: (Include a screenshot of the Server Manager with roles being added.)

### Step 5: Promote to Domain Controller
1. In Server Manager, you will see a notification flag indicating the AD DS role has been installed. Click on it to promote the server to a Domain Controller.
2. Use the **Active Directory Domain Services Configuration Wizard**:
   - Choose to add a new forest and enter **mydomain.com** as the domain name.
3. Complete the wizard and allow the server to restart.

   **Screenshot**: (Capture the promotion process and the configuration steps.)

### Step 6: Configure Remote Access
1. After promoting your server, access **Remote Access Management** from Server Manager.
2. Click on **Configure Remote Access** and proceed with the default options by clicking **Next**.
3. Choose **NAT** for the network topology and select **internal network**.

   **Screenshot**: (Show the Remote Access Management configuration screen.)

### Step 7: Manage Active Directory
1. Open **Active Directory Users and Computers** from the Administrative Tools menu.
2. Create a new IP address scope for the DHCP server and configure it as needed.
3. Add users to **mydomain.com** by right-clicking on the Users container and selecting **New > User**.

   **Screenshot**: (Show the interface of Active Directory Users and Computers, highlighting user creation.)

### Step 8: Test Windows Client Connectivity
1. Open your Windows 10 client VM and check if it’s connected to the **mydomain.com** server.
2. Rename the PC:
   - Go to **System Properties**, click on **Change settings**, and rename it to **Client 1**.
3. Join the domain by entering **mydomain.com** and providing domain credentials.
4. Log in using the user accounts created on the server.

   **Screenshot**: (Capture the Windows login screen showing the two user accounts.)

### Step 9: Automate User Creation with PowerShell
1. Open PowerShell as an administrator on your server.
2. Use the provided PowerShell script to create random users:
   - Download the script from this repository.
   - Run the script to create users automatically in Active Directory.

   **Screenshot**: (Include a screenshot of the PowerShell script in action.)

## Conclusion
Congratulations! You've successfully set up an Active Directory environment and learned how to manage user accounts using PowerShell. This configuration is essential for any network administrator and will enhance your skills in Windows server management.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
Thanks for following along! If you have any questions or feedback, feel free to reach out.


