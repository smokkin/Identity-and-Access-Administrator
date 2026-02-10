# Microsoft Entra ID User Role Management Lab Work
Understanding (Manage User Roles) centred on administering user identities and permissions within Microsoft Entra ID. The scenario shows that an organisation has onboarded a new staff member designated as an application administrator. Consequently, the task entails provisioning a new user account and allocating their required role to help with their responsibilities.
The lab was carried out within a Microsoft 365 E5 tenant environment, it shows the process of user creation, authentication protocols, and role-based access control (RBAC). Entra ID makes sure users can only do tasks that fit their roles, thereby mitigating security risks and upholding compliance standards.

Microsoft Entra ID is a cloud service for managing user accounts, groups, and apps safely. From Microsoft docs, making a new user means giving a unique name (UPN) and display name. You can auto-make a password for better security. Users change it on first login to avoid risks.
The Application Administrator role lets users fully manage apps and registrations, like updating details and permissions. This role covers the whole directory and gives access to all apps. It's good for sharing admin tasks but must be given carefully to avoid easy access.
Logging in uses self-service password reset (SSPR), so users can fix expired passwords themselves. Without the right roles, users get blocked, as shown in the lab. This follows the idea of giving only needed access.
The Entra App Gallery has ready-made apps for easy single sign-on (SSO) and setup. Trying to make custom apps needs higher permissions, showing Entra ID's strong controls.

This lab validates the role assignment hierarchy in Entra ID by creating a user with Application Administrator role and confirming that:
The role cannot create custom enterprise applications (requires Global Admin or Application Developer role)
The role cannot modify tenant-wide consent settings (requires Global Admin)
The role can manage existing application registrations and service principals
: This shows that Entra ID limits actions without roles.

# Step-by-Step Walkthrough 
Exercise 1: Create New User & Test Application Admin Rights

# Task 1: Add a New User

- Initiate Global Administrator Session: Access the Microsoft Entra admin center at https://entra.microsoft.com using your Microsoft 365 admin credentials. This step authenticates you with elevated privileges necessary for user management.
- Navigate to User Management: Expand the Entra ID section in the left-hand menu if collapsed. Under Users, select All Users, then click + New User followed by Create new user. This interface allows for bulk or individual user additions, streamlining onboarding.
- Configure User Details: Inputed the following attributes: - User Principal Name: ChrisG - Display Name: Chris Green
- Retained the Auto-generate password option to produce a temporary credential, which bolsters security by mandating an immediate reset.
- Create New User Form, which shows fiels to fill in Identity and password generation.
- Record Temporary Password: Duplicate the generated password for subsequent use. This generated credential expires upon first login, enforcing a personalised reset.
- Finalize Creation: Proceed to Review + Create, then confirm by selecting Create. The system registers the user, integrating them into the directory.Updated Users List After Creation
- The screenshots below confirms the user addition, displaying Chris Green in the roster with details like user type and sync status.
  
<img width="440" height="230" alt="image" src="https://github.com/user-attachments/assets/3c206c6e-7705-490d-9000-0f5899592bef" /> <img width="440" height="230" alt="image" src="https://github.com/user-attachments/assets/4eb0f7f3-9bb5-46c7-a831-ab9eb82f43db" /> <img width="440" height="230" alt="image" src="https://github.com/user-attachments/assets/7cf2a0e6-4ace-4ea6-a364-aed1352c1c15" />

# Task 2: Login and Try to Create an App

This task validates the user's baseline permissions, demonstrating Entra ID's role enforcement by attempting privileged actions without the Application Administrator role assigned.

- Launched an Isolated Browser Session: Opened an InPrivate window to simulate a dfferent user context, preventing session overlap.
- Authenticate as New User:
  - Navigate to https://entra.microsoft.com and sign in with:
  - Username: ChrisG@ Entra domain
  - Password: The auto-generated value from Task 1.
- New User Sign-In Prompt:
  captures the initial login screen for Chris Green.
  Execute Password Reset: Update the password as prompted, given it's the first sign-in or could be due to expiration.
  
  <img width="440" height="230" alt="image" src="https://github.com/user-attachments/assets/dec01c57-6e6b-4089-83d6-5aabeff38dab" /> <img width="440" height="230" alt="image" src="https://github.com/user-attachments/assets/e22987b3-5662-496a-ace6-efa4fc717631" />
  
   - Current Password: Auto-generated value
   - New Password: A unique string
   - Confirm: Re-enter the new password
  
  <img width="440" height="230" alt="image" src="https://github.com/user-attachments/assets/8b6e2940-04aa-43d1-a182-0563b02b690c" />

