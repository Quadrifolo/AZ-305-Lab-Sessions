
# Lab 2: Design Data Storage Solutions

## Overview

This lab focuses on designing and implementing data storage solutions that align with the requirements of the AZ-305 certification. You'll explore various storage options, their use cases, and how to configure them to meet business needs in terms of scalability, security, performance, and cost optimization.

---

## Lab Objectives

1. Understand Azure Storage options and their use cases:
   - Blob Storage
   - Azure Files
   - Azure Disks
   - Table and Queue Storage
2. Implement scalable and secure storage solutions using Azure Blob Storage.
3. Configure lifecycle management and access policies for data optimization.
4. Enable geo-redundancy for business continuity and disaster recovery (BCDR).
5. Monitor storage usage and costs.

---

## Prerequisites

- An active Azure subscription.
- Basic understanding of Azure Resource Manager (ARM).
- Installed tools:
  - Azure CLI or PowerShell
  - Azure Storage Explorer (optional for GUI-based management).
- Contributor role access to the resource group.

---

## Lab Outline

### 1. Create an Azure Storage Account

1. Log in to the Azure Portal.
2. Navigate to **Storage accounts** > **+ Create**.
3. Configure the following:
   - **Subscription**: Select your active subscription.
   - **Resource Group**: Use an existing group or create a new one.
   - **Storage account name**: Enter a unique name (e.g., `mystoragesolution`).
   - **Region**: Choose a region close to your users.
   - **Performance**: Standard or Premium.
   - **Redundancy**: Select Geo-Redundant Storage (GRS).
4. Review and create the storage account.

### 2. Set Up Blob Storage

#### Steps:

1. In the storage account, go to **Containers** > **+ Container**.
2. Enter a name (e.g., `data-archive`) and set the **Public access level** to Private.
3. Upload sample data to the container using Azure CLI:
   ```bash
   az storage blob upload      --account-name a4eademoquad      --container-name data-archive      --name samplefile.txt      --file /Users/quadrionigbanjo/documents/sampletext.txt
   ```

### 3. Configure Access Policies

#### Steps:

1. In the **Containers** blade, select your container and navigate to **Access Control (IAM)**.
2. Add a role assignment to give specific users or groups access.
3. Generate a Shared Access Signature (SAS) token for limited-time access:
   ```bash
   az storage container generate-sas      --account-name a4eademoquad      --name data-archive      --permissions r      --expiry 2025-12-31T23:59:00Z      --https-only
   ```
4. Use the generated SAS URL to access the container data.

### 4. Implement Lifecycle Management

#### Steps:

1. Navigate to the storage account > **Data management** > **Lifecycle Management**.
2. Add a new rule to transition blobs older than 30 days to Cool storage and delete blobs older than 180 days.
3. Save the policy.

### 5. Enable Geo-Redundancy

#### Steps:

1. In the storage account settings, verify the **Redundancy** setting is set to GRS or RA-GRS.
2. Test failover:
   - Navigate to **Geo-replication**.
   - Initiate a failover and observe the data access from the secondary region.

### 6. Monitor and Optimize Storage Costs

#### Steps:

1. Go to **Metrics** and set up charts for monitoring:
   - Capacity
   - Transactions
2. Use **Cost Management** to analyze storage costs and optimize usage.

---

## Clean-Up

1. Delete the uploaded blobs or containers to save costs.
2. Remove the storage account and associated resources if no longer needed:
   ```bash
   az group delete --name <ResourceGroupName>
   ```

---

## Resources

- [Azure Storage Documentation](https://learn.microsoft.com/en-us/azure/storage/)
- [AZ-305 Learning Path](https://learn.microsoft.com/en-us/certifications/exams/az-305/)

---

## Notes

This lab serves as a practical exercise for understanding the design and implementation of Azure storage solutions. Expand on the lab by exploring additional features such as Azure Files, AD authentication, and hybrid storage options.
