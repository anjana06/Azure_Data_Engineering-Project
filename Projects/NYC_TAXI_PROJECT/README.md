# Azure End-to-End Data Engineering Project (ADF + ADLS + Databricks + Delta + Power BI)

## 📌 Project Overview
This project demonstrates an **end-to-end Azure Data Engineering pipeline** using the **Medallion Architecture (Bronze → Silver → Gold)**.

The pipeline ingests raw data using **Azure Data Factory**, stores it in **Azure Data Lake Storage Gen2**, performs transformations using **Azure Databricks (PySpark)**, and finally creates curated **Delta tables** for analytics and reporting in **Power BI**.

---

## 🏗️ Architecture
![Architecture](Architecture/nyc_taxi_Arch.drawio(1).png)

### ✅ Flow Summary
1. **Ingestion (ADF)**: Data is pulled dynamically from source (API/dataset) and stored in ADLS Gen2 Bronze layer.
2. **Bronze Layer (Raw)**: Stores raw data in **Parquet** format.
3. **Silver Layer (Cleaned/Transformed)**: PySpark transformations applied in Databricks, output stored in **Parquet**.
4. **Gold Layer (Serving)**: Curated dataset stored as **Delta table** for BI/reporting.
5. **Power BI**: Connected to Databricks/Delta tables for reporting.
6. **Security**: Managed Identity is used for secure access to ADLS (no hardcoded credentials).

---

## 🧰 Tech Stack
- **Azure Data Factory (ADF)** – ingestion + orchestration  
- **Azure Data Lake Storage Gen2 (ADLS Gen2)** – Bronze/Silver/Gold storage  
- **Azure Databricks** – PySpark transformations  
- **Apache Spark / PySpark** – data processing  
- **Delta Lake** – Gold layer curated Delta tables  
- **Power BI** – reporting and dashboarding  
- **Azure Managed Identity** – secure authentication and authorization  
- *(Optional)* **Azure Key Vault** – secure secrets management  
- **GitHub** – version control + documentation  

---

## 📂 Data Lake Structure (Medallion Layers)
adls-container/
│
├── bronze/
│ └── source_name/...
│
├── silver/
│ └── transformed/...
│
└── gold/
└── curated_delta_table/...