- This enforces security by requiring a change on first login.
- Accessed Enterprise Applications: Searched for and selected Enterprise applications. I Observe the gallery of integrated apps, such as AWS and Google Cloud.Enterprise Applications Gallery
- This displays the app gallery, where pre-integrated SaaS apps are browsable, but creation is restricted.
- Attempted Application Creation: Click + New application. Note that + Create your own application is greyed out, illustrating permission limitations.
- This shows registered enterprise apps, confirming visibility but no creation rights.
  
  <img width="440" height="230" alt="image" src="https://github.com/user-attachments/assets/5c0fc679-3746-476e-9332-30ffa31d7e06" /> <img width="440" height="230" alt="image" src="https://github.com/user-attachments/assets/4b4f5d57-eb68-4596-808e-6f88e658c40c" />
  
- Tested for Additional Privileges: Navigated to settings > Consent and permissions or User settings. Encountered access denials, confirming the absence of administrative rights.Access Denied in Consent Settings.
- This error page (401 unauthorised) exemplifies RBAC restrictions on sensitive areas.
  
  <img width="440" height="230" alt="image" src="https://github.com/user-attachments/assets/f042e594-564b-4dc3-b0ff-4e96cac00c0a" />


# Step-by-Step Guide: Assigning the Application Administrator Role in Microsoft Entra ID
This lab exercise demonstartes the principle of least-privilege access control in Microsoft Entra ID, by assigning the Application Administrator role to a user named Chris Green, allowing them to manage applications without full Global Administrator rights.

- The Application Administrator role provides targeted permissions:
  - Create and manage enterprise applications and app registrations.
  - Configure application proxy settings.
  - Consent to most delegated permissions and some application permissions.
  - Add and manage application credentials (secrets/certificates) — enabling the app to authenticate as itself.
It limits broader actions like managing users, groups, or conditional access policies. This follows security best practices by granting only necessary permissions.
The ket dfference is that Cloud Application Administrator offers similar permissions plus consent on behalf of all users and user assignments to apps. Application Administrator cannot do those.
Privileged Identity Management (PIM): In tenants with Microsoft Entra ID P2, PIM enables just-in-time or time-bound roles. Assignments may be "Eligible" (requires activation) rather than permanent "Active".

# Task 1: Assign the Application Administrator Role to Chris Green
Using Microsoft Entra ID, organizations can designate limited administrators to manage specific identity tasks. This prevents "admin bloat" and secures the environment by ensuring users only have the permissions they need.
 - Log in to the Microsoft Entra admin center with your administrator account.
 - In the left-hand menu, navigate to Identity > Users > All users.
 - Locate and select the account for Chris Green.
<img width="450" height="271" alt="image" src="https://github.com/user-attachments/assets/5acefaf1-fd49-419a-9877-b518aedac670" />

 - Once in Chris Green's profile, select Assigned roles from the Manage menu.
 - Select the + Add assignments button at the top of the page.
<img width="450" height="271" alt="image" src="https://github.com/user-attachments/assets/8b25de40-1500-4e2a-8196-e08a1448d282" />

 - Configure Role Details and PIM - In the Select role dropdown or search box, find and select Application administrator.
<img width="450" height="271" alt="image" src="https://github.com/user-attachments/assets/b30e3671-4ae4-4764-b9c8-16a0655707c0" />

 - Select Next to move to the assignment settings.
 - Set the Assignment Type to Active.
 - Justification: In the text box, enter a reason such as "Needed for lab".
 - Note: If your environment uses Privileged Identity Management (PIM), you may need to specify if this is a "Permanent" or "Eligible" assignment
<img width="450" height="271" alt="image" src="https://github.com/user-attachments/assets/ade67952-1178-4aa6-b02b-d88ebd54a1fa" />

 - Select Refresh to verify that the role now appears in the user's active assignments
<img width="450" height="271" alt="image" src="https://github.com/user-attachments/assets/905ca7bf-4cc6-4dfa-9418-afc82f451957" />

