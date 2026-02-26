A Privileged role administrator can customize Privileged Identity Management (PIM) in their Microsoft Entra organization, including changing the experience for a user who is activating an eligible role assignment. You must become familiar with configuring PIM.

NOTE - There have been on-going changes to requiring MFA in lab environments. When you switch between users to complete this lab, you may be prompted to set up MFA.

Exercise 1 - Configure Microsoft Entra role settings
Task 1 - Open role settings
Follow these steps to open the settings for an Microsoft Entra role.

Sign in to the https://entra.microsoft.com as a Global administrator.

Search for and then select Privileged Identity Management.

In the Privileged Identity Management page, in the left navigation, select Microsoft Entra roles.

On the Quick start page, in the left navigation, select Settings.

Screen image displaying the Microsoft Entra roles page with the Settings menu highlighted

Review the list of roles and then, in the Search by role name, enter compliance.

In the results, select Compliance Administrator.

Review the role setting details information.

<img width="1426" height="769" alt="image" src="https://github.com/user-attachments/assets/f2a55ba1-40e8-4f65-b4e3-8ccf1d9af545" />
<img width="1427" height="768" alt="image" src="https://github.com/user-attachments/assets/fa3dab6c-db9a-40c7-b74d-f18a4d8e19b2" />
<img width="1425" height="770" alt="image" src="https://github.com/user-attachments/assets/46e8ad65-7b47-48d7-bd4b-9f9bd72bd784" />
<img width="1425" height="766" alt="image" src="https://github.com/user-attachments/assets/e303b439-9e10-4b1c-954a-a41d8847ffe5" />
<img width="1426" height="770" alt="image" src="https://github.com/user-attachments/assets/3ff989eb-53ed-4347-b12c-9b35fab777e9" />
<img width="1429" height="769" alt="image" src="https://github.com/user-attachments/assets/3336fe7b-99b0-43f4-a53b-2eeaa4cf4b3c" />

Task 2 - Require approval to activate
If setting multiple approvers, approval completes as soon as one of them approves or denies. You cannot require approval from at least two users. To require approval to activate a role, follow these steps.

In the Role setting details page, on the top menu, select Edit.

Screen image displaying the top portion of the Role setting details -Compliance Administrator page with Edit highlighted

In the Edit role setting – Compliance Administrator page, select the Require approval to activate check box.

Select Select approvers.

In the Select a member pane, select your administrator account and then select Select.

Screen image displaying the edit role settings page and select a member pane with the selected members highlighted

Once you have configured the role settings, select Update to save your changes.

<img width="1432" height="769" alt="image" src="https://github.com/user-attachments/assets/a7e1f131-2608-4a7f-9c24-50f598fd0871" />
<img width="1427" height="765" alt="image" src="https://github.com/user-attachments/assets/d084d452-0d58-4081-8480-6153588fbcfd" />
<img width="1433" height="773" alt="image" src="https://github.com/user-attachments/assets/5bbccca0-c6a4-4a5e-a310-bee23ce733cc" />
<img width="1425" height="769" alt="image" src="https://github.com/user-attachments/assets/19ee4abc-1ecb-4a41-862f-cec57db5391a" />

Exercise 2 - Use PIM to assign Microsoft Entra roles
Task 1 - Assign a role
With Microsoft Entra ID, a Global administrator can make permanent Microsoft Entra admin role assignments. These role assignments can be created using the Microsoft Entra admin center, the Azure portal, or using PowerShell commands.

The Privileged Identity Management (PIM) service also allows Privileged role administrators to make permanent admin role assignments. Additionally, Privileged role administrators can make users eligible for Microsoft Entra admin roles. An eligible administrator can activate the role when they need it, and then their permissions expire once they're done.

Follow these steps to make a user eligible for an Microsoft Entra admin role.

Sign in to https://entra.microsoft.com using a Global Administrator account.

Search for and then select Privileged Identity Management.

Note - you can find it in the menu at Identity - Identity Governance - Privileged Identity Management.

In the Privileged Identity Management page, in the left navigation, select Microsoft Entra roles.

On the Quick start page, in the left navigation, select Roles.

On the top menu, select + Add assignments.

Screen image displaying Microsoft Entra roles with Add assignments menu highlighted

In the Add assignments page, on the Membership tab, review the settings.

Select the Select role menu and then select Compliance Administrator.

You can use the Search role by name filter to help located a role.

Under Select member(s), select No members selected.

In the Select a member pane, select Miriam Graham and then select Select.

Screen image displaying the select a member pane with a selected member highlighted

In the Add assignments page, select Next.

On the Settings tab, under Assignment type, review the available options. For this task, use the default setting.

Eligible assignments require the member of the role to perform an action to use the role. Actions might include performing a multi-factor authentication (MFA) check, providing a business justification, or requesting approval from designated approvers.
Active assignments do not require the member to perform any action to use the role. Members assigned as active have the privileges always assigned to the role.
Review the remaining settings and then select Assign.

<img width="1427" height="768" alt="image" src="https://github.com/user-attachments/assets/f9f47d77-b7ae-4876-a435-f87bc007f1d3" />
<img width="1429" height="770" alt="image" src="https://github.com/user-attachments/assets/a351e172-afe6-4d2a-aae6-174ea5b06c21" />
<img width="1424" height="766" alt="image" src="https://github.com/user-attachments/assets/f7de0a03-1d43-4869-8c8f-9932e29324c7" />
<img width="1425" height="776" alt="image" src="https://github.com/user-attachments/assets/3f04df44-f717-42c9-82e1-fc2c65b1f45e" />
<img width="1429" height="770" alt="image" src="https://github.com/user-attachments/assets/e2fc8ef9-fc05-4af3-b377-aaee6e891e58" />

