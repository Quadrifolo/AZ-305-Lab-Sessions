# Lab 1: Secure Authentication with Azure AD

## Objective
The objective of this lab is to configure secure authentication in Azure Active Directory (Azure AD) by:
- Setting up Multi-Factor Authentication (MFA).
- Configuring Conditional Access policies.
- Testing user authentication.

---

## Prerequisites
Before starting this lab, ensure you have the following:
- An active Azure subscription.
- Global Administrator permissions in the Azure AD tenant.
- Azure CLI installed on your local machine.
- Basic knowledge of Azure AD and authentication concepts.

---

## Lab Steps

### Step 1: Configure Multi-Factor Authentication (MFA)
1. Log in to the [Azure Portal](https://portal.azure.com).
2. Navigate to **Azure Active Directory** > **Security** > **Multi-Factor Authentication**.
3. Click on **Additional cloud-based MFA settings**.
4. Enable MFA for a test user:
   - Go to **Users** > Select a test user.
   - Click **Require MFA**.
5. Save the settings and test the login process with MFA enabled.

### Step 2: Create a Conditional Access Policy
1. Navigate to **Azure Active Directory** > **Security** > **Conditional Access**.
2. Click **+ New Policy**.
3. Configure the policy as follows:
   - **Assignments**: Include the test user.
   - **Cloud apps or actions**: Select **Microsoft 365**.
   - **Conditions**: Add a location condition to block access from outside your country.
   - **Access controls**: Require MFA.
4. Name the policy and enable it.

### Step 3: Test Authentication
1. Use the test user credentials to sign in to a Microsoft 365 app.
2. Ensure MFA is prompted and that the Conditional Access policy blocks or grants access as configured.

---

## Cleanup
1. Disable the Conditional Access policy to prevent unintended disruptions.
2. Remove MFA requirements for the test user if no longer needed.

---

## Resources
- [Azure AD Multi-Factor Authentication Documentation](https://learn.microsoft.com/en-us/azure/active-directory/authentication/)
- [Conditional Access Policies](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/)

---

## Next Steps
After completing this lab, explore advanced Conditional Access configurations, such as requiring compliant devices or integrating with third-party identity providers.
