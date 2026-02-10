Exercise 1 - Create a custom subdomains
Task 1 - Create a custom subdomain name
You would use Microsoft Entra ID to create a domain that you have purchased. If you want to create a subdomain to divide your existing .onmicrosoft.com domain, you have to use the Microsoft 365 admin center.

Browse to the https://entra.microsoft.com and sign in using a Global administrator account for the directory.

In the Identity menu, use the Show more option at the bottom.

Open the Settings menu, select Domain names.

Select + Add custom domain.

In the Custom domain name field, create a custom subdomain for the lab tenant by putting sales in front of the onmicrosoft.com domain name. The format will look similar to this:

TypeCopy
Sales.labTenantName.onmicrosoft.com
Note - You will be prompted to open the Microsoft 365 Admin center to complete this action.

Select Add domain to add the subdomain.

Enter the subdomain name sales.tenantname.onmicrosoft.com into the dialog. Remember to replace tenantname with the name of your tenant.

Select the Use this domain button at the bottom of the screen.

Select the Close button when the next screen opens up. For the purpose of this lab we will not set up the DNS.
<img width="1433" height="774" alt="image" src="https://github.com/user-attachments/assets/130d106a-5a91-4ddf-8f2d-7380bf2356a6" />
<img width="1430" height="769" alt="image" src="https://github.com/user-attachments/assets/d66c4782-3f00-4175-a885-c217e78eefdc" />
<img width="1433" height="774" alt="image" src="https://github.com/user-attachments/assets/16ee835b-8b24-47c4-81d0-a94748071eaf" />
<img width="1428" height="771" alt="image" src="https://github.com/user-attachments/assets/39b0be4f-d677-45b0-a47f-da81566aa3a6" />

Exercise 2 - Changing the tenant display name
Task 1 - Set the tenant name and technical contact
From within Microsoft Entra admin center, open the Identity menu.

In the left navigation, select Overview menu item, then select Properties.

Change the Tenant Properties for the Name and Technical contact in the dialog.

Setting	Value
Name	Contoso Marketing
Technical contact	your Global admin account
Select Save to update the tenant properties.

You will notice the name change immediately upon completion of the save.
<img width="1428" height="780" alt="image" src="https://github.com/user-attachments/assets/810b744e-bba5-4cf3-8fb7-5c2ab9bda42e" />

Task 2 - Review the Country or region and other values associated with your tenant
In the Identity menu, select Overview, then select Properties.

Under Tenant properties, locate Country or region and review the information.

IMPORTANT - When the tenant is created, the Country or region are specified at that time. This setting cannot be changed later.

In the Properties page, under Tenant properties, locate Location and review the information.

Screen image showing the Azure Active Directory Properties page with the Country or region and Location settings highlighted
<img width="1429" height="777" alt="image" src="https://github.com/user-attachments/assets/6c9d0492-6bc2-4013-8984-8b20dd28e9be" />

Task 3 - Finding the tenant ID
Azure subscriptions have a trust relationship with Microsoft Entra ID. Microsoft Entra ID is trusted to authenticate users, services, and devices for the subscription. Each subscription has a tenant ID associated with it, and there are a few ways you can find the tenant ID for your subscription.

Open the Microsoft Entra admin center https://entra.microsoft.com

In the Identity menu, select Overview, then select Properties.

Under Tenant properties, locate Tenant ID. This is your unique tenant identifier.

Screen image displaying the Tenant properties page with the Tenant ID box highlighted

Note - It is helpful if you record your Tenant-Id note Notepad or other location for use in future labs.
<img width="1430" height="776" alt="image" src="https://github.com/user-attachments/assets/228a7b49-e7ae-47ad-b7a7-128abfcbd4bc" />

Exercise 3 - Setting your privacy information
Task 1 - Adding your privacy info on Microsoft Entra ID, including Global privacy contact and Privacy statement URL
Microsoft strongly recommends you add both your global privacy contact and your organization's privacy statement, so your internal employees and external guests can review your policies. Because privacy statements are uniquely created and tailored for each business, we strongly recommend you contact a lawyer for assistance.

NOTE - For information about viewing or deleting personal data, see https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure. For more information about GDPR, see the https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted.

You add your organization's privacy information in the Properties area of Microsoft Entra ID. To access the Properties area and add your privacy information:

In the Identity menu, select Overview, then select Properties.

Screen image displaying tenant properties with the Technical contact, Global contact, and Privacy statement boxes highlighted

Add your privacy info for your employees:

Global privacy contact - AllanD@ your Azure lab domain

Allan Deyoung is a built-in users in your Azure lab tenant who works as an IT Admin, we will use him as the Privacy contact.
This person is also who Microsoft contacts if there's a data breach. If there's no person listed here, Microsoft contacts your global administrators.
Privacy statement URL - https://github.com/MicrosoftLearning/SC-300-Identity-and-Access-Administrator/blob/master/Allfiles/Labs/Lab2/SC-300-Lab_ContosoPrivacySample.pdf

In sample Privacy PDF is provided in your labs directory. - Type the link to your organization's document that describes how your organization handles both internal and external guest's data privacy.
IMPORTANT -If you don't include either your own privacy statement or your privacy contact, your external guests will see text in the Review Permissions box that says,  has not provided links to their terms for you to review. For example, a guest user will see this message when they receive an invitation to access an organization through B2B collaboration.

B2B Collaboration Review permissions box with message

Select Save.
<img width="1424" height="770" alt="image" src="https://github.com/user-attachments/assets/a45481ca-fa80-4273-ba60-3f46c9778e23" />
<img width="1425" height="773" alt="image" src="https://github.com/user-attachments/assets/7540364f-ed7e-4305-9e36-ae7b009920a5" />

Task 2 - Check your Privacy Statement
Return to the Azure Home screen - Dashboard.

In the upper-right corner of the UI, Select on your username.

Choose View account from the dropdown menu.

A new browser tab will open automatically.

Select the Settings & Privacy on the left menu.

Select Privacy.

Under Organization's notice select the View item next to Contoso Marketing organizational privacy statement.

A new browser tab will open with the Prvacy PDF file you linked to displayed.

Review the sample Privacy statement.

Close the browser tab with the PDF in it.

<img width="1428" height="773" alt="image" src="https://github.com/user-attachments/assets/7f32711b-e34c-428c-abef-9da90fb8704a" />
<img width="1430" height="775" alt="image" src="https://github.com/user-attachments/assets/15b925ff-1198-4a5c-8da9-39f3e8ff36e2" />








