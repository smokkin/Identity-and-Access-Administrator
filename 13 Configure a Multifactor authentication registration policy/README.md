Multifactor authentication provides a means to verify who you are using more than just a username and password. It provides a second layer of security to user sign-ins. For users to be able to respond to MFA prompts, they must first register for Microsoft Entra Multifactor Authentication. You must configure your Microsoft Entra organization's MFA registration policy to be assigned to all users.

Exercise 1 - Set up MFA registration policy
Task 1 - Policy configuration
Sign in to the https://entra.microsoft.com using a Global administrator account.

Open the portal menu and then select Microsoft Entra ID.

On the lefthand men, under Identity, select Protection.

On the Security page, in the left navigation, select Identity protection.

In the Identity protection page, in the left navigation under Protect, select Multifactor authentication registration policy.

Screen image displaying the MFA registration policy page with browsing path highlighted

Under Assignments

Under Assignments, select All users and review the available options.

You can select from All users or Select individuals and groups if limiting your rollout.

Additionally, you can choose to exclude users from the policy.

Under Controls, notice that the Require Microsoft Entra ID multifactor authentication registration is selected and cannot be changed.

<img width="1430" height="772" alt="image" src="https://github.com/user-attachments/assets/a7459ca3-f97f-45e6-ae23-72e7d8491ba0" />

Task 2 - Configure Microsoft Entra Identity Protection policy for MFA registration
Note: Microsoft Entra Identity Protection requires Microsoft Entra ID Premium P2 to be activated.

In the Microsoft Entra admin center, navigate to Microsoft Entra ID Protection in the search bar.

Under Protect in the menu, select Multifactor authentication registration policy.

Under Assignments, select All users under Users, and select a user to enforce MFA.

Find the field Policy enforcement in the dialog. Set the value to Enabled.

Select Save.

<img width="1426" height="771" alt="image" src="https://github.com/user-attachments/assets/0735cb4e-baf7-41fc-ae18-e974e7dbf8af" />
<img width="1425" height="767" alt="image" src="https://github.com/user-attachments/assets/3689b9ce-d2e0-4766-bdac-85de7be17731" />

This will require the user to complete the MFA registration the next time they attempt to login.

From a private browser, navigate to https://login.microsoftonline.com. Enter a user name and password from the tenant. Note the additional security information requirements that the user is asked to enter.
<img width="423" height="471" alt="image" src="https://github.com/user-attachments/assets/f321808c-98b0-444d-a4bd-354cc9b56fa4" />
<img width="464" height="605" alt="image" src="https://github.com/user-attachments/assets/ed30c90b-ce8b-40bc-b4e1-70563dc88e46" />