# Task 2: Verifying Permissions as the New Admin
After delegating a role, it is a best practice to verify that the user can actually perform the intended tasks but remains restricted from others.
 - Go to https://entra.microsoft.com and log in as Chris Green.
 - Username: ChrisG@entradomain.com.
 - Password: Used the secure password created for this user.

 - Search for and select Enterprise applications from the top search bar or the left menu.
 - Observe that the + New Application button is now clickable (it would be grayed out if role is not yet appproved has shown in previous exercise).

<img width="450" height="271" alt="image" src="https://github.com/user-attachments/assets/66f4b748-7523-4206-ac2f-2f2c1bde88a0" /> <img width="450" height="271" alt="image" src="https://github.com/user-attachments/assets/85e7d75a-b50d-4071-bf07-bb587a551ca0" />

Chris Green now has the specific authority to add and manage applications within the tenant without having broad access

Remove a role assignment
Task 1 - Remove the application administrator from Chris Green
This task will use an alternative method to remove the assigned role; it will use the Roles and administrators option in Micrisoft Entra ID.

If you are not already logged in as an Admin, launch the Microsoft Entra admin center and log in now.
In the search box type Roles and then launch Microsoft Entra ID roles and administration.
In All roles of Roles and administrators, select the Application administrator role from the list.
On the Application administrator | Assignments page you should see Chris Green's name listed.
Scroll all the way to the right on Chris Green.
Select Remove from the options at the top of the dialog.
Answer Yes when the confirmation box opens.
<img width="1426" height="769" alt="image" src="https://github.com/user-attachments/assets/dfccf7fd-30a2-46ce-a0bc-6a6092b57993" />
<img width="1429" height="776" alt="image" src="https://github.com/user-attachments/assets/8c845cc1-d998-4af8-b310-55b98055f280" />
<img width="1430" height="773" alt="image" src="https://github.com/user-attachments/assets/429ac02b-6994-4aa0-a086-ea79b8862724" />
<img width="1428" height="774" alt="image" src="https://github.com/user-attachments/assets/3960b40e-6c90-4ad7-adc3-4281f3b1f7a6" />
<img width="1429" height="772" alt="image" src="https://github.com/user-attachments/assets/f1d6fd48-4729-4b06-ae06-67b4b119e76f" />

Exercise 4 - Bulk import of users
Task 1 - Bulk operations for creating users with a .csv file
In the Microsoft Entra ID menu, first open Identity, then select Users and then select All users.

On the Users | All users tile, select the Bulk operations drop-down arrow and then Bulk create.

Selecting Bulk create will open a new tile. This tile provides a Download link to a template file that you will edit to populate with your user information and upload to add the bulk creation of users.

Select Download to download the .csv file.

The .csv template provides you with the fields included with the user profile. This includes the required username, display name, and initial password. You can also complete optional fields, such as Department and Usage location, at this time. The following screenshot is an example of how you can complete the .csvfile:

Bulk import using csv file entry

You can modify this file to add users in bulk. Note that you do not need to fill out all the field. As per the sample data provide, you mainly need to add the name and username information.

A sample CSV has been provided in the Allfiles/Labs/Lab1 folder -- SC300BulkUser.csv.

Open Notepad.
Inside the lab environment, select the START button and type Notepad.
Open the SC300BulkUser.csv file
Change the enter your domain name to the domain of your Azure lab environment.
Save the file.
On the Bulk create users dialog, select the file folder icon on step 3.

Path to the Allfiles/Labs/Lab1 folder and select SC300BulkUser.csv file.

Select Open.

You will be notified that the file uploaded successfully.  Choose Submit to add the users.

After the users have been created, you will be prompted that the creation has succeeded. Close the Bulk create users tile and the new users will be populated in the list of Users | All users.
<img width="1434" height="775" alt="image" src="https://github.com/user-attachments/assets/3c8f3a6f-7b03-42a4-bcda-3771b23e9c14" />
<img width="1434" height="777" alt="image" src="https://github.com/user-attachments/assets/bc41ca67-d7c3-4419-99c2-35d33844de6b" />
<img width="1431" height="773" alt="image" src="https://github.com/user-attachments/assets/c91c1f91-95f3-4c54-a053-02bdf8124101" />
<img width="1428" height="774" alt="image" src="https://github.com/user-attachments/assets/c9bd0e91-03bc-45a7-aceb-e83264ad7391" />
<img width="1439" height="848" alt="image" src="https://github.com/user-attachments/assets/88fff1e6-d486-4804-a0ba-df77d4d33d10" />
<img width="1429" height="772" alt="image" src="https://github.com/user-attachments/assets/88546490-8807-46f9-8b4d-3f289f195793" />
<img width="806" height="554" alt="image" src="https://github.com/user-attachments/assets/d3cf7155-c7f1-4a19-9587-d1d86f0c761c" />


