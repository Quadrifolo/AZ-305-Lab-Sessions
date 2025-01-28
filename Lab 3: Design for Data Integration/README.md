# Lab 3: Design for Data Integration

## Overview

Learn to design and implement data integration solutions that combine and transform data from various sources using Azure tools like **Azure Data Factory (ADF)** and **Azure Synapse Analytics**. This lab will cover key integration tasks, including extracting, transforming, and loading (ETL/ELT) operations.

---

## Lab Objectives

1. Understand Azure Data Factory (ADF) and its key components:
   - Linked Services
   - Datasets
   - Pipelines
2. Create and run a data pipeline to:
   - Ingest data from a blob storage container.
   - Transform the data using mapping data flows.
   - Load the processed data into a SQL database.
3. Use triggers to automate the pipeline execution.
4. Monitor and troubleshoot data integration workflows.

---

## Prerequisites

- An active Azure subscription.
- A storage account with sample data (from Lab 2).
- A pre-configured Azure SQL Database.
- Installed tools:
  - Azure CLI or PowerShell
  - Azure Storage Explorer (optional).

---

## Lab Outline

### 1. Create an Azure Data Factory

#### Steps:

1. Navigate to the Azure Portal and search for **Data Factories**.
2. Click **+ Create** and configure the following:
   - **Subscription**: Choose your active subscription.
   - **Resource Group**: Select the group from Lab 2 or create a new one.
   - **Region**: Pick the region nearest to you.
   - **Name**: Enter a unique name (e.g., `MyDataFactory`).
3. Review and create the Data Factory.

---

### 2. Set Up Data Integration

#### 2.1 Create Linked Services

1. In the ADF UI, configure linked services for:
   - **Azure Blob Storage**: Link to the storage account created in Lab 2.
   - **Azure SQL Database**: Link to your SQL Database.
2. Test connections to ensure proper setup.

#### 2.2 Create Datasets

1. Create a **Blob Dataset** pointing to a CSV file in your blob storage.
2. Create a **SQL Dataset** to write transformed data to your SQL database.

#### 2.3 Design a Pipeline

1. Add activities to the pipeline:
   - Use **Copy Data** to transfer raw data from Blob to SQL.
   - Apply **Mapping Data Flow** to transform the data (e.g., filter or aggregate records).
2. Validate and debug the pipeline.

---

### 3. Automate Pipeline Execution

#### Steps:

1. Add a **Trigger** to the pipeline:
   - Use a scheduled trigger to run the pipeline daily.
2. Test the trigger and monitor its execution.

---

### 4. Monitor and Troubleshoot

#### Steps:

1. Navigate to the **Monitor** tab in ADF.
2. Check the pipeline run status and view activity logs for errors.

---

## Clean-Up

1. Remove unnecessary resources to minimize costs:
   ```bash
   az group delete --name <ResourceGroupName>
   ```

---

## Resources

- [Azure Data Factory Documentation](https://learn.microsoft.com/en-us/azure/data-factory/)
- [AZ-305 Learning Path](https://learn.microsoft.com/en-us/certifications/exams/az-305/)

---

## Notes

This lab provides hands-on experience with data integration in Azure. You can expand on the lab by exploring additional features like parameterized pipelines, integration runtime setups, and hybrid data integration scenarios.

