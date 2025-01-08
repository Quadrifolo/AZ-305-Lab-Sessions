# AZ-305 Lab Sessions

Welcome to the AZ-305 Lab Sessions repository! This repository contains hands-on labs designed to deepen your understanding of Azure solutions architecting, aligned with the **Microsoft AZ-305: Designing Microsoft Azure Infrastructure Solutions** certification domains.

---

## **Repository Structure**

The repository is organized into the following domains:

1. **Design Identity, Governance, and Monitoring Solutions**
2. **Design Data Storage Solutions**
3. **Design Business Continuity Solutions**
4. **Design Infrastructure Solutions**

Each domain contains a set of labs with step-by-step instructions, code snippets, and screenshots.

---

## **Lab Template**

Each lab includes the following sections:

1. **Lab Title**: A descriptive name for the lab.
2. **Objective**: The skills and knowledge you’ll gain.
3. **Prerequisites**: Tools, permissions, or resources required.
4. **Steps**: Detailed, step-by-step instructions.
5. **Validation**: How to verify your work.
6. **Cleanup**: Instructions for removing resources to avoid unnecessary costs.

---

## **Sample Lab: Implementing Azure AD Conditional Access**

### **Objective**
Learn how to create and test a Conditional Access policy in Azure AD to secure access to an application.

### **Prerequisites**
- An active Azure subscription.
- Azure AD Premium P2 license.
- A user account with Global Administrator or Security Administrator role.

### **Steps**

#### 1. **Access Azure AD**
- Navigate to the [Azure Portal](https://portal.azure.com/).
- In the left-hand menu, select **Azure Active Directory**.

#### 2. **Create a Conditional Access Policy**
- In Azure AD, go to **Security** > **Conditional Access**.
- Click **+ New policy** and give it a name (e.g., “Secure Access Policy”).
- Assign the policy to a group or user.

#### 3. **Configure Conditions**
- Under **Assignments**, configure the following:
  - **Users**: Select a test user or group.
  - **Cloud Apps**: Choose an app (e.g., Microsoft Teams).
  - **Conditions**: Enable specific conditions like device platform or location.

#### 4. **Enable Access Controls**
- Under **Access controls**, select **Grant** and require MFA.
- Click **Enable policy** and save the configuration.

#### 5. **Test the Policy**
- Sign in as the test user.
- Verify that MFA is required as per the policy.

#### 6. **Cleanup**
- Disable or delete the Conditional Access policy to avoid disruption.

### **Validation**
- Confirm that access is restricted based on the configured conditions.
- Check Azure AD Sign-In Logs to review authentication activity.

---

## **Contributing**

If you’d like to contribute to this repository, please follow these steps:

1. Fork the repository.
2. Create a feature branch.
3. Add your changes.
4. Submit a pull request.

---

## **Resources**

- [Microsoft Learn: AZ-305](https://learn.microsoft.com/en-us/certifications/azure-solutions-architect/)
- [Azure Documentation](https://learn.microsoft.com/en-us/azure/)
- [GitHub Markdown Guide](https://guides.github.com/features/mastering-markdown/)

---

Happy learning!

.
