# 🚗 Car Sales Data Pipeline (Azure Fabric)

A fully managed end-to-end **Fabric data pipeline** built using **Microsoft Fabric data factory**, **Azure SQL**, **Azure Databricks**, and **Azure Delta Lake** architecture to model a star-schema-based data warehouse with **slowly changing dimensions**.

---

## 🏗️ Project Overview

This project demonstrates a modern data engineering approach using Azure-native tools to process car sales data. The pipeline moves data from source systems to curated analytical layers using Medallion Architecture (Bronze → Silver → Gold).

---

## 🔧 Tools & Technologies Used

- **Microsoft Fabric (Data Factory)**
- **Azure SQL Database**
- **Azure Delta Lake**
- **Azure Databricks (Unity Catalog)**
- **PySpark**
- **Delta Live Tables**
- **Slowly Changing Dimensions (SCD Type 1)**
- **Star Schema Modelling**

---

## ⚙️ Pipeline Architecture

### 1. **Bronze Layer – Raw Ingestion**
- Data is **pulled from Azure SQL Database** into **Azure Delta Lake (Bronze)** using Microsoft Fabric.
- **Incremental loading** logic is applied to handle new and updated records.

### 2. **Silver Layer – Cleansed & Transformed**
- Data from the Bronze layer is processed in **Azure Databricks**.
- **Unity Catalog** is used to manage schemas and access control.
- Data is transformed using business logic and stored in the **Silver schema**.

### 3. **Gold Layer – Dimensional Modeling**
- Created **dimension tables** and **fact tables** from transformed Silver data.
- Applied **SCD Type 1** logic to track changes over time in both dimensions and fact tables.
- Designed a **Star Schema** with proper relationships for efficient analytics and reporting.

---

## ⭐ Key Features

- ⏱️ Incremental Data Loads
- 🛠️ SCD Type 1 Implementation
- 🧱 Medallion Architecture (Bronze/Silver/Gold)
- 🔒 Unity Catalog for Governance
- 💫 Star Schema Dimensional Model
- 🧩 Fully Managed via Microsoft Fabric

---

## 📂 Folder Structure

```bash
car_sales_data_pipeline/
│
├── Fabric pipeline /             # Notebooks or pipelines for raw data load
├── silver_transformation/       # Cleansing and transformation logic
├── gold_modelling/               # Dimensional and fact table creation
├── notebooks/                    # Databricks notebooks used in pipeline
├── data/                    # raw data used for pipeline
└── README.md                     # Project documentation
