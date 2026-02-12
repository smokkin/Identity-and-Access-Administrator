Lab scenario
Your company works with many vendors and, on occasion, you need to add some vendor accounts to your directory as a guest and allow them to use their Google account to sign-in.

Exercise 1 - Configure identity providers
Task 1 - Configure Google to be used as an identity provider
Important Note - For this exercise, you will need a Gmail account on Google. Create a new Google account and then follow the steps for the exercise. Be sure to note the email address and password, they are necessary to complete the lab.

Go to the Google APIs at https://console.developers.google.com, and sign in with your Google account. We recommend that you use a shared team Google account.

Accept the terms of service if you're prompted to do so.

Create a new project:

At the top of the page, select the project menu to open the Select a project page. Choose New Project. Leave the remaining fields with the default settings.

On the New Project page, give the project a name: MyB2BApp, and then select Create.

Open the new project by selecting the link in the Notifications message box or by using the project menu at the top of the page.

In the left menu, select APIs & Services, and then select OAuth consent screen.

Select the Get Started button.

On the Application information screen enter the following information:

Section	Field Name	Value
1 App Information		
App name	Microsoft Entra ID
User support email	Select the email name from the drop down
2 Audience		
Internal / External	External
3 Contact Information		
Email addresses	Use the same email address as above
4 Finish		
Agreement	Mark the checkbox
Select the Create button to continue.

Select the Create OAuth client button.

Choose Application type = Web Application.

Accept the default name for the application.

Within the Authorized JavaScript origins, select the + Add URI button.

Enter the URI https://microsoftonline.com for the value.

Within the Authorized redirect URIs, select + Add URI button. You will need to add three different URI's in this section:

First URI = https://login.microsoftonline.com
Second URI = https://login.microsoftonline.com/te/tenant ID/oauth2/authresp (where is your tenant ID)
Third URI = https://login.microsoftonline.com/te/tenant name.onmicrosoft.com/oauth2/authresp (where is your tenant name)
Lab Tip - you may find this step easier if you use Notepad in the lab VM to create these URI, and then copy and paste from there.

Lab Tip 2 - Results should look similar to this, with your Tenant ID and Tenant Name.

URI #	Link
URIs 1	https://login.microsoftonline.com
URIs 2	https://login.microsoftonline.com/te/aaaa1111bbbb2222cccc/oauth2/authresp
URIs 3	https://login.microsoftonline.com/te/MyTenantName.onmicrosoft.com/oauth2/authresp
Select the Create button.

When the item is created, copy the Client ID and the Client Secret into Notepad for user later.

You can lease your project in this state, we don't need to publish.

<img width="1431" height="778" alt="image" src="https://github.com/user-attachments/assets/e035eb37-cb4c-4b5f-9109-f9ffeb191ebb" />
<img width="1438" height="781" alt="image" src="https://github.com/user-attachments/assets/3b4c5430-763c-46f9-8be0-be59608540f6" />
<img width="1429" height="784" alt="image" src="https://github.com/user-attachments/assets/5b439d06-c7b4-4f25-9f6b-e0e1a9cdb9aa" />
<img width="1435" height="780" alt="image" src="https://github.com/user-attachments/assets/9ddf4e33-0b1b-4341-ae98-6fbb54f9dfd5" />
<img width="1437" height="781" alt="image" src="https://github.com/user-attachments/assets/d7fb53af-71cd-4ea8-abb1-9b66669c4244" />
<img width="1440" height="780" alt="image" src="https://github.com/user-attachments/assets/29068296-1551-4f09-8875-8976a8f7f7f0" />
<img width="1438" height="781" alt="image" src="https://github.com/user-attachments/assets/93cda618-a90b-49e4-92a0-a50a0c525540" />
<img width="1436" height="782" alt="image" src="https://github.com/user-attachments/assets/1a18066f-9c35-4740-b48a-90f56ef00255" />
<img width="1432" height="783" alt="image" src="https://github.com/user-attachments/assets/0c4af9ed-7b03-45bb-9742-770ddbe1ae6c" />
<img width="1434" height="783" alt="image" src="https://github.com/user-attachments/assets/c7cd9c75-9bbf-497a-873e-cd3b6b7fe56d" />
<img width="1433" height="778" alt="image" src="https://github.com/user-attachments/assets/b211ae16-8272-479b-b0e5-776c89699acc" />
<img width="1435" height="776" alt="image" src="https://github.com/user-attachments/assets/8fc8e44d-4a81-481b-9ef8-5285ec005181" />

Task 2 - Add a test user
From the menu on the left, select the Audience item.

In the Test Users section of the page, choose + Add Users.

Enter the gmail account you are using for this lab.

Select Save
<img width="1439" height="780" alt="image" src="https://github.com/user-attachments/assets/4b38c0c9-2bc4-4d16-accb-cbe2471dc257" />
<img width="1434" height="778" alt="image" src="https://github.com/user-attachments/assets/aae19fd1-ac70-44f9-9dfa-ae211a40188f" />
<img width="1445" height="778" alt="image" src="https://github.com/user-attachments/assets/23e13718-fe5b-4ab4-a171-e6debd49c54a" />

Task 3 - Add authorized domain to Branding
From the menu on the left, select the Branding item.

Scroll to the very bottom of the page.

In the Authorized domains section, add the domain microsoftonline.com.

In the Developer contact information add they email address you are using for this lab.

