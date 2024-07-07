<p align="center">
<img width="600" src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5795419a-3012-4a57-b4b0-155c2dd93fc7" alt="Microsoft Active Directory Logo"/>
<br>
<br>



<h1> Configure Virtual Network Connectivity by Using Peering </h1>
<br>

<h2>Understanding the Scenario</h2>

You are a Security Engineer for Hexelo, an organization that needs to configure secure bidirectional communication between Azure virtual networks.

In this Lab, you will configure virtual network connectivity by using peering.
1. First, you will create an Azure virtual network by using the Azure portal.
2. Next, you will create an Azure virtual network by using Azure Cloud Shell.
3. Finally, you will configure virtual network peering connections for secure bidirectional communication.

<br>
<br>

<h2>1️⃣ Create a Virtual Network by using the Azure portal</h2>
<br>
 
On the Azure portal home page, select **Create a resource** to display the Azure Marketplace.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5b9a2405-7215-4592-95f3-363c871949ef" height="80%" width="80%" alt="9"/><br />
<br>

In Search the Marketplace, search for and select ***Virtual Network***, and then select **Create**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/d5bede9d-9732-4c85-8d17-af609b9726fa" height="80%" width="80%" alt="9"/><br />
<br>
  
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/ca90a091-571d-49f1-beed-ddd25755c5c9" height="80%" width="80%" alt="9"/><br />
<br>

On the Create virtual network blade, on the Basics page, in Resource group, select **corp-datalod42226775**, in Virtual network name, enter ***webVNET***, and then select **Next**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/e1696f0a-06fd-4ae4-ae95-3f6c8bfd0507" height="50%" width="50%" alt="9"/><br />
<br>

On the Security page, select **Next**.

On the IP addresses page, in IPv4 address space, select **Delete address space**, and then select **Add IPv4 address space**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/c0524a5f-97cb-478a-bad8-b6fc9236fe7f" height="50%" width="50%" alt="9"/><br />
<br>

For IP address, enter ***10.10.0.0***, and confirm the subnet mask is **/16**.

Select **Add a subnet** to open the Add subnet blade.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/aa430c55-3c00-4b97-b21a-aa572a0f2373" height="50%" width="50%" alt="9"/><br />
<br>

On the Add subnet blade, in Subnet name, enter ***web***, in Starting address, enter ***10.10.0.0***.

In Subnet size, select **/25**, and then select **Add**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/9b7da0cd-748d-4bb3-a77b-c12abd46eb7a" height="50%" width="50%" alt="9"/><br />
<br>

On the Create virtual network blade, select **Review + create**, and then select **Create** to create the virtual network.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/f75b053a-1f8a-4b33-b502-73fa7feba6b3" height="50%" width="50%" alt="9"/><br />
<br>

⚠️You will use this virtual network for the web tier.

<br>
<br>

<h2>2️⃣ Create a Virtual Network by using Azure Cloud Shell</h2>
<br>
 
In the Azure Portal, in the global controls, select the **Cloud Shell** icon.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5b9a2405-7215-4592-95f3-363c871949ef" height="80%" width="80%" alt="9"/><br />
<br>

In Search the Marketplace, search for and select ***Virtual Network***, and then select **Create**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/d5bede9d-9732-4c85-8d17-af609b9726fa" height="80%" width="80%" alt="9"/><br />
<br>
  
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/ca90a091-571d-49f1-beed-ddd25755c5c9" height="80%" width="80%" alt="9"/><br />
<br>

On the Create virtual network blade, on the Basics page, in Resource group, select **corp-datalod42226775**, in Virtual network name, enter ***webVNET***, and then select **Next**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/e1696f0a-06fd-4ae4-ae95-3f6c8bfd0507" height="50%" width="50%" alt="9"/><br />
<br>

On the Security page, select **Next**.

On the IP addresses page, in IPv4 address space, select **Delete address space**, and then select **Add IPv4 address space**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/c0524a5f-97cb-478a-bad8-b6fc9236fe7f" height="50%" width="50%" alt="9"/><br />
<br>

For IP address, enter ***10.10.0.0***, and confirm the subnet mask is **/16**.

Select **Add a subnet** to open the Add subnet blade.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/aa430c55-3c00-4b97-b21a-aa572a0f2373" height="50%" width="50%" alt="9"/><br />
<br>

On the Add subnet blade, in Subnet name, enter ***web***, in Starting address, enter ***10.10.0.0***.

In Subnet size, select **/25**, and then select **Add**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/9b7da0cd-748d-4bb3-a77b-c12abd46eb7a" height="50%" width="50%" alt="9"/><br />
<br>

On the Create virtual network blade, select **Review + create**, and then select **Create** to create the virtual network.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/f75b053a-1f8a-4b33-b502-73fa7feba6b3" height="50%" width="50%" alt="9"/><br />
<br>