Task 2 - Bulk addition of users using PowerShell
Open PowerShell.  This can be done by searching for PowerShell in Windows.

Note - You need to have PowerShell version 7.2 or higher for this lab to function. When PowerShell opens you will get a version at the top of the screen, if you are running and older version, follow the instructions on the screen to go to https://aka.ms/PowerShell-Release?tag=7.3.9. Scroll down to the assets section and select powershell-7.3.1-win-x64.msi. When the download has completed, select Open file. Install using all the defaults.

Lab Tip - TouchType does not work with PowerShell well in the lab environment. To work around this issue, you open Notepad in you lab environment. Next use the TouchType feature to place the script into Notepad, then finally use Copy & Paste to put the command into PowerShell. Apologies for this extra step.

You will need to Install the Microsoft.Graph PowerShell module if you have not used it before. Run the following two commands and when prompted to confirm press Y:

TypeCopy
Install-Module Microsoft.Graph -Scope CurrentUser -Verbose
Confirm the Microsoft.Graph module is installed:

TypeCopy
Get-InstalledModule Microsoft.Graph
Next, you will need to login to Microsoft Graph API by running:

TypeCopy
Connect-MgGraph -Scopes "User.ReadWrite.All"
The Edge browser will open and you will be prompted to sign-in. Use the MOD Administrator account to connect. Accept the permissions request; then close the browser window.

To verify that you are connected and to see existing users, run:

TypeCopy
Get-MgUser 
To assign a common temporary password to all new users, run the following command and replace the with the password that you would like to provide to your users.

TypeCopy
$PWProfile = @{
    Password = "<Enter a complex password you will>";
    ForceChangePasswordNextSignIn = $false
}
You are ready to create a new users. The following command will be populated with the user information and run. If you have more than one user to add, you can use a notepad txt file to add the user information and copy/paste into PowerShell.

