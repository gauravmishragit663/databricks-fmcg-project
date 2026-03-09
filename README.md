# Retail Data Lakehouse ETL Pipeline (Databricks + PySpark)

## Overview
This project demonstrates an end-to-end data engineering pipeline built using Databricks, PySpark, and AWS S3 following the Medallion Architecture (Bronze, Silver, Gold).

The use case is based on an FMCG retail company where a large retailer acquires a smaller company and needs to consolidate datasets from both companies into a unified data platform for analytics.

The pipeline processes raw data, performs transformations, and generates business-ready datasets for reporting and analytics.

---

## Architecture

The project follows the **Lakehouse Medallion Architecture**.

Bronze Layer → Raw Data  
Silver Layer → Cleaned and Transformed Data  
Gold Layer → Business-ready Aggregated Data

---

## Tech Stack

- Databricks
- Apache Spark (PySpark)
- Python
- SQL
- AWS S3
- Delta Lake
- Medallion Architecture

---

## Data Pipeline Flow

### 1. Data Ingestion (Bronze Layer)

Raw CSV files are uploaded to AWS S3 and ingested into Databricks as Delta tables.

Key Features:
- Raw data storage
- Metadata tracking
- Data lineage support

---

### 2. Data Transformation (Silver Layer)

Data cleaning and transformations are performed including:

- Schema standardization
- Data type casting
- Null handling
- Derived columns creation
- Deduplication

---

### 3. Business Aggregations (Gold Layer)

Fact and dimension tables are joined to create business-ready datasets for analytics.

Example metrics generated:

- Total revenue
- Sales by product
- Sales by region
- Product performance

---

## Incremental Processing

The pipeline supports incremental data loading to process only new data instead of full dataset reloads.

Benefits:
- Reduced compute cost
- Faster processing
- Scalable architecture

---

## Orchestration

The pipeline is orchestrated using **Databricks Workflows**, executing multiple notebooks in sequence.

Pipeline Flow:

```
Data Ingestion → Dimension Processing → Fact Processing → Gold Layer Aggregation
```

---

## Project Structure

```
notebooks/
    bronze_ingestion
    silver_transformation
    dimension_processing
    fact_processing
    gold_layer

datasets/
    customers.csv
    products.csv
    sales.csv
```

---

## Key Data Engineering Concepts Demonstrated

- ETL Pipeline Development
- Lakehouse Architecture
- Medallion Architecture
- Incremental Data Processing
- Fact and Dimension Modeling
- Data Transformation using PySpark
- Delta Lake ACID transactions
- Pipeline Orchestration

---

## Business Impact

This pipeline enables the organization to:

- Consolidate data from multiple companies
- Maintain scalable and reliable data pipelines
- Generate analytics-ready datasets
- Support data-driven decision making
