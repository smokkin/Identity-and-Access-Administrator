Your organization needs to be able to limit user access to its internal applications. You must deploy an Microsoft Entra conditional access policy.

Note - For Conditional Access Policies, you can turn off Security Defaults, the key points to remember are from the training. Additional information on Security defaults can be found at this link: https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/concept-fundamentals-security-defaults
Task 1 -- Confirm DebraB has access to Sway
Launch a new InPrivate browser window.

Connect to https://www.office.com

When prompted, log in as DebraB:

Setting	Value
Username	DebraB@ <<your lab domain>>.onmicrosoft.com
Password	Enter the provided password
Bypass the welcome and introduction screens.

Open the Apps page, then then select on the Sway icon to see that it loads correctly.

Log out of Office and close your browser session.
<img width="1427" height="764" alt="image" src="https://github.com/user-attachments/assets/e6980288-cc0a-4df3-a15d-f75f722d0896" />
<img width="1426" height="764" alt="image" src="https://github.com/user-attachments/assets/7c44732f-b1aa-4d95-97b6-7b3a61becf88" />

Task 2 - Create a conditional access policy
Microsoft Entra conditional access is an advanced feature of Microsoft Entra ID that allows you to specify detailed policies that control who can access your resources. Using Conditional Access, you can protect your applications by limiting users' access based on things like groups, device type, location, and role.

Browse to https://entra.microsoft.com and sign in using a Global administrator account for the directory.

Open the portal menu and then select Microsoft Entra ID.

On the menu, under Identity, select Protection.

On the Security page, in the left navigation, select Conditional access.

On the Overview (Preview), click + Create new policy.

Screen image displaying the Conditional Access page with New policy highlighted

In the Name box, enter Block Sway for DebraB.

Note - Using this naming to help you quickly recognize the policy and its function.

Under Assignments, select 0 users and groups selected.

On the Include tab, select Select users and groups, and then mark Users and groups check box.

In the Select pane, select DebraB account and then select Select.

In the Target resources, select No target resource selected.

Verify resources is selected and then select Select resources, then select None in the select section.

In the Select pane, search for Sway and select Sway and then select Select.

Under Access controls, within the Grant section, select 0 controls selected.

In the Grant pane, select Block access and then select Select.

Note - This policy is being configure for the exercise only and is being used to quickly demonstrate a conditional access policy.

Under Enable policy, select On, and then select Create.

Screen image displaying a new conditional access policy with policy settings highlighted

<img width="1428" height="772" alt="image" src="https://github.com/user-attachments/assets/73f47b83-5564-48b5-9774-80a6a2753d39" />
<img width="1432" height="768" alt="image" src="https://github.com/user-attachments/assets/560840a6-4f8e-4082-a24a-cf104b4dc251" />
<img width="1430" height="772" alt="image" src="https://github.com/user-attachments/assets/89db6e03-1f11-4fba-95f4-508748ee977e" />
<img width="1426" height="763" alt="image" src="https://github.com/user-attachments/assets/070b1961-f514-4bcd-b461-444108da69ab" />
<img width="1428" height="768" alt="image" src="https://github.com/user-attachments/assets/e538257a-0ddb-47c5-8af6-63226599954a" />
<img width="1431" height="768" alt="image" src="https://github.com/user-attachments/assets/ab9022c7-0eb8-48e0-a79a-75ff33b5a5a3" />

Task 3 - Test the conditional access policy
You should test your conditional access policies to ensure they working as expected.

Open a new 'InPrivate' browser tab and then browse to https://sway.cloud.microsoft

When prompted, log in as DebraB:
Setting	Value
Username	DebraB@ <<your lab domain>>.onmicrosoft.com
Password	Enter the provided password
Verify you are prevented from accessing Microsoft Sway.

Screen image displaying a the blocked resource access due to an enabled conditional access policy

If you are signed in, close the tab, wait 1 minute, and then retry.

Note - If you are auto-logged into Sway as DebraB, then you will need to manually log out. Your credentials / access were cached. Once you log out and sign-in, your Sway session should deny access.

Close the tab and return to the Conditional Access page.

Select the Block Sway for DebraB policy.

Under Enable policy, select Off and then select Save.

<img width="1432" height="776" alt="image" src="https://github.com/user-attachments/assets/f63ec82f-2528-430c-ad57-95ba421b35b7" />
<img width="1435" height="804" alt="image" src="https://github.com/user-attachments/assets/63e2fcab-7007-46d4-9404-31af1458f1c1" />
<img width="456" height="432" alt="image" src="https://github.com/user-attachments/assets/843a739b-deb6-4fec-b275-7c8f9cfbe788" />
<img width="1429" height="769" alt="image" src="https://github.com/user-attachments/assets/9e6345f6-55c4-4dcb-abcd-e061e45817c5" />
<img width="1432" height="770" alt="image" src="https://github.com/user-attachments/assets/3c4b2346-15c8-4de9-84c9-187d294a5623" />
<img width="1426" height="767" alt="image" src="https://github.com/user-attachments/assets/f4b7c54a-4723-4486-a711-d35973e1dddb" />
<img width="1431" height="767" alt="image" src="https://github.com/user-attachments/assets/64f04021-8b40-496f-ae9c-31b23e9f063a" />


