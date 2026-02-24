# Manage Microsoft Entra Smart Lockout Values

## Overview
This exercise guides you through configuring smart lockout protection settings in Microsoft Entra ID. Smart lockout helps protect your organization by temporarily locking accounts after multiple failed login attempts, preventing unauthorized access through brute force attacks.

## What is Smart Lockout?
Smart lockout is a security feature that:
- Monitors failed login attempts on user accounts
- Automatically locks accounts when suspicious activity is detected
- Prevents attackers from guessing passwords through repeated attempts
- Helps protect your organization's identity security

## Exercise 1 - Manage Microsoft Entra Smart Lockout Values

### Task: Configure Smart Lockout Settings

This task will walk you through customizing Microsoft Entra smart lockout settings to match your organization's security requirements.

### Prerequisites
- Global Administrator access to your Microsoft Entra tenant
- Access to the Microsoft Entra admin center

### Step-by-Step Instructions

#### Step 1: Access the Microsoft Entra Admin Center
1. Open your web browser
2. Navigate to **https://entra.microsoft.com**
3. Sign in using a Global Administrator account for your directory
4. You will see the Microsoft Entra admin center dashboard

#### Step 2: Navigate to Authentication Methods
1. Select the **menu icon** (three horizontal lines) in the left sidebar
2. Click on **Identity** from the menu options
3. From the Identity submenu, select **Protection**
4. In the left navigation pane, click on **Authentication methods**
5. You should now see the Authentication methods configuration page

#### Step 3: Access Password Protection Settings
1. On the Authentication methods page, locate and click on **Password protection**
2. This opens the password protection settings where you can configure smart lockout parameters

#### Step 4: Configure Smart Lockout Parameters
You will see several settings to configure:

**Lockout Duration (in seconds):**
- This controls how long an account remains locked after the threshold is reached
- Set the value to **120 seconds** (2 minutes)
- This prevents immediate re-attack while allowing legitimate users to try again soon

**Mode:**
- Next to the Mode option, select **Enforced**
- This activates the smart lockout feature for all users in your organization
- When enforced, accounts will be automatically locked when suspicious activity is detected

#### Step 5: Save Your Changes
1. Click the **Save** button to apply your configuration
2. You should see a confirmation message indicating the settings have been saved successfully
3. Your smart lockout settings are now active

### What Happens When Smart Lockout is Triggered

When a user exceeds the failed login attempts threshold, they will receive the following message:

> **"Your account is temporarily locked to prevent unauthorized use. Try again later, and if you still have trouble, contact your admin."**

This message informs users that:
- Their account is temporarily restricted due to security measures
- They should wait before attempting to log in again
- They can contact their administrator if the issue persists

### Testing Smart Lockout (Optional)

To verify that smart lockout is working correctly in your environment:

1. **Select a Test User**: Choose a user account in your Microsoft Entra tenant to test with
2. **Open a Private Browser Session**: Open an incognito or private browsing window
3. **Navigate to the Login Page**: Go to the Microsoft Entra sign-in page
4. **Enter Incorrect Passwords**: Deliberately enter an incorrect password multiple times
5. **Observe the Lockout**: Continue entering wrong passwords until you receive the lockout message
6. **Verify the Lockout**: You should see the message: "Your account is temporarily locked to prevent unauthorized use"
7. **Wait for Unlock**: After 120 seconds (2 minutes), the account will automatically unlock

### Reference Screenshots

Below are reference images showing the key configuration screens:

**Microsoft Entra Password Protection Configuration Page:**
<img width="1433" height="771" alt="Password Protection Settings Page" src="https://github.com/user-attachments/assets/81101107-50d0-4ef1-9d2c-9295fabfbada" />

**Smart Lockout Triggered - Lockout Message Display:**
<img width="1431" height="766" alt="Smart Lockout Message" src="https://github.com/user-attachments/assets/3d99e466-5f9a-4d87-b983-8f23b8fd168a" />

**Lockout Message Details:**
<img width="428" height="449" alt="Lockout Message Details" src="https://github.com/user-attachments/assets/17aff4fa-b6a6-4a7b-8f09-32bb789a15e1" />

### Key Takeaways
- Smart lockout provides essential protection against brute force attacks
- A 120-second lockout duration balances security and user experience
- Enforced mode ensures all users benefit from this protection
- Regular testing helps confirm that security measures are working as expected
- Always communicate these security measures to end users