Task 2 - Log in with Miriam
Open a new InPrivate browser window.

Connect to the Microsoft Entra admin center (https://entra.microsoft.com). Note - If it opens with a user logged in, Select on their name in the upper-right corner and select Sign in as a different account.

Log in a Miriam.

Field	Value
Username	MiriamG@ <<your domain.onmicrosoft.com>>
Password	Enter the provided tenant admin password
From the Identity menu, open Users and then select All users.

Find Miriam in the list of users

On the Overview page, look for the Assigned roles.

Select Eligible assignments.

Notice that the Compliance Administrator role is now available to Miriam.

<img width="476" height="609" alt="image" src="https://github.com/user-attachments/assets/b9f4f3e1-f134-41f1-9f36-67e4a4212e3e" />
<img width="1428" height="764" alt="image" src="https://github.com/user-attachments/assets/41a196fe-9d8b-4ec3-b3a6-bbf9b08e5848" />
<img width="1428" height="761" alt="image" src="https://github.com/user-attachments/assets/f95467a8-f623-4401-a8bb-350fe83d1fc8" />

Task 3 - Activate your Microsoft Entra roles
When you need to assume an Microsoft Entra role, you can request activation by opening My roles in Privileged Identity Management.

From the Search, resources, services, and docs bar, look for Privileged.

Open the Privileged Identity Management page.

On the Privileged Identity Management page, in the left navigation menu, select My roles.

In the My roles page, review the list of Eligible assignments.

Screen image displaying My roles with eligible role assignments highlighted

In the Compliance Administrator role row, select Activate.

In the Activate – Compliance Administrator pane, select Additional verification required and then follow the instructions to provide additional security verification. You are required to authenticate only once per session.

Screen image displaying a popup to activate the compliance administrator

Verification - Based on our current lab environment configuration, you will be required configure MFA and log in successfully.

After you have completed the additional security verification, in the Activate – Compliance Administrator pane, in the Reason box, enter the This is my justification for activating this role.

Important Note - the principal of least prvilege, you should only activate the account for the amount of time you need it. If the work needed to be done, only takes 1.5 hours, then set the duration to two hours. Similarily, if you know that you won't be able to do the work until after 3pm, choose a Custom activation time.

Select Activate.

<img width="1428" height="767" alt="image" src="https://github.com/user-attachments/assets/d4042083-203a-492e-8c21-16a659cdb0d8" />
<img width="1428" height="762" alt="image" src="https://github.com/user-attachments/assets/e4a8014e-33ca-43e1-9974-107a77dcd763" />
<img width="1430" height="780" alt="image" src="https://github.com/user-attachments/assets/c1f1dfd5-16a5-474a-a99c-3ac1917c8158" />
<img width="1428" height="762" alt="image" src="https://github.com/user-attachments/assets/a631488b-8666-4a27-a5e8-4495774eebe7" />

Task 4 - Assign a role with restricted scope
For certain roles, the scope of the granted permissions can be restricted to a single admin unit, service principal, or application. This procedure is an example if assigning a role that has the scope of an administrative unit.

Remember to close out the browser windows for MiriamG, then open the Microsoft Entra admin center with your administrator account.

Browse to the Privileged Identity Management page, and in the left navigation menu, select Microsoft Entra roles.

Select Roles.

In the Roles page, on the top menu, select + Add assignments.

In the Add assignments page, select the Select role menu and then select User administrator.

Select the Scope type menu and review the available options. For now, you will use the Directory scope type.

Tip - Go to https://docs.microsoft.com/en-us/azure/active-directory/roles/admin-units-manage for more information about the administrative unit scope type.

As you did when assigning a role without a restricted scope, you would add members and complete the settings options. For now, select Cancel.

<img width="1431" height="763" alt="image" src="https://github.com/user-attachments/assets/2409bc2b-7ca4-473b-8280-01ae3f9c24c5" />
<img width="1424" height="761" alt="image" src="https://github.com/user-attachments/assets/639a119b-e187-4b8d-8b08-b8758afe05a3" />

Task 5 - Update or remove an existing role assignment
Follow these steps to update or remove an existing role assignment.

In the Open Privileged Identity Management > Microsoft Entra roles page, in the left navigation, select Assignments.

In Assignments list, for Compliance Administrator, review the options in the Action column.

Screen image displaying the options listed in the action column of the Compliance Adminsitrator

Select Update and review the options available in the Membership settings pane. When complete, close the pane.

Select Remove.

In the Remove dialog box, review the information and then select Yes.
<img width="1428" height="769" alt="image" src="https://github.com/user-attachments/assets/2062b363-99eb-42ed-8b08-5d63b2978c64" />
<img width="1427" height="763" alt="image" src="https://github.com/user-attachments/assets/84dfac09-54b6-49ed-9828-fb4026a12ece" />
<img width="1426" height="762" alt="image" src="https://github.com/user-attachments/assets/c74cd93b-29b9-45a2-a08f-47775b789ec2" />