Exercise 2 - Test conditional access policies with "What if"
Task - Use What if to test conditional access policies
Open the Microsoft Entra admin center menu and then select Microsoft Entra ID.

On the menu, under Identity, select Protection.

On the Security page, in the left navigation, select Conditional access.

In the navigation pane, select Policies.

Select What If.

Under User or Workload identity, select No user or service principal selected.

Choose DebraB as the user.

Under Cloud apps, actions, or authentication context, select Sway.

Select What if. You will be provided with a report at the bottom of the tile for Policies that will apply and Policies that will not apply.

This allows you to test the policies and their affectiveness before enabling the policies.
<img width="1429" height="765" alt="image" src="https://github.com/user-attachments/assets/95b9d44a-ed77-46d2-acce-ffc8e2ff022a" />
<img width="1427" height="763" alt="image" src="https://github.com/user-attachments/assets/0ffe82bf-63c8-4255-8ee1-53641a2dbb02" />
<img width="1424" height="768" alt="image" src="https://github.com/user-attachments/assets/39465370-16b6-45c3-ba9d-2339a026184b" />
<img width="1434" height="770" alt="image" src="https://github.com/user-attachments/assets/775cfa5b-dda1-4c28-bd3a-7e245352481d" />
<img width="1419" height="765" alt="image" src="https://github.com/user-attachments/assets/f0dbef36-00b5-44d3-91e9-7a64f780e52a" />

Exercise 3 - Configure sign in frequency controls using a conditional access policy
Task - Use the Microsoft Entra admin center to configure conditional access
As part of your company's larger security configuration, you must test a conditional access policy that can be used to control sign in frequency

Browse to https://entra.microsoft.com and sign in using a Global administrator account for the directory.

Open the portal menu and then select Microsoft Entra ID.

On the menu, under Identity, select Protection.

On the Protection menu, in the left navigation, select Conditional access.

On the top menu, select Policies, then select + New policy from the drop-down select Create a new policy.

Screen image displaying the Conditional Access page with New policy highlighted

In the Name box, enter Sign in frequency.

Under Assignments, select 0 users and groups selected.

On the Include tab, mark Select users and groups, then select the Users and groups check box.

In the Select pane, select your Grady Archie account and then select Select.

Select Target Resources - No target resources selected.

Within the Include make sure Select resources is selected, then choose None in the Select section.

In the Select pane, select Office 365 and then select Select.

Under Access controls, select Session.

In the Session pane, select Sign-in frequency.

In the value box, enter 30.

Select the units menu, select Days, and then select Select.

Under Enable policy, select Report-only, and then select Create.

Screen image displaying a new conditional access policy with policy settings highlighted

NOTE - Report-only mode is a new Conditional Access policy state that allows administrators to evaluate the impact of Conditional Access policies before enabling them in their environment. With the release of report-only mode:

Conditional Access policies can be enabled in report-only mode.
During sign-in, policies in report-only mode are evaluated but not enforced.
Results are logged in the Conditional Access and Report-only tabs of the Sign-in log details.
Customers with an Azure Monitor subscription can monitor the impact of their Conditional Access policies using the Conditional Access insights workbook.
<img width="1430" height="765" alt="image" src="https://github.com/user-attachments/assets/277bdb0e-32a4-40ba-a328-3ca8a624a728" />
<img width="1430" height="768" alt="image" src="https://github.com/user-attachments/assets/982e34c1-cced-44da-a143-33bcc0ba71e6" />
<img width="1428" height="768" alt="image" src="https://github.com/user-attachments/assets/66c8c02a-91c5-44de-a6e4-3f97fa623845" />
<img width="1426" height="765" alt="image" src="https://github.com/user-attachments/assets/dac9d3ad-02e3-4d9c-a71d-f0c907f761c6" />
<img width="1424" height="770" alt="image" src="https://github.com/user-attachments/assets/38353d49-064e-4f1c-b4c0-d2b18380402f" />
<img width="1435" height="766" alt="image" src="https://github.com/user-attachments/assets/4432b16b-d0ab-4edc-b035-355e17b030d1" />
<img width="1426" height="766" alt="image" src="https://github.com/user-attachments/assets/7426932c-da8b-4b54-9615-ef3cf4f97b81" />





