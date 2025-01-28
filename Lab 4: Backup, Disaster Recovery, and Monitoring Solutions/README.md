# Lab 4: Backup, Disaster Recovery, and Monitoring Solutions

## Overview

This lab focuses on designing and implementing comprehensive backup, disaster recovery, and monitoring solutions using Azure services. These steps align with best practices for business continuity and system performance monitoring.

### Lab Objectives
Configure Azure Backup to protect virtual machines and other resources.
Enable Azure Site Recovery (ASR) for disaster recovery to a secondary region.
Set up Azure Monitor to track resource performance and generate alerts.

### Prerequisites
An active Azure subscription.
Contributor or Owner role on the resource group.

### Installed tools:
Azure CLI or PowerShell.
Azure Resource Manager (ARM) templates (optional for advanced configuration).
At least one virtual machine deployed in Azure.

## Lab Steps

### 1. Enable Azure Backup

Steps:

-  Navigate to the Azure Portal > Recovery Services Vault > + New.

-  Create a new vault with:
   Name: Lab4RecoveryVault
   Region: Same as your VM.
   Resource Group: Existing or new.

-  Configure backup for an existing VM:
   Go to the Recovery Services Vault > Backup.
   Choose Azure Virtual Machine as the workload.  
   Select the VM to back up and set a daily backup policy.

### 2. Configure Disaster Recovery with Azure Site Recovery

Steps:

- In the Azure Portal, navigate to your VM > Operations > Disaster recovery.

- Set the Target region for replication.

- Enable replication and monitor the health status of ASR.

- Perform a test failover to ensure the replicated VM works in the secondary region.

### 3. Set Up Monitoring with Azure Monitor

Steps:

- In the Azure Portal, go to Monitor > Metrics.

- Create a new Log Analytics workspace.

- Add metrics for:
  CPU Usage
  Disk I/O
  Network performance.
  Create an alert rule:
  Go to Alerts > + New alert rule.
  Set the signal as CPU Percentage > 80%.
  Configure an action group to send email notifications.

- Clean-Up
  Delete the backup and ASR configurations to avoid charges.
  Remove the monitoring alert rules and Log Analytics workspace:
  bash
  Copy
  Edit

   ---

## Clean-Up

1. Remove unnecessary resources to minimize costs:
   ```bash
   az monitor log-analytics workspace delete --resource-group <ResourceGroup> --workspace-name <WorkspaceName>
   ```

   ---

  

### Resources
- [Azure Backup Documentation](https://learn.microsoft.com/en-us/azure/backup/)
- [Azure Site Recovery Documentation](https://learn.microsoft.com/en-us/azure/site-recovery/)
- [Azure Monitor Documentation](https://learn.microsoft.com/en-us/azure/azure-monitor/)

### Notes
This lab demonstrates how to implement data protection and monitoring strategies to ensure business continuity and proactive performance management.
