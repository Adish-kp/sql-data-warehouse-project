# sql-data-warehouse-project

## Project Overview
This project demonstrates the design and implementation of a **SQL-based Data Warehouse** using the **Medallion Architecture (Bronze → Silver → Gold)** approach.

The objective of this project is to:
- Ingest raw data from multiple source systems (CRM and ERP)
- Clean and transform the data
- Build a structured **Star Schema** optimized for analytics
- Enable business-ready reporting and insights

This project simulates a real-world data engineering workflow using pure SQL.

---

## 🧱 Architecture

The project follows a **three-layer Medallion Architecture**:

### 🟤 Bronze Layer – Raw Data
- Stores raw data exactly as received from source systems
- Data is loaded from CSV files into database tables
- No transformations applied
- Preserves source-level structure

### ⚪ Silver Layer – Clean & Standardized Data
- Cleans and transforms raw data
- Removes duplicates
- Standardizes formats (dates, text, null handling)
- Performs data quality validations
- Prepares integrated datasets

### 🟡 Gold Layer – Business-Ready Data (Star Schema)
- Contains analytical data models
- Structured using a **Star Schema**
- Optimized for reporting and BI tools

---

## ⭐ Data Modeling (Star Schema)

The Gold layer consists of:

### 📌 Fact Table

#### `fact_sales`
Stores measurable business events:
- order_number
- product_key (FK)
- customer_key (FK)
- order_date
- shipping_date
- due_date
- sales_amount
- quantity
- price

---

### 📌 Dimension Tables

#### `dim_customers`
Contains descriptive customer information:
- customer_key (PK)
- customer_id
- customer_number
- first_name
- last_name
- country
- marital_status
- gender
- birthdate

#### `dim_products`
Contains descriptive product details:
- product_key (PK)
- product_id
- product_number
- product_name
- category
- subcategory
- maintenance
- cost
- product_line
- start_date

---

## 🔄 ETL Process

The project implements a complete SQL-based ETL pipeline:

1. **Extract**
   - Load raw CRM and ERP data from CSV files into Bronze tables

2. **Transform**
   - Clean and standardize data in the Silver layer
   - Handle null values and inconsistencies
   - Deduplicate records
   - Generate surrogate keys

3. **Load**
   - Populate dimension tables
   - Load fact tables with foreign key relationships
   - Enforce referential integrity

All transformations are implemented using **T-SQL scripts**.

---

## 📊 Business Use Cases

This warehouse enables:

- Sales trend analysis over time
- Customer segmentation and profiling
- Product performance evaluation
- Revenue and profitability tracking
- Clean and integrated reporting data

---

## 🛠️ Technologies Used

- SQL Server / T-SQL
- Star Schema Modeling
- Medallion Architecture
- ETL Design Principles
- Data Warehousing Concepts

---

## 📁 Project Structure

```
sql-data-warehouse-project/
│
├── dataset/        # Raw CSV files (CRM & ERP)
├── scripts/        # SQL scripts (Bronze, Silver, Gold)
├── docs/           # Architecture & schema diagrams
└── README.md
```

---

## 🚀 Skills Demonstrated

- Data Warehouse Architecture
- ETL Pipeline Design
- SQL Data Transformation
- Star Schema Modeling
- Data Cleaning & Standardization
- Analytical Data Modeling

---

## 🎯 Conclusion

This project demonstrates a complete end-to-end data warehousing workflow — from raw source ingestion to business-ready analytical models. It showcases practical data engineering concepts and SQL-based implementation of a scalable warehouse architecture.
