# 🚀 Azure Data Factory - End-to-End Data Pipeline Project

- This project showcases an **End-to-End Data Engineering Pipeline** built on **Azure Data Factory**, designed to move, transform, and serve data using the **Medallion Architecture (Bronze, Silver, Gold)**.
- It integrates various data sources including **On-Prem files**, **REST APIs**, and **Azure SQL Database**, and processes them into structured, analytics-ready layers.

---

## 📌 Key Features

- ⛓ Ingested data from **3 sources**: On-Prem CSV, REST API (GitHub), and Azure SQL DB
- 🔁 Built **dynamic pipelines** using **ForEach**, expressions, and parameters
- 📥 Implemented **Incremental Load** from SQL DB using a **JSON-based watermark file**
- 🧱 Followed **Medallion Architecture** (Bronze, Silver, Gold) for modular data handling
- 🧩 Performed transformations using **Mapping Data Flows** and stored in **Parquet & Delta formats**
- 📊 Created **Delta tables in Databricks** for querying and visualizing the Gold Layer
- 🛠 Managed resources using Azure Portal including Linked Services, Datasets, and Triggers

--- 

## 💻 Technologies Used

- Azure Data Factory
- Azure Data Lake Gen2
- Azure SQL Database
- REST API (GitHub)
- Mapping Data Flows
- Databricks (Delta Tables)
- PySpark 
- JSON, CSV, Parquet, Delta

---

# 🗂 Architecture Overview
🔹 This diagram shows the full data flow from multiple sources to the Gold layer using ADF and Databricks.

<img width="1008" height="557" alt="Flow (1)" src="https://github.com/user-attachments/assets/220affb8-402a-43ef-be5c-a01fbc734e47" />

---

# 🧱 Resource Group Setup
🔹 Resource group where all Azure services like Data Factory, SQL DB, and Data Lake were hosted.

<img width="1920" height="842" alt="image" src="https://github.com/user-attachments/assets/7b2d2f9e-a565-4452-88e2-6c12984ae496" />

---

#  🏗 Medallion Architecture
🔹 Bronze, Silver, and Gold layers help in modularizing and cleaning the data at each stage.

<img width="1919" height="846" alt="image" src="https://github.com/user-attachments/assets/02e55963-b81a-4029-bf8b-585283c5eb6d" />

---

# 📥 Bronze Layer - Raw Ingestion
🔹 Raw files from On-Prem, API, and SQL sources are stored in the Bronze layer without transformations.

<img width="1920" height="838" alt="image" src="https://github.com/user-attachments/assets/398e5231-e691-4907-9cdd-30bb0009e648" />

---


# 🌐 API Ingestion (GitHub JSON)
🔹 JSON data pulled from a public GitHub REST API using HTTP + Copy activity and stored in the lake.

<img width="1920" height="759" alt="image" src="https://github.com/user-attachments/assets/cce2d6bb-a50e-4138-bbda-18ddd4d86f95" />

# 🏢 On-Prem CSV Ingestion
🔹 CSV files from On-Premises are loaded dynamically using ForEach and parameterized pipelines.

<img width="1920" height="743" alt="image" src="https://github.com/user-attachments/assets/e132aacc-c1ca-4e3f-8186-7d4b7fbfa04b" />


# 🧹 Silver Layer - Cleaned Data
🔹 Raw data is cleaned, formatted, and structured here using Mapping Data Flows.

<img width="1920" height="820" alt="image" src="https://github.com/user-attachments/assets/42f1019f-c446-4819-9718-b455c0e6e8cd" />


# Gold Layer - Final Data for Analytics
🔹 Fully transformed data, ready for reporting or consumption by Power BI, Databricks, etc.

<img width="1920" height="633" alt="image" src="https://github.com/user-attachments/assets/0e39706a-edd1-4460-8c4d-577164b8d0a7" />



# 🧩 Datasets & Dataflows
🔹 Datasets and data flows are reusable components that define structure and logic for transformations.

<img width="398" height="833" alt="image" src="https://github.com/user-attachments/assets/f6a626ec-d865-4592-a8f5-45aa190fe0c6" />

# 🔗 Linked Services
🔹 Secure connections created to Data Lake, SQL Server, REST API, etc. using linked services.

<img width="1917" height="1076" alt="image" src="https://github.com/user-attachments/assets/9caa6bf7-41b1-4941-9519-1eeb11a3d278" />


#  🔀 ADF - Pipelines
🔹 Overview of all ADF pipelines for each source system and processing layer.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/21e9e0e6-8f69-43de-af47-364365feae1f" />


# API Ingestion 
🔹 Pipeline to fetch API response, store in JSON format in lake, and trigger further transformations.

<img width="1920" height="845" alt="image" src="https://github.com/user-attachments/assets/aebde57b-a391-46a1-b53a-270877b05055" />

# Gold layer 
<img width="1918" height="1080" alt="image" src="https://github.com/user-attachments/assets/f02fcc76-d50b-4959-b460-1107003ce7cd" />

# OnPrem Ingestion
<img width="1909" height="890" alt="image" src="https://github.com/user-attachments/assets/29bb8147-afe2-4b5a-98a0-1776eb4017f4" />

# 🔁 Parent Pipeline (Controller)
🔹 A controller pipeline that orchestrates child pipelines for On-Prem, API, and SQL ingestion.

<img width="1920" height="871" alt="image" src="https://github.com/user-attachments/assets/cd75215b-13aa-4b29-9287-183b38473fbc" />

# Silver Layer
<img width="1920" height="893" alt="image" src="https://github.com/user-attachments/assets/08d50250-7bc1-4178-a1cb-3c9970fa5980" />

# 📦 SQL to Data Lake (Incremental Load)
🔹 Used Lookup and Set Variable to fetch `lastLoadDate` and ingest only new records from SQL.

<img width="1920" height="1007" alt="image" src="https://github.com/user-attachments/assets/bb1a10ef-424f-4c42-a512-94c9869e2daf" />

# 🔄 Data Transformation in ADF using Dataflow
🔹 Data Flow transformations applied on Silver layer to clean and enrich the data before Gold.

<img width="1920" height="926" alt="image" src="https://github.com/user-attachments/assets/c10ccce0-8ae1-4f68-8b50-454289f0d8e0" />

# 📡 Data Serving Layer
🔹 Final data is stored in Delta tables in Databricks and can be queried or visualized easily.

<img width="1920" height="797" alt="image" src="https://github.com/user-attachments/assets/81ef1585-a11c-49c3-9a95-62c76d478853" />

