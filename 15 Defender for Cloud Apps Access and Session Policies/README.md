Microsoft Defender for Cloud Apps allows us to create additional Conditional Access policies specific to the cloud apps that we are monitoring. Creating these policies can be done from within the Control menu within the Microsoft Defender for Cloud Apps portal.
Exercise 1 - Create and test the Conditional Access App Contol policy
Task 1 - Confirm that PradeepG has unconditional access to FORMS
Launch a new InPrivate browsing window.
Connect to https://forms.microsoft.com.
Select the login in the upper-right corner of the page.
Log in as Pradeep Gupta.
Username = PradeepG@ [your lab hoster provided domain]
Password = the password from your resources tab
Confirm that Microsoft Forms opens and that you do not get any warning messages.
Close the InPrivate browsing window.

<img width="1426" height="767" alt="image" src="https://github.com/user-attachments/assets/c3946c45-a837-40f8-bf69-e4d05b311c28" />

Task 2 - Configure Microsoft Entra ID to work with Defender for Cloud Apps
Navigate to https://entra.microsoft.com and go to Microsoft Entra ID.

Under Identity, select Protection.

Then select Conditional Access.

Select + Create new policy.

Enter a policy name, such as Monitor Pradeep using Forms.

Under Assignments, choose 0 users and groups selected, select Specific users included, select Select users and groups and mark the Users and groups.

Choose the Pradeep Gupta account for the lab tenant and select Select.

Under Target resources, select No target resources selected.

Select Select resources, and then click none under Select to be able to choose Microsoft Forms..

Under Access controls, select Session and 0 controls selected.

Select the Use Conditional Access App Control box, leave the default of Monitor only, and select Select.

Under Enable policy, select On, and select Create.

<img width="1426" height="771" alt="image" src="https://github.com/user-attachments/assets/3a3cd8e2-34f4-4c91-ada7-ae814ed9883c" />
<img width="1429" height="768" alt="image" src="https://github.com/user-attachments/assets/388e030b-b18b-428c-95d7-09bd6b244e42" />
<img width="1429" height="772" alt="image" src="https://github.com/user-attachments/assets/f0ce9ac8-5dd9-4b8e-8dad-2be88d87edfb" />
<img width="1427" height="764" alt="image" src="https://github.com/user-attachments/assets/b2cc394b-53df-43bc-b209-6d770e84bbe5" />
<img width="1426" height="769" alt="image" src="https://github.com/user-attachments/assets/299505c4-c0c6-4890-b76f-6c5a19829869" />
<img width="1429" height="769" alt="image" src="https://github.com/user-attachments/assets/95cbee48-6840-4926-bc90-146d19c7481f" />

Task 3 - Log into Forms and validate that conditional access is monitoring
Launch a new InPrivate browsing window.
Connect to https://forms.microsoft.com.
Select the login in the upper-right corner of the page.
Log in as Pradeep Gupta.
Username = PradeepG@ [your lab hoster provided domain]
Password = the password from your resources tab
Confirm that Pradeep has access and that you get a new message:
Your company is monitoring the usage of this application.
Close the InPrivate browsing window.

Exercise 2 - Setup alerts in Microsoft Defender for Cloud Apps
Task 1 - Access Microsoft Defender for Cloud Apps and create Conditional Access App Control
Registering your application establishes a trust relationship between your app and the Microsoft identity platform. The trust is unidirectional: Your app trusts the Microsoft identity platform—not the other way around.

Sign in to https://security.microsoft.com using a Global Administrator account.

On the left menu, scroll to and select Polices in the Cloud Apps section of the menu on the left..

In the Policies menu, locate and select Policy Management.

Select + Create policy. Select Access policy.

Enter a name for the policy, such as Monitor Microsoft Forms access..

Leave the Category as Access control.

Under Activities matching all of the following, select the drop-down for Intune compliant, Microsoft Entra Hybrid joined and unselect Microsoft Entra Hybrid joined.

Select the drop-down for Select apps. Select Microsoft Forms.

Leave Actions as Test.

Under Alerts, leave Create an alert… checked and select Send alert as email.

Enter the lab admin email address and select Enter on your keyboard.

Select Create to create the access policy.

<img width="1426" height="765" alt="image" src="https://github.com/user-attachments/assets/17de7197-143a-4413-98c5-b84840956e21" />

Task 2 - Log in as Pradeep to Forms to trigger activity
Launch a new InPrivate browsing window.
Connect to https://forms.microsoft.com.
Select the login in the upper-right corner of the page.
Log in as Pradeep Gupta.
Username = PradeepG@ [your lab hoster provided domain]
Password = the password from your resources tab
Confirm that Pradeep has access and that you get a new message:
Your company is monitoring the usage of this application.
Close the InPrivate browsing window.
Task 3 - Review the Activity in Defender for Cloud Apps
Return to the browswer running Defender for Cloud Apps.
Refresh the browser to ensure the most recent data is downloaded.
From the Cloud Apps menu, select Activity log.
Using the App: filter pick Microsoft Forms from the list.
Notice the sign-on records for Pradeep.