TypeCopy
New-MgUser `
    -DisplayName "New PW User" `
    -GivenName "New" -Surname "User" `
    -MailNickname "newuser" `
    -UsageLocation "US" `
    -UserPrincipalName "newuser@<labtenantname.com>" `
    -PasswordProfile $PWProfile -AccountEnabled `
    -Department "Research" -JobTitle "Trainer"
Note - Replace labtenantname.com with the onmicrosoft.com name assigned by the lab tenant.
<img width="1122" height="626" alt="image" src="https://github.com/user-attachments/assets/95189cfb-67b5-4b3d-afb6-4c074b8eb189" />
<img width="1426" height="776" alt="image" src="https://github.com/user-attachments/assets/dcba74d0-14f1-4b91-bac1-48b3aebf35f7" />
<img width="1431" height="776" alt="image" src="https://github.com/user-attachments/assets/2780b41e-099f-40ad-93bc-1a26658ef760" />
<img width="1431" height="773" alt="image" src="https://github.com/user-attachments/assets/c8797e6a-f437-4ec1-9b26-ab0202aece1d" />
<img width="1431" height="782" alt="image" src="https://github.com/user-attachments/assets/9f47038d-7503-41be-8f74-5426977bca15" />
<img width="1431" height="777" alt="image" src="https://github.com/user-attachments/assets/5d9e1193-c60c-4d78-9f81-0a962df5d70a" />
<img width="1426" height="809" alt="image" src="https://github.com/user-attachments/assets/6de837bc-123d-48c2-a224-b360d24239fc" />
<img width="1431" height="772" alt="image" src="https://github.com/user-attachments/assets/85bcc244-6e63-4e2b-a1eb-2050eedc0394" />
<img width="1427" height="771" alt="image" src="https://github.com/user-attachments/assets/2797353b-4eb9-4f26-81d6-9c5f8c94a570" />

Experiment with managing users
You can add and remove users with the Microsoft Entra ID page. However, users can be created and roles can be assigned using the scripting. Experiment with giving the Chris Green user account a different role using script.

Exercise 5 - Remove a user from Microsoft Entra ID
Task 1 - Remove a User
It may happen that an account is deleted and then needs to be recovered. You need to verify you can recover an account that has been deleted recently.

Browse to https://entra.microsoft.com.

In the left navigation, under Identity, select Users.

Open the All users list, select the check box for a user that will be deleted. For example, select Chris Green.

Tip - Selecting users from the list allows you to manage multiple users at the same time. If you select the user, to open that user’s page, you will only be managing that individual user.

Screen image displaying the All users users list with one user check box selected and another check box highlighted indicating the ability to select multiple users from the list.

With the user account selected, on the menu, select Delete.

Review the dialog box and then select OK.

<img width="1431" height="774" alt="image" src="https://github.com/user-attachments/assets/35a812cb-f92a-43cb-b262-ba2fa288184d" />
<img width="1430" height="776" alt="image" src="https://github.com/user-attachments/assets/da62db29-fcd0-48bd-b34d-892ead7c4974" />
<img width="1422" height="761" alt="image" src="https://github.com/user-attachments/assets/4cb706f8-b9cd-4c9c-8aa8-1cec68692346" />

Task 2 - Restore a deleted user
In the Users page,select All User in the left navigation, select Deleted users.

Review the list of deleted users and select Chris Green.

Important - By default, deleted user accounts are permanently removed from Azure Active Directory automatically after 30 days.

On the menu, select Restore user.

Review the dialog box and then select OK.

In the left navigation, select All users.

Verify the user has been restored.

<img width="1429" height="771" alt="image" src="https://github.com/user-attachments/assets/dd2cd88e-c4ac-49f7-bd70-bc1049f509af" />
<img width="1430" height="772" alt="image" src="https://github.com/user-attachments/assets/5bf81c26-a288-46a6-b4d5-c8538ea60eb8" />
<img width="1428" height="779" alt="image" src="https://github.com/user-attachments/assets/ca6bf90c-e222-46e1-9205-15c00b67eb15" />

Exercise 6 - Add a Windows 10 license to a user account
Task 1 - Find your unlicensed user in Azure Active Directory
Some user accounts in your organization will not be provided all available products in their assigned license or will need updates or additions to their license assignment. You need to ensure you are able to update a user account's license assignment in Microsoft Entra ID.

Browse to https://entra.microsoft.com.

In the left navigation, under Identity, select Users, then select All users.

In the Users page, enter Raul into the search box.

Select on Raul Razo.

Review Raul's profile and ensure he has a Usage Location set.

Warning - To assign a license to a user, the user must assigned a usage location.

Select the Licenses menu item in the menu on the left.

Ensure that Raul has "No license assignments found."

<img width="1428" height="774" alt="image" src="https://github.com/user-attachments/assets/ecb51cca-0b88-4cb3-8555-846ac1e67c6e" />
<img width="1432" height="773" alt="image" src="https://github.com/user-attachments/assets/5128e32d-e8af-4dd8-8a0d-a7940a5f4194" />

Task 2 - Add a Windows license to Raul
You have to add and remove licenses via the Microsoft 365 admin center. This is a relatively new change.

Open a new tab in your browser.

Connect to the Microsoft 365 admin center at https://admin.microsoft.com.

Log in as your administrator account if prompted.

From the menu on the left, select Billing and then select Licenses.

Select Windows 10/11 Enterprise E3 license from the list.

Choose the + Assign licenses item.

Search for Raul Razo in the list.

Once you have added Raul, select Assign.

Return to the browser tab with Microsoft Entra admin center open.

Navigate back to the All Users in the left navigation, under Identity, select Users

In the Users page, select Raul Razo.

In the left navigation, select Licenses.

Notice that the license has been assigned.

You can exit out of the license screen.

<img width="1433" height="777" alt="image" src="https://github.com/user-attachments/assets/639578fe-5522-4d67-8c63-d190d9abf6f4" />
<img width="1427" height="777" alt="image" src="https://github.com/user-attachments/assets/05ef0bf5-8d60-4b3c-93c6-1e0ee8216d45" />
<img width="1430" height="774" alt="image" src="https://github.com/user-attachments/assets/6ad04dce-9375-452e-b14d-60f42eb983bc" />
<img width="1431" height="771" alt="image" src="https://github.com/user-attachments/assets/a05fa447-dd03-4a25-bdbe-d5a9fdcdd3d1" />
<img width="1433" height="775" alt="image" src="https://github.com/user-attachments/assets/0ec008bc-fa81-4b87-bb82-d967ae8c8a4e" />
<img width="1429" height="771" alt="image" src="https://github.com/user-attachments/assets/3891a58b-ff96-4f50-aa5b-d713f1ae0419" />










