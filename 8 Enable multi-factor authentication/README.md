To improve security in your organization, you've been directed to enable multifactor authentication for Microsoft Entra ID.
A Microsoft Entra ID Premium license is required for this exercise.
Exercise 1 - Review and enable Multi-factor Authentication in Azure
Task 1 - Review Azure Multi-Factor Authentication options
Browse to the https://entra.microsoft.com and sign in using a Global administrator account for the directory.

Use the search feature and search for multifactor.

In the search results, select Multifactor authentication.

Alternatively, you can open Identity, then select Protection, and select Multifactor authentication.

On the Getting started page, under Configure, select Additional cloud-based MFA settings.

Screenshot showing MFA options in the dashboard

In the new browser page, you can see the MFA options for Azure users and service settings.

Screenshot showing MFA configuration

This is where you would select the supported authentication methods, in the screen above, all of them are selected.

You can also enable or disable app passwords here, which allow users to create unique account passwords for apps that don't support multi-factor authentication. This feature lets the user authenticate with their Microsoft Entra identity using a different password specific to that app.

<img width="1432" height="773" alt="image" src="https://github.com/user-attachments/assets/39f40e8c-eab8-476e-9411-e8416352fa3e" />
<img width="1434" height="771" alt="image" src="https://github.com/user-attachments/assets/cd9544bc-ce77-4982-9a32-35d0bc307a76" />
<img width="1428" height="773" alt="image" src="https://github.com/user-attachments/assets/80f27513-7ecd-4520-9443-dfca64085a70" />

Task 2 - Setup conditional access rules for MFA for Delia Dennis
Next let's examine how to set up Conditional Access policy rules that would enforce MFA for guest users accessing specific apps on your network.

Switch back to the Microsoft Entra admin center and select Identity, then Protection, and then Conditional access.

On the menu, Select the Policies page , Select + New policy. From the drop down select + Create new policy.

Screenshot highlighting the New Policy button in the Microsoft Entra admin center.

Name your policy, for example MFA_for_Delia.

Select Users under Assignments.

Select 0 users or workload identities selected
On the right side screen, select Select users and groups check box to configure.
Check Users and groups (available users will be populated to the right)
Choose Delia Dennis from the list of users then choose Select button.
Select No target resources selected in Target resources.

In the dropdown, make sure Cloud apps is selected.
Under Include, mark Resources (formerly cloud apps) and note the warning the pops up about possibly locking yourself out.
Now under Include section, choose the Select resources item.
In the Select section select the None link.
In the newly opened dialog, choose Office 365.
Reminder - in a previous lab we gave Delia Dennis an Office 365 license and logged into ensure it worked.
Choose Select.
Choose a network location in the Conditions section, then select Not configured.

In the Conditions section choose the 0 conditions selected link.
At the bottom of the newly opened menu find the Locations section, and select Not configured.
Choose Yes for the Configure item.
Select Any network or location.
Under Access Controls, find the Grant section and select the 0 controls selected link.

Select the Require multifactor authentication check box to enforces MFA.
Ensure that Require all the selected controls is selected.
Select Select.
Set Enable policy to On.

Select the Create button to create the policy.

Screenshot showing the complete Add Policy dialog

MFA is now enabled for your selected user and application(s). The next time a guest tries to sign into that app they will be prompted to register for MFA.

<img width="1427" height="765" alt="image" src="https://github.com/user-attachments/assets/69f760f5-446d-4d1e-be10-7a38cd16a9a1" />
<img width="1431" height="771" alt="image" src="https://github.com/user-attachments/assets/dbb48619-ee52-4fac-9010-1266044256b4" />
<img width="1429" height="771" alt="image" src="https://github.com/user-attachments/assets/7305db57-0549-4a54-96c4-52d88ee66572" />
<img width="1425" height="766" alt="image" src="https://github.com/user-attachments/assets/73f6173c-e0af-41e5-8914-2b9f25ff7262" />
<img width="1428" height="770" alt="image" src="https://github.com/user-attachments/assets/5a4b94d3-849c-4ca6-9624-3b371b276605" />
<img width="1426" height="767" alt="image" src="https://github.com/user-attachments/assets/63977ba5-477b-4d95-959a-5041b4a89b7f" />
<img width="1431" height="769" alt="image" src="https://github.com/user-attachments/assets/db46cc37-55d7-44f3-a21e-f0f0042c0535" />

Task 3 - Test Delia's login
Open a new InPrivate Browsing windows.
Connect to https://www.office.com
Select the sign-in option.
enter DeliaD@ <<your domain address>>.
Enter the password = Enter the Global admin password of the tenant (Note : Refer the 'Lab Resources' tab to retrieve the admin password).
Note - At this point one of two things will happen. You should get a message that you need to set up Authenticator app and register for MFA. Follow the prompts to complete using your personal phone. NOTE - there is a chance that you might get a login failure message with several options on how to proceed. Select the Try Again option in this case.

You can see that because of the Conditional Access rule we created for Delia, MFA is required to launch Office 365 home page.






