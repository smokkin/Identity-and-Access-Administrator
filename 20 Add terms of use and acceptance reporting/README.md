Microsoft Entra terms of use policies provide a simple method that organizations can use to present information to end users. This presentation ensures users see relevant disclaimers for legal or compliance requirements. This article describes how to get started with terms of use (ToU) policies.

You must create and enforce a ToU policy for your organization.

Exercise 1 - Set up a Term of Use and test them
Task 1 - Add terms of use
Once you have finalized your terms of use document, use the following procedure to add it.

Sign in to https://entra.microsoft.com using a Global Administrator account.

Open select Identity Governance in the lefthand navigation menu.

In the menu, under Entitlement management, select Terms of use.

On the Terms of use page, on the top menu, select + New terms

Screen image displaying the Terms of use page with New terms highlighted

In the Name box, enter Testing terms of use.

Note - This is the terms of use that will be used in the Azure portal.

Select the Terms of use document box, browse to your finalized terms of use PDF and select it.

ToU File Provided - browse to the github repo AllFiles/Labs/Lab26 to get a sample Terms-of-User PDF document for use in this lab.

In the Display name box, enter Contoso Terms of Use.

Note - This is the title that users see when they sign in.

Select English for the language for your terms of use document.

Note - The language option allows you to upload multiple terms of use, each with a different language. The version of the terms of use that an end user will see will be based on their browser preferences.

To require end users to view the terms of use prior to accepting them, set Require users to expand the terms of use to On.

To require end users to accept your terms of use on every device they are accessing from, set Require users to consent on every device to Off. Users may be required to install additional applications if this option is enabled.

Warning - Consent on every device will require users to register each device with Microsoft Entra ID prior to getting access. It is a good practice to require this setting to On; however for the purpose of a cleaner lab, we are using Off.

If you want to expire terms of use consents on a schedule, set Expire consents to On. When set to On, two additional schedule settings are displayed.

Expire consents settings to set start date, frequency, and duration

Use the Expire starting on and Frequency settings to specify the schedule for terms of use expirations. The following table shows the result for a couple of example settings:

Expire starting on	Frequency	Result
Today's date	Monthly	Starting today, users must accept the terms of use and then reaccept every month.
Date in the future	Monthly	Starting today, users must accept the terms of use. When the future date occurs, consents will expire and then users must reaccept every month.
For example, if you set the expire starting on date to Jan 1 and frequency to Monthly, here is how expirations might occur for two users:

User	First accept date	First expire date	Second expire date	Third expire date
Alice	Jan 1	Feb 1	Mar 1	Apr 1
Bob	Jan 15	Feb 1	Mar 1	Apr 1
Use the Duration before re-acceptance requires (days) setting to specify the number of days before the user must reaccept the terms of use. This allows users to follow their own schedule. For example, if you set the duration to 30 days, here is how expirations might occur for two users:

User	First accept date	First expire date	Second expire date	Third expire date
Alice	Jan 1	Jan 31	Mar 2	Apr 1
Bob	Jan 15	Feb 14	Mar 16	Apr 15
Note - It is possible to use the Expire consents and Duration before re-acceptance requires (days) settings together, but typically you use one or the other.

Under Conditional Access, select Custom policy.

Possible choices and when to use them:
Template	Description
Access to cloud apps for all guests	A Conditional Access policy will be created for all guests and all cloud apps. This policy impacts the Azure portal. Once this is created, you might be required to sign-out and sign-in.
Access to cloud apps for all users	A Conditional Access policy will be created for all users and all cloud apps. This policy impacts the Azure portal. Once this is created, you will be required to sign-out and sign-in.
Custom policy	Select the users, groups, and apps that this terms of use will be applied to.
Create Conditional Access policy later	This terms of use will appear in the grant control list when creating a Conditional Access policy.
IMPORTANT - Conditional Access policy controls (including terms of use) do not support enforcement on service accounts. We recommend excluding all service accounts from the Conditional Access policy. Custom Conditional Access policies enable granular terms of use, down to a specific cloud application or group of users. For more information, see https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/require-tou.

When complete, select Create.

