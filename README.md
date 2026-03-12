# Retail-Sales-ETL-Pipeline-Databricks-PySpark-

## Overview
This project implements an end-to-end **Retail Sales Data Engineering Pipeline** using the **Medallion Architecture (Source → Bronze → Silver → Gold)**.  
The pipeline processes raw retail sales data, performs data transformations, manages historical records using **Slowly Changing Dimension Type 2 (SCD2)**, and builds a **Star Schema data model** for analytical reporting.

The project demonstrates key **data engineering concepts such as ETL pipelines, incremental data loading, dimensional modeling, and data transformation using PySpark and Spark SQL in Databricks**.

---

## Architecture

The project follows the **Medallion Architecture** approach:

Source → Bronze → Silver → Gold

<img width="1519" height="598" alt="image" src="https://github.com/user-attachments/assets/9dcbf227-a4d1-430b-b578-4126c89b3afa" />




### Source Layer
- Raw CSV retail sales dataset.
- Acts as the initial data ingestion point.
- Incremental load approach implemented to process only new data.

### Bronze Layer
- Stores raw ingested data.
- Data is stored in **Delta format**.
- Includes metadata columns such as ingestion timestamp.

### Silver Layer
- Performs data cleaning and transformations.
- Implements **SCD Type 2 logic** to maintain historical data changes.
- Handles schema consistency and transformation logic.

### Gold Layer
- Implements a **Star Schema** data model.
- Creates dimensional tables:
  - `DimCustomers`
  - `DimProducts`
- Creates fact table:
  - `FactRetailSales`
- Optimized for analytics and reporting.

---

## Data Model

### Dimension Tables
- **DimCustomers** – Stores customer-related attributes.
- **DimProducts** – Stores product-related attributes.

### Fact Table
- **FactRetailSales**
  - Contains retail sales transactions.
  - Linked to dimension tables through surrogate keys.

---

## Technologies Used

- **Apache Spark**
- **PySpark**
- **Spark SQL**
- **Databricks Notebooks**
- **Delta Lake**
- **Medallion Architecture**
- **Dimensional Modeling (Star Schema)**
- **Slowly Changing Dimensions (SCD Type 2)**

---

## Project Workflow

1. Raw retail sales CSV file is ingested into the Source layer.
2. Bronze layer loads raw data and stores it in Delta format.
3. Silver layer performs:
   - Data transformations
   - Data cleansing
   - SCD Type 2 implementation
4. Gold layer builds dimensional models and fact tables for analytics.

---

## Key Features

- Incremental data ingestion
- Medallion architecture implementation
- Historical data tracking using SCD Type 2
- Star schema dimensional modeling
- Scalable data processing using Spark

---

## Future Improvements

- Add **Apache Airflow orchestration** for automated pipeline scheduling.
- Implement **data quality validation checks**.
- Add **dashboard reporting using Power BI or Tableau**.
- Enable **streaming ingestion for real-time sales data**.

---

## Author

Hariharan Thangarasu  
Data Engineering Enthusiast
