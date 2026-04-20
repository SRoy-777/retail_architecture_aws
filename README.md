# Sales Data Pipeline – AWS S3 + Databricks

## Overview

This project demonstrates an end-to-end data pipeline built using AWS S3 and Databricks, designed to process sales data from raw ingestion to reporting-ready datasets.

The pipeline follows a Medallion Architecture (Bronze → Silver → Gold) and is orchestrated using Databricks Workflows.

The final output is consumed in Power BI dashboards with row-level security (RLS) implemented.

---

## Architecture

![Architecture](./architecture/architecture_diagram.png)

BC365 API → AWS S3 (Bronze) → Databricks (Silver → Gold) → SQL Views → Power BI

---

## Data Lake Structure

orient-retail-data-lake/

bronze/  
silver/  
gold/  

![S3 Structure](./screenshots/medallion_architecture.png)

---

## Pipeline Components

### Data Ingestion
- Data is ingested from BC365 (ERP) APIs into AWS S3 (Bronze layer)

### Data Transformation
- Bronze → Silver: Cleaning and schema standardization  
- Silver → Gold: Business transformations and modeling
![Transformation](./screenshots/s3_import_&_EDA.png)
![Transformation2](./screenshots/silver_to_gold_transformations.png)

### Orchestration
- Implemented using Databricks Workflows  
- Task flow:

bronze_to_silver → silver_to_gold → create_views

![Workflow](./screenshots/automated_workflow_in_action.png)

---

## Reporting Layer

- SQL Views created in Databricks  
- Connected to Power BI dashboards  
- Row-Level Security (RLS) implemented  

![Dashboard](./screenshots/dashboard.png)

![RLS](./screenshots/Dynamic_RLS_table_security.png)
![RLS_Testing](./screenshots/dynamic_rls_testing.png)

---

## Tech Stack

AWS S3  
Databricks  
Python  
SQL  
Power BI  

---

## Notes

- Dataset used is synthetic  
- Architecture reflects real production setup  

---

## Future Improvements

- Data quality checks  
- Monitoring & alerting  
- Parameterized pipelines  
