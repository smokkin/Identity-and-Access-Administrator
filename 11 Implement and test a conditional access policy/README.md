# Implement and Test a Conditional Access Policy

## Overview
Your organization needs to limit user access to internal applications. This guide walks you through deploying a Microsoft Entra conditional access policy to control who can access specific resources.

**Note:** For Conditional Access Policies, you can turn off Security Defaults. Remember the key training concepts. For more information on Security defaults, visit the [Microsoft documentation](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-conditions).

---

## Exercise 1: Create and Test a Conditional Access Policy

### Task 1: Confirm User Access to Sway (Before Policy)

Before creating the policy, verify that DebraB can access Microsoft Sway without restrictions.

**Steps:**

1. Open a new **InPrivate/Incognito browser window** (this ensures no cached credentials interfere with testing)

2. Navigate to `https://www.office.com`

3. When prompted to log in, enter DebraB's credentials:
   - **Username:** `DebraB@<<your lab domain>>.onmicrosoft.com`
   - **Password:** Enter the password provided for this account

4. Skip any welcome screens or introduction screens that appear

5. Navigate to the **Apps** section

6. Click on the **Sway icon** to confirm it loads successfully

7. Log out and close the browser window

**Expected Result:** Sway should load without any errors or access restrictions.

![Access Confirmation Screenshot 1](https://github.com/user-attachments/assets/e6980288-cc0a-4df3-a15d-f75f722d0896)
![Access Confirmation Screenshot 2](https://github.com/user-attachments/assets/7c44732f-b1aa-4d95-97b6-7b3a61becf88)

---

### Task 2: Create a Conditional Access Policy

Microsoft Entra conditional access allows you to specify detailed policies that control access to your resources based on specific conditions. In this task, you'll create a policy that blocks DebraB from accessing Sway.

**Steps:**

1. Navigate to `https://entra.microsoft.com` and sign in with a **Global Administrator account**

2. In the portal menu, select **Microsoft Entra ID**

3. In the left navigation menu, select **Protection** (under the Identity section)

4. On the Protection page, in the left sidebar, select **Conditional Access**

5. On the Conditional Access overview page, click the **+ Create new policy** button

6. **Enter the Policy Name:**
   - In the **Name** field, type: `Block Sway for DebraB`
   - This name helps you quickly identify the policy's purpose

7. **Configure User Assignment:**
   - Click **0 users and groups selected** (under Assignments)
   - Select the **Include** tab
   - Check the **"Select users and groups"** checkbox
   - Click **Select users and groups**
   - Search for and select **DebraB's account**
   - Click **Select** to confirm

8. **Configure Target Resources:**
   - Click **No target resource selected** (under Assignments)
   - Ensure **"Select resources"** is selected
   - Click the resource dropdown and select **None** first
   - In the search pane, search for **"Sway"**
   - Select **Sway** from the results
   - Click **Select** to confirm

9. **Configure Access Controls:**
   - Under the **Grant** section, click **0 controls selected**
   - In the Grant pane, select **Block access**
   - Click **Select**
   - **Note:** This policy is for demonstration purposes only to quickly show how conditional access works

10. **Enable the Policy:**
    - Under **Enable policy**, select **On**
    - Click **Create** to finalize the policy

**Expected Result:** The policy is now created and active.

![Policy Creation Screenshot 1](https://github.com/user-attachments/assets/73f47b83-5564-48b5-9774-80a6a2753d39)
![Policy Creation Screenshot 2](https://github.com/user-attachments/assets/560840a6-4f8e-4082-a24a-cf104b4dc251)
![Policy Creation Screenshot 3](https://github.com/user-attachments/assets/89db6e03-1f11-4fba-95f4-508748ee977e)
![Policy Creation Screenshot 4](https://github.com/user-attachments/assets/070b1961-f514-4bcd-b461-444108da69ab)
![Policy Creation Screenshot 5](https://github.com/user-attachments/assets/e538257a-0ddb-47c5-8af6-63226599954a)
![Policy Creation Screenshot 6](https://github.com/user-attachments/assets/ab9022c7-0eb8-48e0-a79a-75ff33b5a5a3)

---

### Task 3: Test the Conditional Access Policy

Now test the policy to confirm it's working as expected and blocking DebraB from accessing Sway.

**Steps:**

1. Open a new **InPrivate/Incognito browser tab** (to avoid cached credentials)

2. Navigate to `https://sway.cloud.microsoft`

3. When prompted to log in, enter DebraB's credentials:
   - **Username:** `DebraB@<<your lab domain>>.onmicrosoft.com`
   - **Password:** Enter the password provided for this account

4. **Verify the Block:** You should see a message indicating that access to Microsoft Sway is denied due to the conditional access policy

5. **If Access Is Not Blocked:**
   - If you're already logged in to Sway, you may need to manually log out first
   - This happens because your credentials/session were cached
   - Close the tab, wait 1 minute for the cache to clear, and retry
   - Log out, then log in again—access should now be denied

6. After confirming the policy is working, close the browser tab

7. Return to the Conditional Access page in the Microsoft Entra admin center

8. **Disable the Policy (for cleanup):**
   - Select the **"Block Sway for DebraB"** policy
   - Under **Enable policy**, select **Off**
   - Click **Save**

**Expected Result:** DebraB is blocked from accessing Sway with a clear denial message. After disabling the policy, access is restored.

![Blocked Access Screenshot 1](https://github.com/user-attachments/assets/f63ec82f-2528-430c-ad57-95ba421b35b7)
![Blocked Access Screenshot 2](https://github.com/user-attachments/assets/63e2fcab-7007-46d4-9404-31af1458f1c1)
![Blocked Access Screenshot 3](https://github.com/user-attachments/assets/843a739b-deb6-4fec-b275-7c8f9cfbe788)
![Disabled Policy Screenshot 1](https://github.com/user-attachments/assets/9e6345f6-55c4-4dcb-abcd-e061e45817c5)
![Disabled Policy Screenshot 2](https://github.com/user-attachments/assets/3c4b2346-15c8-4de9-84c9-187d294a5623)
![Disabled Policy Screenshot 3](https://github.com/user-attachments/assets/f4b7c54a-4723-4486-a711-d35973e1dddb)
![Disabled Policy Screenshot 4](https://github.com/user-attachments/assets/64f04021-8b40-496f-ae9c-31b23e9f063a)

---

## Exercise 2: Test Conditional Access Policies with "What If" Analysis

The "What If" tool allows you to evaluate how conditional access policies will affect users **before** enabling them in your production environment. This is a safer way to test policy effectiveness.

### Task: Use "What If" to Preview Policy Impact

**Steps:**

1. Navigate to `https://entra.microsoft.com` and sign in with a **Global Administrator account**

2. In the portal menu, select **Microsoft Entra ID**

3. In the left navigation menu, select **Protection** (under Identity)

4. On the Protection page, select **Conditional Access** from the left sidebar

5. In the Conditional Access navigation pane, select **Policies**

6. Click the **What If** button/tab

7. **Select a User to Test:**
   - Click **"No user or service principal selected"** (under User or Workload identity)
   - Search for and select **DebraB** as the test user

8. **Select a Cloud Application:**
   - Click **"Sway"** (or your target cloud app) under "Cloud apps, actions, or authentication context"
   - If Sway isn't visible, click the dropdown and search for it

9. **Run the What If Analysis:**
   - Click the **What If** button
   - A report appears at the bottom showing:
     - **Policies that will apply:** Any policies that would block or require action
     - **Policies that will not apply:** Policies that don't match this user/app combination

10. **Review the Results:**
    - Examine which policies would take effect for DebraB accessing Sway
    - This helps you validate policy logic before enabling it in production

**Benefits of Using "What If":**
- Test policies without impacting actual users
- Identify unintended policy interactions
- Verify policy effectiveness before deployment
- Ensure your policies work as intended

![What If Analysis Screenshot 1](https://github.com/user-attachments/assets/95b9d44a-ed77-46d2-acce-ffc8e2ff022a)
![What If Analysis Screenshot 2](https://github.com/user-attachments/assets/0ffe82bf-63c8-4255-8ee1-53641a2dbb02)
![What If Analysis Screenshot 3](https://github.com/user-attachments/assets/39465370-16b6-45c3-ba9d-2339a026184b)
![What If Analysis Screenshot 4](https://github.com/user-attachments/assets/775cfa5b-dda1-4c28-bd3a-7e245352481d)
![What If Analysis Screenshot 5](https://github.com/user-attachments/assets/f0dbef36-00b5-44d3-91e9-7a64f780e52f)

---

## Exercise 3: Configure Sign-In Frequency Controls

Sign-in frequency controls allow you to require users to re-authenticate at specified intervals. This enhances security by limiting the lifespan of user sessions. In this exercise, you'll create a policy that requires Grady Archie to sign in again every 30 days when accessing Office 365.

### Task: Create a Sign-In Frequency Conditional Access Policy

**Steps:**

1. Navigate to `https://entra.microsoft.com` and sign in with a **Global Administrator account**

2. In the portal menu, select **Microsoft Entra ID**

3. In the left navigation menu, select **Protection** (under Identity)

4. On the Protection page, select **Conditional Access** from the left sidebar

5. On the top menu, click **Policies**

6. Click the **+ New policy** dropdown button and select **Create a new policy**

7. **Enter the Policy Name:**
   - In the **Name** field, type: `Sign in frequency`

8. **Configure User Assignment:**
   - Click **0 users and groups selected** (under Assignments)
   - Select the **Include** tab
   - Check the **"Select users and groups"** checkbox
   - Click **Select users and groups**
   - Search for and select your **Grady Archie account**
   - Click **Select** to confirm

9. **Configure Target Resources:**
   - Click **No target resources selected** (under Assignments)
   - Ensure **"Select resources"** is selected
   - Click the dropdown and select **None** first
   - In the search pane, search for **"Office 365"**
   - Select **Office 365** from the results
   - Click **Select** to confirm

10. **Configure Session Controls:**
    - Under **Access controls**, click the **Session** section (or find the Session tab)
    - Select **Sign-in frequency** from the available session controls
    - In the **Value** field, enter: `30`
    - Click the **Units** dropdown menu
    - Select **Days**
    - Click **Select** to confirm

11. **Set Policy Mode to Report-Only:**
    - Under **Enable policy**, select **Report-only** (instead of "On")
    - This allows the policy to be evaluated and logged without actually enforcing restrictions
    - Click **Create** to finalize the policy

**What is Report-Only Mode?**

Report-only mode is a safe way to evaluate conditional access policies before fully enabling them:
- Policies are evaluated during every sign-in
- Policies are **NOT enforced** (users aren't blocked)
- Results are logged for review in:
  - The **Conditional Access** tab of sign-in logs
  - The **Report-only** tab of sign-in logs
- If you have an Azure Monitor subscription, use the **Conditional Access insights workbook** to analyze policy impact
- You can review the impact data and adjust the policy before enabling it fully

**Expected Result:** The policy is created in report-only mode. Grady Archie's sign-in activity is now logged against this policy, and you can review the impact before enabling it fully.

![Sign-In Frequency Policy Screenshot 1](https://github.com/user-attachments/assets/277bdb0e-32a4-40ba-a328-3ca8a624a728)
![Sign-In Frequency Policy Screenshot 2](https://github.com/user-attachments/assets/982e34c1-cced-44da-a143-33bcc0ba71e6)
![Sign-In Frequency Policy Screenshot 3](https://github.com/user-attachments/assets/66c8c02a-91c5-44de-a6e4-3f97fa623845)
![Sign-In Frequency Policy Screenshot 4](https://github.com/user-attachments/assets/dac9d3ad-02e3-4d9c-a71d-f0c907f761c6)
![Sign-In Frequency Policy Screenshot 5](https://github.com/user-attachments/assets/38353d49-064e-4f1c-b4c0-d2b18380402f)
![Sign-In Frequency Policy Screenshot 6](https://github.com/user-attachments/assets/4432b16b-d0ab-4edc-b035-355e17b030d1)
![Sign-In Frequency Policy Screenshot 7](https://github.com/user-attachments/assets/7426932c-da8b-4b54-9615-ef3cf4f97b81)

---

## Summary

You've now completed three important conditional access exercises:

1. **Created a Block Policy** – Demonstrated how to block specific users from accessing specific resources
2. **Tested with "What If"** – Learned how to safely evaluate policies before deployment
3. **Configured Session Controls** – Set up sign-in frequency requirements in report-only mode for safe evaluation

These skills are essential for managing security in your Microsoft Entra ID environment.