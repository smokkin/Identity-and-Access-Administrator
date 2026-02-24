Microsoft Defender for Cloud Apps utilizes logs from network traffic to identify the applications that users are accessing.  Traffic logs from on-premises firewalls will provide a snapshot report on the most common applications and the users that are accessing these apps.  Traffic from managed devices will be fed into the Microsoft Defender for Cloud Apps discovery overview dashboard

Exercise 1 - Defender for Cloud Apps discovery
Task 1 - Discovery apps in Defender for Cloud Apps
Sign in to https://security.microsoft.com using a Global Administrator account.

On the left menu, scroll to the heading named Cloud Apps and click Cloud App Catalog.

In Browse by category pane, select Cloud storage.

In the list of apps, note the Risk score next to the app name.

Open another browser tab and navigate to www.dropbox.com.

You will be able to access this website.

Close the tab for Dropbox.

Return to the Defender for Cloud Apps screen, and select the three-dot to the right of Dropbox.

Choose Sanctioned and then the Next button.

<img width="1426" height="764" alt="image" src="https://github.com/user-attachments/assets/7ae9bdb1-2fa7-44ad-9554-8b0787a9960a" />
<img width="1427" height="764" alt="image" src="https://github.com/user-attachments/assets/6c15e7a7-9e08-4a4c-900f-671b6ade6217" />
<img width="1427" height="767" alt="image" src="https://github.com/user-attachments/assets/5099c140-34e5-419f-9039-c2ab1f5444d4" />
<img width="1424" height="766" alt="image" src="https://github.com/user-attachments/assets/2f9e0e31-83bb-4a7e-97e9-af3fcf1f18a4" />
<img width="1427" height="766" alt="image" src="https://github.com/user-attachments/assets/8d3e2386-c0fc-411e-8d58-a9f29807aed2" />

Task 2 - Restrict Apps in Defender for Cloud Apps
Return to the Discovered apps tile and select the Tag as unsanctioned for Dropbox. Note: This is located next to the circled check-mark.

Click Save

This process allows you to block applications that are not sanctioned within your company policy, limiting Shadow IT within your organization.

Note: There is a delay when sactioning and unsanctioning an application and that application. You may have to wait up to 5 minutes.

Once the application has been blocked as unsanctioned, the application will not be accessible through browser, in-private browser, or store download on a Client that is onboarded to MDE (Microsoft Defender for Endpoint) integrated with Microsoft Defender for Cloud Apps.

<img width="1429" height="762" alt="image" src="https://github.com/user-attachments/assets/4c2c2c20-858b-42e0-bc33-403819feb3bf" />
<img width="1428" height="767" alt="image" src="https://github.com/user-attachments/assets/0447832e-e084-44ce-846b-4d456ab8a39e" />






