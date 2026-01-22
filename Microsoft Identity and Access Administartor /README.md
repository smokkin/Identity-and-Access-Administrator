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

Task 1: Add a New User

- Initiate Global Administrator Session: Access the Microsoft Entra admin center at https://entra.microsoft.com using your Microsoft 365 admin credentials. This step authenticates you with elevated privileges necessary for user management.
- Navigate to User Management: Expand the Entra ID section in the left-hand menu if collapsed. Under Users, select All Users, then click + New User followed by Create new user. This interface allows for bulk or individual user additions, streamlining onboarding.
- Configure User Details: Inputed the following attributes: - User Principal Name: ChrisG - Display Name: Chris Green
- Retained the Auto-generate password option to produce a temporary credential, which bolsters security by mandating an immediate reset.
- Create New User Form, which shows fiels to fill in Identity and password generation.
- Record Temporary Password: Duplicate the generated password for subsequent use. This generated credential expires upon first login, enforcing a personalised reset.
- Finalize Creation: Proceed to Review + Create, then confirm by selecting Create. The system registers the user, integrating them into the directory.Updated Users List After Creation
- The screenshots below confirms the user addition, displaying Chris Green in the roster with details like user type and sync status.
  
<img width="460" height="230" alt="image" src="https://github.com/user-attachments/assets/3c206c6e-7705-490d-9000-0f5899592bef" /> <img width="460" height="230" alt="image" src="https://github.com/user-attachments/assets/4eb0f7f3-9bb5-46c7-a831-ab9eb82f43db" /> <img width="460" height="230" alt="image" src="https://github.com/user-attachments/assets/7cf2a0e6-4ace-4ea6-a364-aed1352c1c15" />

Task 2: Login and Try to Create an App

This task validates the user's baseline permissions, demonstrating Entra ID's role enforcement by attempting privileged actions without the Application Administrator role assigned.

- Launched an Isolated Browser Session: Opened an InPrivate window to simulate a dfferent user context, preventing session overlap.
- Authenticate as New User: Navigate to https://entra.microsoft.com and sign in with: - Username: ChrisG@yourdomain.com - Password: The auto-generated value from Task 1.
- New User Sign-In Prompt:
  captures the initial login screen for Chris Green.
  Execute Password Reset: Update the password as prompted, given it's the first sign-in or could be due to expiration.
  
  <img width="460" height="230" alt="image" src="https://github.com/user-attachments/assets/dec01c57-6e6b-4089-83d6-5aabeff38dab" /> <img width="460" height="230" alt="image" src="https://github.com/user-attachments/assets/e22987b3-5662-496a-ace6-efa4fc717631" />
  
  Current Password: Auto-generated value
  New Password: A robust, unique string
  Confirm: Re-enter the new password
  
  <img width="460" height="230" alt="image" src="https://github.com/user-attachments/assets/8b6e2940-04aa-43d1-a182-0563b02b690c" />

- This enforces security by requiring a change on first login.
- Accessed Enterprise Applications: Searched for and selected Enterprise applications. I Observe the gallery of integrated apps, such as AWS and Google Cloud.Enterprise Applications Gallery
- This displays the app gallery, where pre-integrated SaaS apps are browsable, but creation is restricted.
- Attempted Application Creation: Click + New application. Note that + Create your own application is greyed out, illustrating permission limitations.
- This shows registered enterprise apps, confirming visibility but no creation rights.
  
  <img width="460" height="230" alt="image" src="https://github.com/user-attachments/assets/5c0fc679-3746-476e-9332-30ffa31d7e06" />
  
- Tested for Additional Privileges: Navigated to settings > Consent and permissions or User settings. Encountered access denials, confirming the absence of administrative rights.Access Denied in Consent Settings.
- This error page (401 unauthorised) exemplifies RBAC restrictions on sensitive areas.
  
  <img width="460" height="230" alt="image" src="https://github.com/user-attachments/assets/4b4f5d57-eb68-4596-808e-6f88e658c40c" /> <img width="460" height="230" alt="image" src="https://github.com/user-attachments/assets/f042e594-564b-4dc3-b0ff-4e96cac00c0a" />




