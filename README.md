# Incremental Data Load using Azure Synapse

## 🚀 Overview
This project demonstrates a **step-by-step implementation of Incremental Data Load** using **Azure Synapse Analytics**. Instead of reloading the entire dataset, we use a **watermarking strategy** to load only new records from **Azure SQL Database** to **Azure Data Lake Storage (ADLS)**.

## 📌 Use Case
- **Source**: Azure SQL Database  
- **Target**: Azure Data Lake Storage (ADLS)  
- **Goal**: Implement an **efficient ETL process** by fetching only incremental changes using a **watermarking strategy**.  

## ⚙️ Step-by-Step Implementation
1. **Lookup Activity (1)** – Fetch metadata from the watermark table.  
2. **Foreach Activity** – Iterate through the watermark table to process each table.  
3. **Lookup Activity (2)** – Retrieve the **max value (LPV)** from the source table based on input from Foreach.  
4. **If Condition Activity** – Check for new records by comparing LPV values (avoiding empty file creation).  
5. **Copy Activity** – Load only the **new** data from **Azure SQL DB** to **ADLS**.  
6. **Stored Procedure Activity** – Update the **LPV** for future incremental runs.  

## 🚀 Why Use Incremental Data Load?
✅ **Faster Data Processing** – Avoids reloading entire datasets.  
✅ **Cost-Effective** – Saves compute and storage resources.  
✅ **Optimized Performance** – Ensures up-to-date data without redundancy.  

## 🏗️ Technologies Used
- **Azure Synapse Analytics**  
- **Azure Data Lake Storage (ADLS)**  
- **Azure SQL Database**  
- **T-SQL (Stored Procedures for LPV Updates)**  