⚠️You will use this virtual network for the web tier.


<br>


<h2>Key Objectives</h2>

<h3>🟢 Scenario Simulation</h3>

- Engage in practical simulations of diverse scenarios, such as password resets, group membership changes, and account deactivations.

<h3>🟢 Troubleshooting Scenarios</h3>

- Develop troubleshooting skills by simulating scenarios where users encounter access issues, and learn to identify and resolve these challenges effectively.
<br>

<h2>Environments and Technologies Used</h2>

🔹 Microsoft Azure (Virtual Machines)

🔹 Remote Desktop

🔹 Active Directory Domain Services

<br>

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)
<br>

<h1>Scenarios</h1>

<h3>1️⃣ User Account Creation </h3>
<br>

*<h4>BACKGROUND:</h4>*

- A new software developer, John Smith, has been hired to join the IT department at your company.

- As part of the onboarding process, the IT help desk needs to **Create a New User Account** for John in **Active Directory**.
<br>
<br>


First **Create a New User Account** named *John Smith* with the Username "*john_smith*" and a Temporary Password.

<img width="600" alt="john smith" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/090466f7-bb0a-418d-93de-e24dee6e9418">
<br>
<br>


⚠️ NOTE: Set the Account to ***User must change the password at next logon***.

<img width="600" alt="john smith" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/b04b9990-c04c-4808-9218-498b7b7dac98">
<br>
<br>


Assign John to the "***Developers***" Security Group in Active Directory.

<img width="600" alt="developers" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/08ed3545-24ff-4002-a044-9a75b8edff4c">

<br>
<br>
<br>

Then ensure that **John's Account** is located in the appropriate **Organizational Unit (OU)** for the IT staff (***Developers***):

<img width="600" alt="check" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/ec0f5e0e-f753-49ef-bcd8-429305fdaed0">

<br>
<br>
<br>

➜ Communicate the **Login Credentials** and **Temporary Password** to John through a secure channel.

➜ Document the **Date and Time of Account Creation** for auditing purposes.
  
<br>


*<h4>CONSIDERATIONS:</h4>*

✔ The Temporary Password should meet the Company's Password Policy Requirements.

✔ Ensure that John has the Necessary Permissions and Group Memberships to access the Resources required for his role.

<br>
<br>

<h2></h2>

<h3>2️⃣ Password Reset </h3>
<br>

*<h4>BACKGROUND:</h4>*

- Sarah Thompson, a marketing executive, contacts the IT help desk reporting that she has forgotten her password and is unable to access her computer and email.

- The help desk needs to assist Sarah in **resetting her password in Active Directory**.
<br>
<br>


Locate Sarah's User Account and **Initiate a Password Reset**.

<img width="600" alt="reset password" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/a668a089-e1e1-4b7c-8e2b-f4da359500fb">

<br>
<br>
<br>


Set a temporary password for Sarah that complies with the ***Company's Password Policy***.

⚠️ NOTE: Make sure to click the highlighted boxes to ensure the user’s account is unlocked and enable them to set their own password.

<img width="600" alt="enable acc" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/e3fdffdb-6a67-4019-8c75-320edd7c263b">

<br>
<br>
<br>

➜ Communicate the **Temporary Password** to Sarah through a secure channel and instruct her to **Change it Immediately upon Login**.

➜ Provide guidance on **How to Change the Password** using the company's **Self-service Password Reset Tool** if available.

➜ Document the **Date and Time of Account Creation** for auditing purposes.
  
<br>


*<h4>CONSIDERATIONS:</h4>*

✔ Ensure that the chosen temporary password is strong and complies with the company's password policy.

✔ Remind Sarah to update the password on any additional devices or applications where the old password was saved.


<br>
<br>

<h2></h2>

<h3>3️⃣ Group Membership Update </h3>
<br>

*<h4>BACKGROUND:</h4>*

- Emma Rodriguez, a systems analyst, has recently been promoted to a managerial role within the IT department.

- As part of her new responsibilities, Emma now requires access to specific network resources and project folders.

- The IT help desk needs to **Update Emma's Group Memberships in Active Directory** accordingly.
<br>
<br>


Locate **Emma's User Account** and review her current **Group Memberships**.

<img width="600" alt="Emma " src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/0387d564-7ef7-408d-861f-e55d23cfeee3">

<br>
<br>
<br>


Remove Emma from the "***Systems Analysts***" Group and add her to the "***IT Managers***" Group.

<img width="600" alt="IT managers" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/075f3450-100d-41b3-89e2-2901be595462">

<br>
<br>
<br>


Confirm that Emma now has the **Necessary Access Rights to Specific Network Resources and Project Folders**.

