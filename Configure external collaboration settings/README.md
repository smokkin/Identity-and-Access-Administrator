Lab scenario
You must enable external collaboration settings for your organization for approved guests access.

Estimated timing: 5 minutes
Exercise 1 - Allowing guest users to be invited into your organization
Task 1 - Enable Guest Users to perform self service sign-up
Sign in to the https://entra.microsoft.com as a tenant administrator.
Select Identity, then select Users.
Open the All users menu item, then select User Settings.
Select Manage external user collaboration settings.
Ensure that YES is marked for the setting Enable guest self-service sign up via user flows.
Select Save at the top of the screen.

<img width="1429" height="775" alt="image" src="https://github.com/user-attachments/assets/56139c14-1b15-4c63-80f6-50542ac2cf6a" />
<img width="1425" height="775" alt="image" src="https://github.com/user-attachments/assets/2436d853-819e-4cec-96fc-a64d7309b504" />
<img width="1426" height="775" alt="image" src="https://github.com/user-attachments/assets/bc7f1046-64af-4075-aa8d-6dd1dc4933e0" />

Task 2 - Configure external collaboration settings
Sign in to the https://entra.microsoft.com as a tenant administrator.

Select Identity.

Select External Identities, and then select All identity providers.

Select the Email one-time passcode item in the list of providers, then select Configured.

Note - A one-time passcode is a very secure way to invite a user to join your organization.

Ensure that Yes is selected.

Select Save if needed.

Return to the External Identities menu.

Select External Collaboration Settings on the left

Under Guest user access, review access levels that are available and then select Guest user access is restricted to properties and memberships of their own directory objects (most restrictive).

NOTE

Guest users have the same access as members (most inclusive): This option gives guests the same access to Microsoft Entra resources and directory data as member users.
Guest users have limited access to properties and memberships of directory objects: (Default) This setting blocks guests from certain directory tasks, like enumerating users, groups, or other directory resources. Guests can see membership of all non-hidden groups.
Guest user access is restricted to properties and memberships of their own directory objects (most restrictive): With this setting, guests can access only their own profiles. Guests are not allowed to see other users' profiles, groups, or group memberships.
Screen image displaying guest user access restriction options

Under Guest invite settings, select Member users and users assigned to specific admin roles can invite guest users including guests with member permissions!

NOTE

Anyone in the organization can invite guest users including guests and non-admins (most inclusive): To allow guests in the organization to invite other guests including those who are not members of an organization, select this radio button.
Member users and users assigned to specific admin roles can invite guest users including guests with member permissions: To allow member users and users who have specific administrator roles to invite guests, select this radio button.
Only users assigned to specific admin roles can invite guest users: To allow only those users with administrator roles to invite guests, select this radio button. The administrator roles include Global Administrator, User Administrator, and Guest Inviter.
No one in the organization can invite guest users including admins (most restrictive): To deny everyone in the organization from inviting guests, select this radio button.
If Members can invite is set to No and Admins and users in the guest inviter role can invite is set to Yes, users in the Guest Inviter role will still be able to invite guests.
Screen image displaying guest invite settings with Guests can invite set to No and highlighted

Under Collaboration restrictions, review the available options and accept the default settings.

IMPORTANT

You can create either an allow list or a deny list. You can't set up both types of lists. By default, whatever domains are not in the allow list are on the deny list, and vice versa.
You can create only one policy per organization. You can update the policy to include more domains, or you can delete the policy to create a new one.
The number of domains you can add to an allow list or deny list is limited only by the size of the policy. The maximum size of the entire policy is 25 KB (25,000 characters), which includes the allow list or deny list and any other parameters configured for other features.
This list works independently from OneDrive for Business and SharePoint Online allow/block lists. If you want to restrict individual file sharing in SharePoint Online, you need to set up an allow or deny list for OneDrive for Business and SharePoint Online.
The list does not apply to external users who have already redeemed the invitation. The list will be enforced after the list is set up. If a user invitation is in a pending state, and you set a policy that blocks their domain, the user's attempt to redeem the invitation will fail.
When finished, Save your changes.

<img width="1429" height="776" alt="image" src="https://github.com/user-attachments/assets/80db21f9-9d35-4833-9a4e-759dbd9698cc" />
<img width="1425" height="774" alt="image" src="https://github.com/user-attachments/assets/f0592fe2-6977-4d3c-9339-ae771c23d294" />
<img width="1430" height="779" alt="image" src="https://github.com/user-attachments/assets/d8effb22-f17d-424e-84b9-9354821bebfa" />
<img width="1428" height="776" alt="image" src="https://github.com/user-attachments/assets/6a84352d-60f3-4c5c-8fe8-49537f953572" />
<img width="1431" height="775" alt="image" src="https://github.com/user-attachments/assets/419100ba-0715-4440-9156-e9ed86489a37" />






