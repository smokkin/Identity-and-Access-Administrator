For applications your organization has developed or for those that are registered directly in your Microsoft Entra tenant, you can grant tenant-wide admin consent from App registrations in the Azure portal.

Exercise 1 - Admin Consent
Task 1 - Grant admin consent in App registrations
Warning - Granting tenant-wide admin consent to an application will grant the app and the app's publisher access to your organization's data. Carefully review the permissions the application is requesting before granting consent.

The Global Administrator role is required in order to provide admin consent for application permissions to the Microsoft Graph API.

In a previous exercise, you created an app named Demo app. If necessary, in Microsoft Entra admin center, browse to Identity, Applications, then select App registrations, and then select Demo app.

On the Demo app page, locate and copy and save each Application (client) ID and Directory (tenant) ID values so that you can use them later.

Note - Demo app is created in the previous labs. Please complete these labs before this lab.

Screen image displaying the Demo app page with the directory ID highlighted

In the left navigation, under Manage, select API permissions.

Under Configured permissions, select Grant admin consent.

Screen image displaying the API permission page with Grant admin consent for Contoso highlighted

Review the dialogue box, and then select Yes.

Warning - Granting tenant-wide admin consent through App registrations will revoke any permissions that had previously been granted tenant-wide. Permissions previously granted by users on their own behalf will not be affected.

<img width="1431" height="768" alt="image" src="https://github.com/user-attachments/assets/d123dde2-4be6-47d3-86c0-92d3971a3e18" />
<img width="1428" height="764" alt="image" src="https://github.com/user-attachments/assets/c354971d-cd8d-44c4-b6e5-d8061955caf2" />
<img width="1429" height="770" alt="image" src="https://github.com/user-attachments/assets/79b8181d-364a-4be0-bf80-837d334f07cb" />
<img width="1429" height="769" alt="image" src="https://github.com/user-attachments/assets/8ebc9a84-da38-45ef-ab57-ae6c58cd3b50" />

Task 2 - Grant admin consent in Enterprise apps
You can grant tenant-wide admin consent through Enterprise applications if the application has already been provisioned in your tenant.

In Microsoft Entra admin center, browse to Identity and Applications.

From the menu open Enterprise applications.

From the list of Enterprise applications pick the Demo app that we registered earlier.

On the Demo app page, in the left navigation, under Security, select Permissions.

Under Permissions, select Grant admin consent.

Screen image displaying the Demo app permissions page with Grant admin consent for Contoso highlighted

Warning - Granting tenant-wide admin consent through App registrations will revoke any permissions that had previously been granted tenant-wide. Permissions previously granted by users on their own behalf will not be affected.

When prompted, sign in using your Global Administrator account.

In the Permissions requested dialog box, review the information and then select Accept.

<img width="1424" height="768" alt="image" src="https://github.com/user-attachments/assets/8e38661f-638f-4a5c-929f-8a67c0d97e8d" />
<img width="1429" height="770" alt="image" src="https://github.com/user-attachments/assets/39492265-ce43-4890-beb6-82713e8a6db9" />
<img width="1431" height="768" alt="image" src="https://github.com/user-attachments/assets/1b250c7e-3953-41bc-b798-a5575f296e86" />
<img width="1430" height="772" alt="image" src="https://github.com/user-attachments/assets/b27f1fe8-4315-4df4-9da2-a5c626ac0ed2" />
<img width="1427" height="767" alt="image" src="https://github.com/user-attachments/assets/b388bb4d-a5d6-43e2-b97f-9e1f2b6cae75" />