<img width="700" alt="image" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/9f80fb40-a0e4-4feb-9db0-7502a4c95ba9">

<br>
<br>
<br>

➜ Communicate the group membership update to Emma, along with any additional instructions or changes in access.

➜ Document the whole process

➜ Document the **Date and Time of Account Creation** for auditing purposes.
  
<br>


*<h4>CONSIDERATIONS:</h4>*

✔ Ensure that Emma's new group memberships align with her managerial responsibilities.

✔ Communicate the changes to other relevant parties, such as the IT security team, to maintain awareness.

✔ Verify that Emma's access permissions are correctly configured after the group membership update.

<br>
<br>

<h2></h2>

<h3>4️⃣ Account Deactivation </h3>
<br>

*<h4>BACKGROUND:</h4>*

- Mark Johnson, a network administrator, has recently resigned from the company. 

- The IT help desk needs to **Deactivate Mark's User Account in Active Directory** to prevent unauthorized access and ensure the security of company resources.
<br>
<br>


Locate **Mark's User Account** and initiate the **Account Deactivation Process**.</strong></p>

<img width="600" alt="makr" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/81f1cb1f-822f-4cf0-a3ac-6a90bd25ee9d">

<br>
<br>
<br>


**Disable Mark's Account** to prevent further logins while *retaining the account details for reference*.

<img width="600" alt="disable" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/0a5c21de-a440-426e-bd72-ea4db51052b2">

<br>
<br>
<br>


You may receive a confirmation dialog ➜ click "**Yes**" to confirm the **disabling of the User Account**.

<img width="400" alt="disable 2" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/0843f9b2-f8b7-4b4a-8f91-2f771a2fbdad">

<br>
<br>
<br>



**Remove Mark from all Security Groups** to revoke his access to network resources.

<img width="600" alt="remove mark" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/94814d6f-af67-4570-ad8b-7cea15c63e76">

<br>
<br>

➜ Confirm with other relevant departments (e.g. HR) that Mark's departure aligns with **Company Policies** and **Document the Whole Process**.
<br>
<br>

*<h4>CONSIDERATIONS:</h4>*

✔ Ensure a smooth transition of Mark's responsibilities to other team members.

✔ Communicate the account deactivation to other departments, such as HR and security, for coordinated efforts.

✔ Retain Mark's user account details for historical records and potential future reference.
   
✔ Conduct a review of Mark's access rights to identify and update any shared resources associated with his account.

<br>
<br>

<h2></h2>


<h3>5️⃣ Organizational Unit (OU) Management </h3>
<br>

*<h4>BACKGROUND:</h4>*

- The Sales department has recently undergone a reorganization, resulting in the creation of a new team focused on international sales. 

- The IT help desk needs to reflect this change in the **Active Directory** structure by creating a new **Organizational Unit (OU)** for the International Sales team and **moving relevant user accounts into the new OU**.
<br>
<br>


**Create a new Organizational Unit** named "***International Sales***" within the Sales department's organizational structure.

<img width="600" alt="International Sales" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/514f52ad-daa3-4d8f-a518-c32c4efcc509">

<br>
<br>
<br>


Move the user accounts of team members, such as *Alex Turner* and *Maria Sanchez*, to the **newly created OU**.

<img width="600" alt="Alex Turner to IS " src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/a7755794-8a21-4625-93c2-7f2cbe69a785">
<br>

<img width="600" alt="Maria to IS" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/3704b7ac-35c7-4693-8b08-2bfbbc6d088e">

<br>
<br>
<br>


**Verify** that the users now appear under the ***"International Sales" OU*** in Active Directory.

<img width="600" alt="Verify" src="https://github.com/franciscovfonseca/Active-Directory-Practical-Scenario-Simulation/assets/172988970/d872f000-83a6-4efb-b176-fee8e3946cca">

<br>

<br>

➜ Communicate the organizational change to relevant stakeholders, such as department heads and team leaders.
<br>
<br>

*<h4>CONSIDERATIONS:</h4>*

✔ Ensure that the new OU structure aligns with the company's organizational hierarchy.

✔ Confirm that the appropriate Group Policy settings apply to the users within the new OU.
  
✔ Communicate any changes in access permissions or policies resulting from the OU reorganization to the IT security team.

<br>
<br>
<br>


<h2> Final Thoughts </h2>


In summary, **Active Directory** is crucial for Managing User Accounts and Network Resources.


The scenarios provided cover common IT help desk tasks, such as:

- **Creating User Accounts**
- **Resetting Passwords**
- **Updating Group Memberships**
- **Handling Account Deactivation**


These scenarios serve as practical exercises for training IT personnel and highlight the importance of **Active Directory** in Maintaining a Secure and Organized Digital Environment.

<br>
<br>
<br>
<br>
