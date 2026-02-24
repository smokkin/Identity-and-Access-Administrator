As an additional layer of security, you need to enable and configure your Microsoft Entra organization's sign in and user risk policies.

Exercise 1 - Enable User risk policy
Task 1 - Configure the policy
Sign in to the https://entra.microsoft.com using a Global administrator account.

Open the portal menu and then select Entra ID.

On menu, under ID Protection, select Dashboard.

5. In the Identity protection Dashboard, in the left navigation, select User risk policy.

Screen image displaying the User risk policy page and highlighted browsing path

Under Assignments, select All users and review the available options.

You can select from All users or Select individuals and groups if limiting your rollout.

Additionally, you can choose to exclude users from the policy.

Under User risk, select Low and above.

In the User risk pane, select High and then select Done.

Under Controls > Access, select Block access.

In the Access pane, review the available options.

Tip - Microsoft's recommendation is to Allow access and Require password change.

Select the Require password change check box and then select Done.

Under Policy enforcement, select Enabled and then select Save.

<img width="1427" height="769" alt="image" src="https://github.com/user-attachments/assets/88df7a30-b47f-426a-87c3-22b4fe1f20e1" />
<img width="1428" height="781" alt="image" src="https://github.com/user-attachments/assets/4347dc1a-1376-4df2-8fa6-01ff3e85d8fb" />
<img width="1426" height="778" alt="image" src="https://github.com/user-attachments/assets/b56457d0-5bb4-4a9a-ae04-5df94cb623ab" />
<img width="1428" height="768" alt="image" src="https://github.com/user-attachments/assets/dd3a72de-d0e6-48da-8399-377404881c44" />
<img width="651" height="43" alt="image" src="https://github.com/user-attachments/assets/476f8e17-95c4-482f-a1ef-9d414db593b5" />



Task 2 - Enable Sign-in risk policy
On the Identity protection page, in the left navigation, select Sign-in risk policy.

As with the User risk policy, the Sign-in risk policy can be assigned to users and groups and allows you to exclude users from the policy.

Under Sign-in risk, select Low and above.

In the Sign-in risk pane, select High and then select Done.

Under Controls > Access, select Block access.

Select the Require multi-factor authentication check box and then select Done.

Under Policy enforcement, select Enabled and then select Save.
<img width="1431" height="768" alt="image" src="https://github.com/user-attachments/assets/e68aaf44-c81b-43fe-a5ed-99beec79e8d2" />
<img width="647" height="38" alt="image" src="https://github.com/user-attachments/assets/fe2a4712-7e4f-444d-aacd-fb80964545e2" />




