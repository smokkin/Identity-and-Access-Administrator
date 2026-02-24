The company has decided to empower the employees and enable self-service password reset. You must configure this setting in your organization.
Exercise 1 - Create a group with SSPR enabled and add users to it
Task 1 - Create a group to assign SSPR to
You want to roll out SSPR to a limited set of users first to make sure your SSPR configuration works as expected. Let's create a security group for the limited rollout and add a user to the group.

On the Microsoft Entra admin center, open the Identity navigation menu on the left.

Under Groups, select All groups and select New Group on the right side window.

Create a new group using the following information:

Setting	Value
Group type	Security
Group name	SSPRTesters
Group description	Testers of SSPR rollout
Membership type	Assigned
Members	Alex Wilber
Allan Deyoung
Bianca Pisani
Select Create.

<img width="1425" height="770" alt="image" src="https://github.com/user-attachments/assets/36d2580f-a399-4e1f-8676-a08dc030f9be" />
<img width="1427" height="770" alt="image" src="https://github.com/user-attachments/assets/a66f1566-7425-4dd1-81bb-208f5afb45ba" />
<img width="1425" height="767" alt="image" src="https://github.com/user-attachments/assets/bae0228b-eeb4-443b-a6d1-9b7c91438ec0" />

Task 2 - Enable SSPR for you test group
Enable SSPR for the group.

Browse back to the Identity navigation menu.

Under Protection, select Password reset.

On the Password reset page Properties page, under Self service password reset enabled, select Selected.

Under Select group, replace the existing SSPRSecurityGroupUsers with SSPRTesters you just created.

On the Password reset page Properties page, select Save.

Screen image displaying the Password reset properties page with selected, select group, and save highlighted

On the Password reset screen, look under Manage*, select and review the default values for each of the **Authentication methods, Registration, Notifications, and Customization settings.

Note it is important to have phone selected as one of the authentication methods for the rest of this lab, but you can have other options as well.
<img width="1431" height="763" alt="image" src="https://github.com/user-attachments/assets/87bc7e6e-adf2-4aac-8ee8-d39bd6a6145e" />
<img width="1420" height="764" alt="image" src="https://github.com/user-attachments/assets/12521a81-9e52-40dd-bd23-614a9a183546" />
<img width="1429" height="768" alt="image" src="https://github.com/user-attachments/assets/4a7dca27-6c67-45ac-a1f5-3d3a71a46659" />
<img width="1430" height="767" alt="image" src="https://github.com/user-attachments/assets/d99ccc65-53b0-4980-adb9-f72befa965e7" />
<img width="1430" height="768" alt="image" src="https://github.com/user-attachments/assets/ea614280-e23b-4253-8983-bb6cad733d0a" />
<img width="1423" height="762" alt="image" src="https://github.com/user-attachments/assets/458a704a-d59a-44d4-8964-f0b9728c46cf" />
<img width="1430" height="766" alt="image" src="https://github.com/user-attachments/assets/ef67d0ed-3216-4e9d-9c43-af7b26cf8c4e" />
<img width="1422" height="768" alt="image" src="https://github.com/user-attachments/assets/c23abba8-15af-496b-81b6-feb806542999" />

Taks 3 - Register for SSPR with Allan
Now that the SSPR configuration is complete, register a mobile phone number for the user you created.

Open a different browser or open an InPrivate or Incognito browser session and then browse to https://aka.ms/ssprsetup.

This is to ensure you are prompted for user authentication.

Sign in as AllanD@ <<organization-domain-name>>.onmicrosoft.com with the password provided.

Note - Replace the organization-domain-name with your domain name.

If prompted to update your password, enter a new password of your choice. Be sure to record the new password.

If prompted to stay signed in, choose Yes.

In the More information required dialog box, select Next.

On the Keep your account secure page, select Next to use the Authenticator app.

Follow the on screen instructions to set up your account in Authenticator by scanning the QR-code.

Complete the process by selecting Done when you successfully registered.

Note - at this point you have both registered for SSPR and MFA in a single step.
<img width="482" height="680" alt="image" src="https://github.com/user-attachments/assets/85a96e47-f6e0-4db9-891a-35476591ad34" />
<img width="609" height="684" alt="image" src="https://github.com/user-attachments/assets/e437c5ff-a29d-4b0a-bb0f-14d5b0bbbb39" />
<img width="1443" height="814" alt="image" src="https://github.com/user-attachments/assets/3aed95df-3ea6-42e3-a563-d19eba86a1c7" />

Task 4 - Test SSPR
Now let's test whether the user can reset their password.

Open a different browser or open an InPrivate or Incognito browser session and then browse to https://portal.azure.com.

This is to ensure you well be prompted for user authentication.

enter AllanD@ <<organization-domain-name>>.onmicrosoft.com and then select Next.

Note - Replace the organization-domain-name with your domain name.

On the Enter password page, select Forgot my password.

On the Get back into your account page, complete the requested information and then select Next.

Follow the on-screen instructions to get the verification code from Microsoft Authenticator app.

Enter your verification code and then select Next.

In the choose a new password step, enter and then confirm your new password.

When complete, select Finish.

Sign in as AllanD with the new password you created.

Enter your verification code and then verify you can complete the sign in process.

<img width="457" height="453" alt="image" src="https://github.com/user-attachments/assets/8a1a9263-b4fc-4f19-be28-17a2691ea9db" />
<img width="513" height="416" alt="image" src="https://github.com/user-attachments/assets/52b7e518-88cb-41c4-a448-961a55f463e8" />
<img width="1427" height="766" alt="image" src="https://github.com/user-attachments/assets/87628b38-3e95-4975-9bd6-be0c63a738c7" />
<img width="1426" height="768" alt="image" src="https://github.com/user-attachments/assets/52ffd445-7eb6-4a1e-8309-8011880bc5f7" />
<img width="1427" height="765" alt="image" src="https://github.com/user-attachments/assets/6c991b03-b570-45d7-8cb4-593cf37247d1" />
<img width="1427" height="765" alt="image" src="https://github.com/user-attachments/assets/ecc1f9dd-7a0c-48e6-a4c5-46d9e2032ab5" />
<img width="1428" height="767" alt="image" src="https://github.com/user-attachments/assets/a68784f2-13b5-43eb-99c9-a06ac8e6e00a" />
<img width="423" height="390" alt="image" src="https://github.com/user-attachments/assets/23ccca5f-38c1-4391-9b08-e4e913f78cbb" />
<img width="426" height="577" alt="image" src="https://github.com/user-attachments/assets/d7ddd4cd-5c6e-4425-afc9-5a61e05fc821" />
<img width="1427" height="766" alt="image" src="https://github.com/user-attachments/assets/f662cd3f-4ae1-45ac-85d0-425c7a8d4ddf" />

Task 5 - What happens if you try a user not in SSPRTesters group?
As a test, open a new InPrivate browser window and try to log into the Azure Portal as GradyA, and select Forgot my password option.
<img width="444" height="400" alt="image" src="https://github.com/user-attachments/assets/8223af8f-be51-490e-a75e-d4cc374721bc" />
<img width="1431" height="765" alt="image" src="https://github.com/user-attachments/assets/7bb36688-1a93-435a-8c67-0d5b8c7dd0b1" />