Screen image displaying the New terms of use page with configured options highlighted
<img width="1430" height="768" alt="image" src="https://github.com/user-attachments/assets/e8cd264a-cfe4-44ea-833a-eeeab26cc11a" />
<img width="1429" height="767" alt="image" src="https://github.com/user-attachments/assets/5a9d6dff-bad5-462e-a06f-e517c846a3af" />

Continued Task 1 - Create the Conditional Access Policy
When the terms of use is created, you will automatically be redirected to the Conditional access policy page. On the page, in the Name box, enter Enforce ToU.

Under Assignments, select Users identities.

On the Include tab choose Select users and groups, then select Users and groups check box.

In the Select pane, select Adele Vance to use to test the terms of use policy.

Warning - If you choose your administrator account, like all conditional access policies, be sure you have another account with enough permissions to change the conditional access policy. This is to ensure your administrator account will not be locked out should the conditional access policy result in an undesirable outcome.

Select Target resources.

Select All cloud apps.

Under Access controls, select Grant.

In the Grant pane, select Contoso Terms of Use and then select Select.

Under Enable policy, select On.

When complete, select Create.

Screen image displaying the conditional access policy with configuration options highlighted

If you chose to use your own account, you can refresh your browser. You will be prompted to sign in again. When you sign in, you will be required to accept the terms of use.

<img width="1423" height="767" alt="image" src="https://github.com/user-attachments/assets/5386b4ef-0820-422d-bd31-837be46cc944" />
<img width="1427" height="768" alt="image" src="https://github.com/user-attachments/assets/e9ec370d-6d34-4500-b3dc-f7d0c47f05fe" />
<img width="1431" height="766" alt="image" src="https://github.com/user-attachments/assets/23cc1f17-cead-46d3-92d2-5c404c4584ff" />
<img width="1429" height="777" alt="image" src="https://github.com/user-attachments/assets/19827001-331a-4d69-862d-832329b25d21" />
<img width="1427" height="770" alt="image" src="https://github.com/user-attachments/assets/9c91364b-02e0-4e4e-9c2e-9351cf493089" />

Task 2 - Log in as Adele
Open a new InPrivate browser window.

Connect to https://portal.azure.com.

If if comes up saying you are already logged in, Select on the logged in users name in the upper-right of the screen and choose Sign in with a different account.

Log in as Adele:

Setting	Value to enter
User Name	AdeleV@ <<your domain name>>.onmicrosoft.com
Password	Enter the tenant's admin password(Refer the Lab Resources tab to retrieve the tenant admin password)
Validate Adele's login with the MFA request.

View the Terms of Use.

You can choose to Accept or Decline.

Note - If you choose decline then during a future login as AdeleV you will again be required to view and accept the Terms of Use.

Note: Terms of Use may take a few minutes to appear or you can logout and log back in to the portal.
<img width="466" height="584" alt="image" src="https://github.com/user-attachments/assets/8b96de03-11af-4a0f-8ca1-2873470b8611" />
<img width="472" height="662" alt="image" src="https://github.com/user-attachments/assets/16f8a94b-47ae-4c7b-8917-e5d93f6a94ba" />
<img width="1422" height="760" alt="image" src="https://github.com/user-attachments/assets/8289a7cb-bfcb-4620-aae9-f94daf63f8f7" />
<img width="1425" height="762" alt="image" src="https://github.com/user-attachments/assets/1593bdb5-42ec-453b-a183-7cbd9eaa2a80" />

Task 3 - View report of who has accepted and declined
The Terms of use page shows a count of the users who have accepted and declined. These counts and who accepted/declined are stored for the life of the terms of use.

In Microsoft Azure, in Identity Governance > Terms of use, locate your terms of use.

For a terms of use, select the numbers under Accepted or Declined to view the current state for users.

Screen image displaying the terms of use with the Accepted and Declined columns highlighted

In this exercise you may not have any accepted or declined terms of use. In the following example, the Accepted value was selected. You can see the reported user information for those that have accepted the terms of use.

Terms of use consents pane listing the users that have accepted

On the Terms of Use Consents page select Download to download a consents report.

