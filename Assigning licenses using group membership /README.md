Lab 03: Assigning licenses using group membership
Login type = Microsoft 365 + E5 tenant log-in
Lab scenario
Your organization has decided to use security groups in Microsoft Entra ID to manage licenses. You need to configure a new security group and assign a license to that group and verify group member license's have been updated.

Estimated time: 25 minutes
Exercise 1 - Create a security group and add a user
Task 1 - Check to see if Delia Dennis has access to Office 365
Launch a new InPrivate browser window.

Connect to https://www.office.com.

Select Sign in and connect as Delia Dennis.

Setting	Value
Username	DeliaD@your domain name.com
Password	Enter the User password provided for DeliaD
You should connect to the Office.com website, but see a message indicating you don't have a license.

Screen image the Office.com website with Delia Dennis logged in but no office applications are available, because no license is assigned.
<img width="1431" height="771" alt="image" src="https://github.com/user-attachments/assets/bdbfbde6-538a-4339-bf01-48235536dc17" />

Task 2 - Create a security group in Microsoft Entra ID
Browse to https://entra.microsoft.com.

In the left navigation, under Identity, select Groups, then select All groups.

In the Groups page, on the menu, select New group.

Create a group using the following information:

Setting	Value
Group type	Security
Group name	sg-SC300-O365
Membership type	Assigned
Owners	Assign your own administrator account as the group owner
Select the No members selected text under Members.

Select Delia Dennis from the list of users.

Select the Select button.

Screen image displaying the New Group page with Group type, Group name, Owners, and Members highlighted

Select the Create button.

When complete, verify the group named sg-SC300-O365 is shown in the All groups list.
<img width="1430" height="773" alt="image" src="https://github.com/user-attachments/assets/02554469-2fc9-4b91-a4cc-c8bf18ac28ff" />
<img width="1426" height="772" alt="image" src="https://github.com/user-attachments/assets/9f16aa6a-89b9-4f54-b305-7367779d06b2" />
<img width="1428" height="774" alt="image" src="https://github.com/user-attachments/assets/524568a1-35de-4f28-8c85-b33cdb03505a" />
<img width="1431" height="777" alt="image" src="https://github.com/user-attachments/assets/c6570549-b536-4488-bf5c-96f9ff808124" />
<img width="1430" height="770" alt="image" src="https://github.com/user-attachments/assets/303f11b6-891a-4f01-ac2a-f42a850f3c7f" />

Task 3 - Add an Office license to sg-SC300-O365
Lab Tip - You have to add and remove licenses via the Microsoft 365 admin center. This is a relatively new change.

Open a new tab in your browser.

Connect to the Microsoft 365 admin center at http://admin.microsoft.com.

Log in as your administrator account if prompted.

From the menu on the left, select Billing and then select Licenses.

Select Office 365 E3 license from the list.

Select the Groups tab on the licensing screen.

Choose the + Assign licenses item.

Search for sg-SC300-O365 group the select it from the list.

Once you have added the group, select Assign.

Close the confirmation message.

Return to the browser tab with Microsoft Entra admin center open.

Navigate back to the All groups in the left navigation, under Identity, select Groups

In the Groups page, select sg-SC300-O365.

In the left navigation, select Licenses.

Notice that the Office 365 E3 license has been assigned.
<img width="1431" height="776" alt="image" src="https://github.com/user-attachments/assets/1506285c-67c0-4316-836f-aa7750583751" />
<img width="1428" height="774" alt="image" src="https://github.com/user-attachments/assets/6c4648f5-7c6b-40c0-9898-53dbfa99e6e5" />
<img width="1426" height="772" alt="image" src="https://github.com/user-attachments/assets/571f3882-1713-410b-b0bf-f059a49fd531" />
<img width="1428" height="774" alt="image" src="https://github.com/user-attachments/assets/25a8bbd6-38de-4da5-a723-1a6147364007" />
<img width="1427" height="772" alt="image" src="https://github.com/user-attachments/assets/4cbfe52a-e0a5-47d6-99b4-1a4613957398" />

