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
<img width="1438" height="781" alt="image" src="https://github.com/user-attachments/assets/3b4c5430-763c-46f9-8be0-be59608540f6" />
![Uploading image.png…]()
![Uploading image.png…]()

<img width="1431" height="778" alt="image" src="https://github.com/user-attachments/assets/e035eb37-cb4c-4b5f-9109-f9ffeb191ebb" />