On the Identity Governance | Terms of Use page, highlight Testing terms of use and select View selected audit logs to view the audit logs activity.
<img width="1424" height="770" alt="image" src="https://github.com/user-attachments/assets/c9ba1844-8c5f-4180-9648-c8ebd68a7ee7" />
<img width="1423" height="766" alt="image" src="https://github.com/user-attachments/assets/33113648-cce0-4d24-88ed-a69efb61d9f0" />
<img width="1430" height="765" alt="image" src="https://github.com/user-attachments/assets/c2e3f2ba-2675-4b96-b898-1e6c538b6961" />
<img width="1425" height="764" alt="image" src="https://github.com/user-attachments/assets/814baa70-88d8-4eaa-abce-70d1ceeab8a6" />

Task 4 - What terms of use looks like for users
Once a terms of use is created and enforced, users who are in scope will see the terms of use page.

Example terms of use that appears when a user signs in

Users can view the terms of use and, if necessary, use buttons to zoom in and out.

View of terms of use with zoom buttons

On mobile devices, the terms of use will be displayed similar to the following example.


Task 5 - How users can review their terms of use
Users can review and see the terms of use that they have accepted by using the following procedure.

Browse to https://myapps.microsoft.com/ and then sign in using your user account.

Select the user profile photo and then select View account. On the Overview page, select VIEW SETTINGS AND PRIVACY.

Screen image of a popup which says "View settings and privacy"

On the Settings & Privacy page, select the Privacy tab.

Screen image displaying the settings and privacy page with organization

Under Organization’s notice, you can review the terms of use you have accepted.

<img width="1428" height="765" alt="image" src="https://github.com/user-attachments/assets/cf9c7100-30d6-42ab-93bb-595f608aeb5a" />
<img width="1426" height="762" alt="image" src="https://github.com/user-attachments/assets/90f075d0-55c9-4d2f-94cd-3f7e57e6deb2" />

Task 6 - Edit terms of use details
You can edit some details of terms of use, but you can't modify an existing document. The following procedure describes how to edit the details.

Sign in to the https://entra.microsoft.com as a Global administrator.

Open Microsoft Entra ID item and the select Identity Governance from the menu.

In the left navigation menu, under Entitlement management, select Terms of use.

Select the terms of use you want to edit.

Note: You have to click on open space, not directly on name of the Terms or Use.

On the top menu, select Edit terms.

In the Edit terms of use pane, you can change the following:

Name – this is the internal name of the ToU that is not shared with end users

Display name – this is the name that end users can see when viewing the ToU

Require users to expand the terms of use – Setting this to On will force the end use to expand the terms of use document before accepting it.

Update an existing terms of use document.

You can add a language to an existing ToU If there are other settings you would like to change, such as require users to consent on every device, expire consents, duration before reacceptance, or Conditional Access policy, you must create a new terms of use.

Screen image of the Identity Governance terms of use being edited.

Once you are done, select Save to save your changes.

<img width="1426" height="769" alt="image" src="https://github.com/user-attachments/assets/f89f6479-9184-4d6d-8cf1-d387d3288119" />
<img width="1429" height="765" alt="image" src="https://github.com/user-attachments/assets/ac9e0bc3-fdde-4f6b-8661-9f5774e6cbee" />

Task 7 - Update an existing terms of use document
You may, on occasion, be required to update the terms of use document.

Select the terms of use you want to edit.

Select Edit terms.

In the Language Options table, identify the terms of use language you want to update and then, in the Action column, select Update.

Screen image displaying the terms of use with the update option highlighted

In the Update terms of use version pane, you can upload a new version of your terms of use document.

Additionally, you can use the Require reaccept toggle button if you want to require your users to accept this new version the next time they sign in. If you do not require your users to re-accept, their previous consent will stay current and only new users who have not consented before or whose consent expires will see the new version.

Screen image displaying the update terms of use version pane with the upload required pdf and require re-accept highlighted

Once you have uploaded your new pdf and decided on re-accept, select Add.

You will now see the most recent version under the Document column.
<img width="1424" height="766" alt="image" src="https://github.com/user-attachments/assets/8a4675f1-7aa8-4aba-a50e-4185e976519a" />
<img width="1426" height="767" alt="image" src="https://github.com/user-attachments/assets/7cdb40a4-fecc-4579-96ac-7f957013aa51" />
<img width="1428" height="765" alt="image" src="https://github.com/user-attachments/assets/a7968d99-2083-4309-90cb-36598f842b57" />

