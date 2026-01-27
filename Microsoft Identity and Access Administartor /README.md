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


<img width="1431" height="773" alt="image" src="https://github.com/user-attachments/assets/c91c1f91-95f3-4c54-a053-02bdf8124101" />
<img width="806" height="554" alt="image" src="https://github.com/user-attachments/assets/d3cf7155-c7f1-4a19-9587-d1d86f0c761c" />

<img width="1122" height="626" alt="image" src="https://github.com/user-attachments/assets/95189cfb-67b5-4b3d-afb6-4c074b8eb189" />
<img width="1133" height="644" alt="image" src="https://github.com/user-attachments/assets/5fe88e07-30f0-4482-bd69-28c6342661cb" />
<img width="1126" height="638" alt="image" src="https://github.com/user-attachments/assets/4f5924c0-3996-427d-851d-8a43c1ebf27d" />
<img width="1426" height="769" alt="image" src="https://github.com/user-attachments/assets/39a2a4fe-6e52-46f1-8523-1d3d9431368d" />


<img width="1431" height="774" alt="image" src="https://github.com/user-attachments/assets/35a812cb-f92a-43cb-b262-ba2fa288184d" />
<img width="1430" height="776" alt="image" src="https://github.com/user-attachments/assets/da62db29-fcd0-48bd-b34d-892ead7c4974" />
<img width="1422" height="761" alt="image" src="https://github.com/user-attachments/assets/4cb706f8-b9cd-4c9c-8aa8-1cec68692346" />

<img width="1429" height="771" alt="image" src="https://github.com/user-attachments/assets/dd2cd88e-c4ac-49f7-bd70-bc1049f509af" />
<img width="1430" height="772" alt="image" src="https://github.com/user-attachments/assets/5bf81c26-a288-46a6-b4d5-c8538ea60eb8" />
<img width="1428" height="779" alt="image" src="https://github.com/user-attachments/assets/ca6bf90c-e222-46e1-9205-15c00b67eb15" />

<img width="1428" height="774" alt="image" src="https://github.com/user-attachments/assets/ecb51cca-0b88-4cb3-8555-846ac1e67c6e" />
<img width="1432" height="773" alt="image" src="https://github.com/user-attachments/assets/5128e32d-e8af-4dd8-8a0d-a7940a5f4194" />

<img width="1433" height="777" alt="image" src="https://github.com/user-attachments/assets/639578fe-5522-4d67-8c63-d190d9abf6f4" />
<img width="1427" height="777" alt="image" src="https://github.com/user-attachments/assets/05ef0bf5-8d60-4b3c-93c6-1e0ee8216d45" />
<img width="1430" height="774" alt="image" src="https://github.com/user-attachments/assets/6ad04dce-9375-452e-b14d-60f42eb983bc" />
<img width="1431" height="771" alt="image" src="https://github.com/user-attachments/assets/a05fa447-dd03-4a25-bdbe-d5a9fdcdd3d1" />
<img width="1433" height="775" alt="image" src="https://github.com/user-attachments/assets/0ec008bc-fa81-4b87-bb82-d967ae8c8a4e" />
<img width="1429" height="771" alt="image" src="https://github.com/user-attachments/assets/3891a58b-ff96-4f50-aa5b-d713f1ae0419" />










