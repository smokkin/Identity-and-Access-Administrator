Microsoft Entra Identity Protection provides automated detection and remediation to identity-based risks, and provides data in the portal to investigate potential risks. Microsoft Entra Identity Protection also provides an Identity Secure Score to monitor and improve your identity security posture. In the same manner as Microsoft Defender XDR and Microsoft Defender for Cloud, Identity Secure Score provides improvement actions and recommendations that can improve your overall security posture for identity in Microsoft Entra ID. This lab will explore this capability.

Exercise 1 - Using Identity Secure Score to monitor and manage identity security posture
Task 1 - Review Identity Secure Score and improvement actions
Sign in to the https://entra.microsoft.com as an administrator.

From the left menu and select Identity Secure Score

Review the information provided in the dashboard page page.

Notice the value to Identity Secure Score, your Score History and other information.

Scroll down to view the Recommdendations.

Lab Tip - In contrast to the recommendations in Microsoft Defender for Cloud and Microsoft Defender XDR, these actions are specific to identity. This provides a more focused list of potential actions to your security posture management for identity. Any recommendations initiated from this list will also provide an impact to your overall tenant security posture.

<img width="1424" height="765" alt="image" src="https://github.com/user-attachments/assets/58e02047-f7e2-4e70-b60c-f682c944b579" />

Task 2 - Execute an improvement action
To improve one area of the identity security posture, select Protect all users with a sign-in risk policy.

In the page that opens, review the risk. You should have 33 users that are unprotected. Additionally, you see an Action plan on how to resolve the threat.

Select the link Follow these steps to create a Conditional Access policy from scratch or by using a template. Review the steps in the article.

Close the article tab, and return to the tab with Microsoft Entra ID opened.

From the menu on the left, select Conditional Access.

Select + Create new policy.

Use the following values to create the policy:

Field	Value
Name	**Sign-in risk protection policy
Assignments	1. Select **0 users or agents (Preview) selected
2. On the Include tab mark All users
3. On the Excdlue tab, use the Users and groups to exclude MOD Administrator
Target resources	All resources (formerly All cloud resource)
Network	Leave at default
Conditions	1. Select 0 conditions selected
2. Under Sign-in risk select the Not configured link.
3. Set Configure = Yes and mark the box next to High and Medium.
4. Select Done to save changes.
Access controls	1. Under Grant select 0 controls selected.
2. Select Require risk remediation.
3. Under the Require authentication strength select Phishing-resistant MFA.
Session	Leave at default
Set Enable policy to Report-only. You can use the WhatIf function to verify the policy before you enable it.

Select Create.

<img width="1425" height="766" alt="image" src="https://github.com/user-attachments/assets/396b15bc-8264-4ee2-a762-4c1374ba61b2" />
<img width="1423" height="761" alt="image" src="https://github.com/user-attachments/assets/f755cb28-5052-4596-af61-710965d631fc" />
<img width="1426" height="766" alt="image" src="https://github.com/user-attachments/assets/93e899a0-9e2d-4d85-b8bb-68c6b24c345e" />
<img width="1429" height="766" alt="image" src="https://github.com/user-attachments/assets/cc51ad17-2bea-4d67-bb68-b69dfcece6aa" />
<img width="1426" height="768" alt="image" src="https://github.com/user-attachments/assets/1ddaecbc-f41f-478d-b302-bc98dd59028d" />
<img width="1428" height="763" alt="image" src="https://github.com/user-attachments/assets/041e0ac4-6e8d-458a-97fe-0ed57e73aa7f" />
<img width="1424" height="768" alt="image" src="https://github.com/user-attachments/assets/3148013e-e4ae-44dc-900f-3ec0b34f73f4" />
<img width="1421" height="775" alt="image" src="https://github.com/user-attachments/assets/9ee8a332-66f3-4c8d-be77-11a866f17300" />
<img width="1426" height="765" alt="image" src="https://github.com/user-attachments/assets/49bc766f-effb-4a4d-9cb9-467f25b44775" />
<img width="1426" height="770" alt="image" src="https://github.com/user-attachments/assets/fa76efd8-9ba2-4c3b-b27a-89495e314e49" />
<img width="1429" height="769" alt="image" src="https://github.com/user-attachments/assets/30449278-de08-4d31-bfed-1fe292808e43" />
<img width="1425" height="775" alt="image" src="https://github.com/user-attachments/assets/0efebc98-da2d-465d-a073-676715f3f906" />
<img width="1429" height="768" alt="image" src="https://github.com/user-attachments/assets/d20dce8a-48c0-46d1-8626-6c92572f5afc" />
<img width="1428" height="764" alt="image" src="https://github.com/user-attachments/assets/54740eb7-ed86-43ed-9f54-dc8046fa2629" />