Task 4 - Confirm the Office 365 license
Launch a new InPrivate browser window.

Connect to https://www.office.com.

Select Sign in and connect as Delia Dennis.

Setting	Value
Username	DeliaD@your domain name.com
Password	Enter the password of the provided password
You should connect to the Office.com website, and see no messages regarding license. All of the Office applications are available on the left.

Screen image the Office.com website with Delia Dennis logged in with office applications available, because a license is assigned.
<img width="1429" height="771" alt="image" src="https://github.com/user-attachments/assets/83a306b7-1433-47d1-8564-ccf09dad20c4" />

<img width="1427" height="772" alt="image" src="https://github.com/user-attachments/assets/549ad2b4-9404-44f4-b80b-ab3924d06405" />


<img width="1427" height="773" alt="image" src="https://github.com/user-attachments/assets/f36abfbf-ea41-4db1-b2ee-16031ce97c3f" />
<img width="1431" height="770" alt="image" src="https://github.com/user-attachments/assets/ec0a676c-14ef-4dbf-b5f5-b7d226d3e950" />
<img width="1428" height="775" alt="image" src="https://github.com/user-attachments/assets/52ff22e8-af1c-472d-8f6e-dcb8dd5f53df" />
<img width="1430" height="776" alt="image" src="https://github.com/user-attachments/assets/4fdfa22f-3c24-48ff-97ac-f43c37327ae5" />


<img width="1427" height="780" alt="image" src="https://github.com/user-attachments/assets/6835b88a-dee0-418b-9638-060d9dd66aed" />
<img width="1424" height="771" alt="image" src="https://github.com/user-attachments/assets/bb2cd8c0-b2a9-4cba-bb01-3f738236a6bc" />
<img width="1432" height="773" alt="image" src="https://github.com/user-attachments/assets/48d6e076-3f00-4062-abf0-8a19dc72c6e6" />
<img width="1427" height="776" alt="image" src="https://github.com/user-attachments/assets/c695345f-ade9-4c80-9b3e-9a5d26463512" />
<img width="1424" height="773" alt="image" src="https://github.com/user-attachments/assets/218a2599-51c7-499d-9af5-b60611e0dfb8" />
<img width="1431" height="774" alt="image" src="https://github.com/user-attachments/assets/9e009300-442b-451c-a1a4-1ab93d01f3fd" />
<img width="1429" height="772" alt="image" src="https://github.com/user-attachments/assets/32af7f7c-b732-4393-9d27-1479a51a5f2d" />


<img width="1425" height="773" alt="image" src="https://github.com/user-attachments/assets/eac713af-2ffc-4476-900c-0eb2541464bb" />
<img width="1428" height="772" alt="image" src="https://github.com/user-attachments/assets/74ecacfd-c2c8-464a-9dde-95a434544473" />


<img width="1427" height="779" alt="image" src="https://github.com/user-attachments/assets/86ba676b-9a4f-4707-80a5-53069501b1f5" />
<img width="1429" height="771" alt="image" src="https://github.com/user-attachments/assets/65ef7c2e-2903-4f2d-840b-e4e397f67a9d" />
<img width="1432" height="776" alt="image" src="https://github.com/user-attachments/assets/104ab204-fb59-4651-932a-0707de8a0575" />
<img width="1430" height="770" alt="image" src="https://github.com/user-attachments/assets/65463e34-83c1-48f1-a7c1-02c46b56197a" />
<img width="1430" height="769" alt="image" src="https://github.com/user-attachments/assets/ca5f037a-296a-4ad2-9772-8fadc1cff83e" />
<img width="1428" height="776" alt="image" src="https://github.com/user-attachments/assets/a789afd2-9f53-4226-8f4a-79bcaee59518" />
<img width="1424" height="774" alt="image" src="https://github.com/user-attachments/assets/d61162b9-0dc0-4d94-b9c2-06991835ccac" />
<img width="1426" height="774" alt="image" src="https://github.com/user-attachments/assets/4c6b4ab0-8da3-46e5-a7bb-108bb6aa56e6" />














