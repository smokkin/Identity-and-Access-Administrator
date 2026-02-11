Lab scenario
Your company works with many vendors and, on occasion, you need to add some vendor accounts to your directory as a guest.

Exercise 1 - Add guest users to the directory
Task - Add the guest user
Sign in to the https://entra.microsoft.com as a user who is assigned a limited administrator directory role or the Guest Inviter role, or as Global Administrator.

Select Identity.

Under Users, select All users.

Select + New user.

On the New user menu, select Invite external user and then add your information as the guest user.

NOTE - Group email addresses are not supported; enter the email address for an individual. Also, some email providers allow users to add a plus symbol (+) and additional text to their email addresses to help with things like inbox filtering. However, Microsoft Entra ID does not currently support plus symbols in email addresses. To avoid delivery issues, omit the plus symbol and any characters following it up to the @ symbol.

Enter an email address, such as sc300externaluser1@sc300email.com.

Select the Properties tab.

On the Users page, verify your account is listed and, in the User type column, verify Guest is shown.

When complete, select Review + Invite, then select Invite.

After you send the invitation, the user account is automatically added to the directory as a guest.
<img width="1432" height="770" alt="image" src="https://github.com/user-attachments/assets/c1ed5761-6498-4897-851a-56e20eae16d6" />
<img width="1428" height="778" alt="image" src="https://github.com/user-attachments/assets/3d975639-1628-4cbf-a2d4-452774a2bbc6" />
<img width="1430" height="777" alt="image" src="https://github.com/user-attachments/assets/f3dd6da9-f6df-49b8-9e4a-3481765b6904" />

Exercise 2 - Invite guest users in bulk
Task 1 - Bulk user invite
A recent partnership has been established with another company. For now, employees of the partner company will be added as guests. You need to ensure you can import multiple guest users at one time.

Sign in to the https://entra.microsoft.com as your Global Administrator.

In the navigation pane, select Identity.

Under Users, select All users.

On the Users page, on the menu, select Bulk operations > Bulk invite.

Screen image displaying the All user page with the Bulk operations and Bulk invite menu options highlighted

In the Bulk invite users pane, select Download to a sample CSV template with invitation properties.

Using an editor to view the CSV file, review the template.

Open the .csv template and add a line for each guest user. Required values are:

Email address to invite - the user who will receive an invitation
Redirection url - the URL to which the invited user is forwarded after accepting the invitation.
Screen image displaying the example bulk invite guests template CSV

Lab Tip - The users listed in the screenshot and the template files are examples, they don't really exist. You will have to add a real users to fully test this feature.

Save the file.

On the Bulk invite users page, under Upload your csv file, browse to the file.

Note - When you select the file, validation of the .csv file starts.

After the file contents are validated, you will see File uploaded successfully. If there are errors, you must fix them before you can submit the job.

Screen image displaying Bulk invite users with File uploaded successfully message highlighted

When your file passes validation, select Submit to start the Azure bulk operation that adds the invitations.

To view the job status, select Select here to view the status of each operation. Or, you can select Bulk operation results in the Activity section. For details about each line item within the bulk operation, select the values under the # Success, # Failure, or Total Requests columns. If failures occurred, the reasons for failure will be listed.

Screen image displaying the results of a bulk operation

When the job completes, you will see a notification that the bulk operation succeeded.


