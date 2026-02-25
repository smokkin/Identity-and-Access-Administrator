A catalog is a container of resources and access packages. You create a catalog when you want to group related resources and access packages. Whoever creates the catalog becomes the first catalog owner. A catalog owner can add additional catalog owners. You must create and configure a catalog in your organization.

Exercise 1 - Building out resources in Entitlement Management
Task 1 - Create a catalog
Sign in to https://entra.microsoft.com using a Global Administrator account.

Important - To use and configure Microsoft Entra ID terms of use, you must have:

Microsoft Entra ID Premium P1, P2, EMS E3, or EMS E5 subscription.
If you don't have one of these subscriptions, you can get Microsoft Entra ID Premium trial.
One of the following administrator accounts for the directory you want to configure:
Global Administrator
Security Administrator
Conditional Access Administrator
Open the Identity menu, and then select Identity Governance.

In the left menu, under Entitlement management, select Catalogs.

On the top menu, select + New Catalog.

Screen image displaying the Identity governance catalog page with the New catalog menu highlighted 

In the New catalog pane, in the Name box, enter Marketing.

In the Description box, enter For marketing department users. Users will see this information in an access package's details.

Under Enabled, select Yes.

Enabled for external users select No. This setting allows users in selected external directories to be able to request access packages in this catalog. No changes will be made to this setting.
You may choose to enable the catalog for immediate use or disable if you intend to stage it or keep it unavailable until you intend to use it. For this exercise, the catalog does not need to be enabled.

Screen image displaying the New catalog pan with the Name, Description, Enabled, and Create options highlighted

Select Create.
<img width="1433" height="774" alt="image" src="https://github.com/user-attachments/assets/fdb51a2d-6901-483b-aa08-d30a22702269" />
<img width="1429" height="771" alt="image" src="https://github.com/user-attachments/assets/32b3f19a-0dc2-4274-8291-20979ce35edd" />

Task 2 - Add resources to a catalog
To include resources in an access package, the resources must exist in a catalog. The types of resources you can add are groups, applications, and SharePoint Online sites. The groups can be cloud-created Microsoft 365 Groups or cloud-created Microsoft Entra security groups. The applications can be Microsoft Entra enterprise applications, including both SaaS applications and your own applications federated to Microsoft Entra ID. The sites can be SharePoint Online sites or SharePoint Online site collections.

On the Identity Governance page, if necessary, select Catalogs.

In the Catalogs list, select Marketing.

In the left navigation, under Manage, select Resources.

On the menu, select + Add resources.

In the Add resources to catalog page, review the available options. Add the following items:

Resource Type	Value
Groups and Teams	Retail
Applications	Box
Applications	Salesforce
SharePoint sites	Brand - pick this SharePoint from your list of available sites
You may not have any resources in Groups and Teams, Applications, or SharePoint sites. Select any resource category and then select a resource from that category.

For this exercise, it is okay to choose any resource you may have available.

Add resources to a catalog

When finished, Select Add. These resources can now be included in access packages within the catalog.
<img width="1431" height="764" alt="image" src="https://github.com/user-attachments/assets/f49b1be7-1b0e-426b-b531-4ee4430f2c31" />
<img width="1429" height="769" alt="image" src="https://github.com/user-attachments/assets/909db052-5037-4a56-8823-fdf2459d5053" />

Task 3 - Add additional catalog owners
The user that created a catalog becomes the first catalog owner. To delegate management of a catalog, you add users to the catalog owner role. This helps share the catalog management responsibilities.

If necessary, in the Microsoft Entra admin center, browse to Identity, then select Identity Governance and select Catalogs and then select Marketing.

In the Marketing catalog page, in the left navigation menu, select Roles and administrators.

Screen image displaying the Roles and administrators page for the Marketing catalog

On the top menu, review the available roles and then select + Add catalog owner.

In the Select members pane, select your Adele Vance and then select Select.

Review the newly added role in the Roles and administrators list.

<img width="1428" height="764" alt="image" src="https://github.com/user-attachments/assets/23d8bf87-1620-429f-b363-e784cd3fa40f" />
<img width="1434" height="768" alt="image" src="https://github.com/user-attachments/assets/bfb64a47-2410-4280-a850-321d14e7ecf3" />
<img width="1430" height="765" alt="image" src="https://github.com/user-attachments/assets/b02b8835-da8d-4aed-a3b9-977a19c0b85f" />

Task 4 - Edit a catalog
You can edit the name and description for a catalog. Users see this information in an access package's details.

In the Marketing page, in the left navigation, select Overview.

On the top menu, select Edit.

Review the setting and, under Properties > Enabled, select Yes.

Screen image displaying the properties being enabled.

Select Save.

<img width="1430" height="769" alt="image" src="https://github.com/user-attachments/assets/8f22bc86-4858-4d30-90f1-56dbee6855c7" />

Task 5 - Create Access reviews for guest users
Access reviews can manage the access lifecycle.  Microsoft Entra Identity Governance provides an overview dashboard showing the status of access reviews. Select Access reviews in the Identity Governance menu.

Under the Access review menu, you can select Access reviews to configure an access review for guest users.  You will select + New access review to create your guest user access review.  The tile will open to configure the access review for guest users.

Select Teams + Groups for Select what to review.

Under Select review scope, select All Microsoft 365 groups with guest users

Under Select user scope, select Guest users only.

Select Next: Reviews.

The next tile is where you configure who reviews and approves access, how often access will be reviewed, and when access will expire.

Under Select reviewers, select Group owners as these reviewers.

Note: Guest users should not be allowed to review their own access as a good identity governance practice.
Enter a Duration (in days), default is 3, choose a Review recurrence and Start date for the review.

Select Next: Settings and configure the settings for how the review will take place and what happens when the guest user responds or does not respond. A good practice is to select Auto apply results to resource and select Remove access for If reviewers don't respond.

Select Next: Review + create, and select Create to create the new Access review

<img width="1428" height="768" alt="image" src="https://github.com/user-attachments/assets/588b6b33-736c-4310-b165-6616f8d9d67e" />
<img width="1433" height="767" alt="image" src="https://github.com/user-attachments/assets/5e8b3669-8960-46bd-ba2e-2fd9d9aaec97" />
<img width="1429" height="768" alt="image" src="https://github.com/user-attachments/assets/0930ace4-8959-4fbd-a9d9-c62104346d0c" />
<img width="1428" height="771" alt="image" src="https://github.com/user-attachments/assets/b1703bc5-b6d9-4bc5-8a1e-68a63ca11513" />
<img width="1430" height="765" alt="image" src="https://github.com/user-attachments/assets/8a83eb7a-494a-4c0d-aa35-7eb78def7236" />
<img width="1430" height="768" alt="image" src="https://github.com/user-attachments/assets/899f92c5-1b0f-470a-a37f-05ef0111b94c" />
<img width="1425" height="767" alt="image" src="https://github.com/user-attachments/assets/eb74dfb7-0dff-4a17-b43d-dbdec9046398" />

Task 6 - Delete a catalog
You can delete a catalog, but only if it does not have any access packages.

In the Marketing catalog’s Overview page, on the top menu, select Delete.

In the Delete dialog box, review the information and then select No.

Note - we are keeping the catalog for use in the next lab.

<img width="1424" height="770" alt="image" src="https://github.com/user-attachments/assets/e12c20fe-1c19-42d0-989e-d577958fe7b7" />