Select Save.
<img width="1438" height="736" alt="image" src="https://github.com/user-attachments/assets/22e638eb-4e55-4792-88a3-2bc91e3bb6cb" />
<img width="1439" height="776" alt="image" src="https://github.com/user-attachments/assets/42c5ea06-6286-4add-a42c-d72682e2dfe7" />

Exercise 2 - Configure Azure to work with an External identity provider
Task 1 - Configure Microsoft Entra ID for Google federation
Sign in to the https://entra.microsoft.com as an admin.

Select Microsoft Entra ID.

Under Identity, select External Identities.

Choose All identity providers from the menu on the left.

Microsoft provides a direct federation for Google as an identity provider.  This can be initiated by selecting + Google from the External Identities | All identity providers page

After selecting + Google, another page will open with additional information that is required to configure Google as an identity provider.

Enter the Client ID and Client secret you obtained earlier.

Select Save.
<img width="1435" height="778" alt="image" src="https://github.com/user-attachments/assets/fc010017-0512-4478-90a0-fc9373a94588" />
<img width="1430" height="779" alt="image" src="https://github.com/user-attachments/assets/533aa1f5-69c9-4e2f-a0ca-667237e7eca4" />
<img width="1436" height="778" alt="image" src="https://github.com/user-attachments/assets/ea95ca15-ce40-4e61-b5ee-f4e945bcc9a6" />
<img width="1429" height="774" alt="image" src="https://github.com/user-attachments/assets/4c13939f-3ff6-41c7-9c2f-4023a07ce7ef" />

Task 2 - Invite you Test User account
If you used an existing Gmail account, remember to delete the account with External Identities | All identity providers. You can also return to the Google developer console and delete the project that you created.

Open Microsoft Entra ID.

Go to Users and select All users.

Select + New User.

Choose Invite external user from the dropdown menu.

Enter the information for the gmail account you set up as a test user for the Google App in Exercise 1 Task 2.

Enter a personal message as you want.

Select Review & Invite then select Invite.

Security Note
If you are using an existing Gmail account that has Passkeys enable, you will be unable to complete the login processs within the lab environment. Passkey requires BlueTooth, which cannot be enabled through the VM. You can still complete the lab, just do these last few tasks in an InPrivate brower running outside the lab environment.
<img width="1431" height="778" alt="image" src="https://github.com/user-attachments/assets/83b4f4e4-5805-4dfa-9e38-e33c0608c275" />
<img width="1428" height="779" alt="image" src="https://github.com/user-attachments/assets/b502cf2b-ea0b-42e4-999b-d8ff36c840b7" />
<img width="1432" height="776" alt="image" src="https://github.com/user-attachments/assets/f5b200e1-0ce7-4ead-bce8-d68f9df060c7" />
<img width="1382" height="755" alt="image" src="https://github.com/user-attachments/assets/24c51f8f-7463-4d34-88ea-bc06ac67f4fe" />
<img width="1431" height="776" alt="image" src="https://github.com/user-attachments/assets/89aff7ad-6a3c-4cde-a1dc-f4ef2a0f5a85" />
Task 3 - Accept the invitation and login
Use an InPrivate browser to log into your gmail account.

Open the Microsoft Invitation on behalf of in the Inbox.

Select the Accept invitation link in the message.

Enter your username and password as requested in the login dialog (if requested).

NOTE If the ferderation is working correctly, this is where you will see the first results of your new Google External Identity provider. You will go to the login screen and be able to log in with your gmail credentials. If the federation is not work, or has not been set up, the user would be sent and ACCOUNT VERIFICATION email after the log in, to confirm the account. With the federation, no extra verification is needed.

NOTE If you get an access error 500, wait about 30 seconds and refresh the page. Choose to RESUBMIT. This error is a timing issue only in the lab environment.

Read over the new Permissions requested by: message that you get. This message is coming from your Azure Lab Domain.

Choose Accept.

Once login is complete, you will be sent My Apps.
<img width="1426" height="775" alt="image" src="https://github.com/user-attachments/assets/f5ecd930-2603-445a-865a-25c8869c9139" />
<img width="1424" height="770" alt="image" src="https://github.com/user-attachments/assets/532da45b-45a1-4388-8dfc-89cff9e619a9" />

Task 4 - Login to Microsoft 365 using your Google account
Once you have finished the external user invite process of Task 3, you can log directly into Microsoft Online.

Open a new tab in the browser you have open.

NOTE if you did not open a new InPrivate browser in Task 3, you should do so for this step.

Enter the following web address:

TypeCopy
login.microsoftonline.com
Select Sign-in options on the dialog.

Choose Sign in to an organization.

Enter your lab tenant domain name in the box and select Next.

Enter the Google email address and password that you created.

At this point, you should see your account passed to Google for confirmation; then enter the Microsoft Office portal.
<img width="1434" height="779" alt="image" src="https://github.com/user-attachments/assets/4f558571-0331-428e-a5db-94a3243a3820" />
<img width="1424" height="771" alt="image" src="https://github.com/user-attachments/assets/164ab520-a826-40eb-98b5-a0797880e543" />
<img width="1431" height="772" alt="image" src="https://github.com/user-attachments/assets/5204a493-cefd-4aa3-be9c-95dc156ed065" />
<img width="1430" height="769" alt="image" src="https://github.com/user-attachments/assets/7e1486e0-d7f1-4d1b-9283-28f7cf6ba711" />
<img width="1430" height="772" alt="image" src="https://github.com/user-attachments/assets/451ec26e-e71b-4a44-bf73-97ee569b5289" />
























