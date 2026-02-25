Microsoft Entra terms of use policies provide a simple method that organizations can use to present information to end users. This presentation ensures users see relevant disclaimers for legal or compliance requirements. This article describes how to get started with terms of use (ToU) policies.

You must create and enforce a ToU policy for your organization.

Exercise 1 - Set up a Term of Use and test them
Task 1 - Add terms of use
Once you have finalized your terms of use document, use the following procedure to add it.

Sign in to https://entra.microsoft.com using a Global Administrator account.

Open select Identity Governance in the lefthand navigation menu.

In the menu, under Entitlement management, select Terms of use.

On the Terms of use page, on the top menu, select + New terms

Screen image displaying the Terms of use page with New terms highlighted

In the Name box, enter Testing terms of use.

Note - This is the terms of use that will be used in the Azure portal.

Select the Terms of use document box, browse to your finalized terms of use PDF and select it.

ToU File Provided - browse to the github repo AllFiles/Labs/Lab26 to get a sample Terms-of-User PDF document for use in this lab.

In the Display name box, enter Contoso Terms of Use.

Note - This is the title that users see when they sign in.

Select English for the language for your terms of use document.

Note - The language option allows you to upload multiple terms of use, each with a different language. The version of the terms of use that an end user will see will be based on their browser preferences.

To require end users to view the terms of use prior to accepting them, set Require users to expand the terms of use to On.

To require end users to accept your terms of use on every device they are accessing from, set Require users to consent on every device to Off. Users may be required to install additional applications if this option is enabled.

Warning - Consent on every device will require users to register each device with Microsoft Entra ID prior to getting access. It is a good practice to require this setting to On; however for the purpose of a cleaner lab, we are using Off.

If you want to expire terms of use consents on a schedule, set Expire consents to On. When set to On, two additional schedule settings are displayed.

Expire consents settings to set start date, frequency, and duration

Use the Expire starting on and Frequency settings to specify the schedule for terms of use expirations. The following table shows the result for a couple of example settings:

Expire starting on	Frequency	Result
Today's date	Monthly	Starting today, users must accept the terms of use and then reaccept every month.
Date in the future	Monthly	Starting today, users must accept the terms of use. When the future date occurs, consents will expire and then users must reaccept every month.
For example, if you set the expire starting on date to Jan 1 and frequency to Monthly, here is how expirations might occur for two users:

User	First accept date	First expire date	Second expire date	Third expire date
Alice	Jan 1	Feb 1	Mar 1	Apr 1
Bob	Jan 15	Feb 1	Mar 1	Apr 1
Use the Duration before re-acceptance requires (days) setting to specify the number of days before the user must reaccept the terms of use. This allows users to follow their own schedule. For example, if you set the duration to 30 days, here is how expirations might occur for two users:

User	First accept date	First expire date	Second expire date	Third expire date
Alice	Jan 1	Jan 31	Mar 2	Apr 1
Bob	Jan 15	Feb 14	Mar 16	Apr 15
Note - It is possible to use the Expire consents and Duration before re-acceptance requires (days) settings together, but typically you use one or the other.

Under Conditional Access, select Custom policy.

Possible choices and when to use them:
Template	Description
Access to cloud apps for all guests	A Conditional Access policy will be created for all guests and all cloud apps. This policy impacts the Azure portal. Once this is created, you might be required to sign-out and sign-in.
Access to cloud apps for all users	A Conditional Access policy will be created for all users and all cloud apps. This policy impacts the Azure portal. Once this is created, you will be required to sign-out and sign-in.
Custom policy	Select the users, groups, and apps that this terms of use will be applied to.
Create Conditional Access policy later	This terms of use will appear in the grant control list when creating a Conditional Access policy.
IMPORTANT - Conditional Access policy controls (including terms of use) do not support enforcement on service accounts. We recommend excluding all service accounts from the Conditional Access policy. Custom Conditional Access policies enable granular terms of use, down to a specific cloud application or group of users. For more information, see https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/require-tou.

When complete, select Create.

Screen image displaying the New terms of use page with configured options highlighted


