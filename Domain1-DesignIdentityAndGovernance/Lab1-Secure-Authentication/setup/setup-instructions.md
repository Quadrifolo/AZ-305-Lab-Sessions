# Setup Instructions for Secure Authentication Lab

## Objective
This document outlines the steps to prepare your environment for the **Secure Authentication with Azure AD** lab.

---

## Prerequisites
Ensure the following prerequisites are met before proceeding:
- **Azure Subscription**: You must have an active Azure subscription.
- **Administrator Access**: Global Administrator permissions for your Azure AD tenant.
- **Azure CLI Installed**: Download and install [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli).
- **Test User Account**: A test user in Azure AD with no previous MFA or Conditional Access policies applied.

---

## Steps

### Step 1: Log In to Azure CLI
1. Open a terminal or command prompt.
2. Log in to your Azure account using the Azure CLI:
   ```bash
   az login
   ```
   This will open a browser window for authentication. Follow the prompts to sign in.

### Step 2: Create a Test User
1. Run the following command to create a test user:
   ```bash
   az ad user create \
     --display-name "Test User" \
     --user-principal-name testuser@yourtenant.onmicrosoft.com \
     --password P@ssword1234
   ```
   Replace `yourtenant.onmicrosoft.com` with your Azure AD tenant domain.

### Step 3: Assign a License to the User
1. Assign a Microsoft 365 license to the test user to enable Conditional Access testing:
   ```bash
   az ad user license assign \
     --user-principal-name testuser@yourtenant.onmicrosoft.com \
     --sku-id ENTER_SKU_ID
   ```
   Replace `ENTER_SKU_ID` with the SKU ID of your license. Find available SKUs using:
   ```bash
   az ad signed-in-user license list
   ```

### Step 4: Verify Configuration
1. Log in to the Azure Portal.
2. Navigate to **Azure Active Directory** > **Users** and verify the test user exists and is licensed.

---

## Cleanup
If you want to clean up the environment after the lab:
1. Delete the test user:
   ```bash
   az ad user delete --id testuser@yourtenant.onmicrosoft.com
   ```
2. Remove any resources or configurations made during the lab.

---

## Troubleshooting
- Ensure you are using the correct tenant domain for the user principal name.
- Verify your Azure CLI is up to date using `az --version`.

---

For further assistance, consult the [Azure CLI documentation](https://learn.microsoft.com/en-us/cli/azure/).
