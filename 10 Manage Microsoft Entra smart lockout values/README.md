You must configure the additional password protection settings for your organization.
Exercise 1 - Manage Microsoft Entra smart lockout values
Task - Add Smart Lockouts
Based on your organizational requirements, you can customize the Microsoft Entra smart lockout values. Customization of the smart lockout settings, with values specific to your organization, requires Microsoft Entra ID Premium P1 or higher licenses for your users.

Browse to https://entra.microsoft.com and sign in using a Global administrator account for the directory.

Open the portal menu and then select Identity.

On the Identity menu, open the Protection menu.

In the left navigation, select Authentication methods.

Then select Password protection.

Screen image displaying the Authentication methods page and the highlighted selections to browse to Password authentication

In the Password protection settings, in the Lockout duration in seconds box, set the value to 120.

Next to Mode, select Enforced.

Save your changes.

NOTE - When the smart lockout threshold is triggered, you will get the following message while the account is locked:

Your account is temporarily locked to prevent unauthorized use. Try again later, and if you still have trouble, contact your admin.
This can be tested by choosing a user in your Microsoft Entra tenant, navigate in a private browser to and enter an incorrect password until the account gets notification that it is locked out.
<img width="1433" height="771" alt="image" src="https://github.com/user-attachments/assets/81101107-50d0-4ef1-9d2c-9295fabfbada" />
<img width="1431" height="766" alt="image" src="https://github.com/user-attachments/assets/3d99e466-5f9a-4d87-b983-8f23b8fd168a" />
<img width="428" height="449" alt="image" src="https://github.com/user-attachments/assets/17aff4fa-b6a6-4a7b-8f09-32bb789a15e1" />



