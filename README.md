# Azure Customer Analytics Pipeline

End-to-end Azure data engineering project that transforms raw AdventureWorks data into analytics-ready datasets using **Azure Data Factory, Azure Data Lake Storage Gen2, PySpark, Azure Synapse Analytics, and Power BI**.

## Overview

This project demonstrates the design and implementation of a cloud-based data pipeline for customer and sales analytics.

The solution follows a **Medallion Architecture**, separating data into Bronze, Silver, and Gold layers to maintain a clear progression from raw ingestion to analytics-ready data.

### Data Flow

```text
AdventureWorks Data
        ↓
Azure Data Factory
        ↓
ADLS Gen2 - Bronze
        ↓
PySpark Transformation
        ↓
ADLS Gen2 - Silver
        ↓
Azure Synapse Analytics
        ↓
ADLS Gen2 - Gold
        ↓
Power BI
```

## Technology Stack

| Technology | Purpose |
|---|---|
| Azure Data Factory | Data ingestion and pipeline orchestration |
| Azure Data Lake Storage Gen2 | Bronze, Silver, and Gold data storage |
| PySpark | Data cleaning and transformation |
| Azure Synapse Analytics | SQL querying and analytical processing |
| Parquet | Storage format for processed data |
| Power BI | Customer and sales analytics |
| GitHub | Version control and project documentation |

## Pipeline Implementation

### Data Ingestion

AdventureWorks datasets containing customer, product, sales, returns, calendar, and territory data are ingested through **Azure Data Factory** and stored in the Bronze layer of Azure Data Lake Storage Gen2.

### Bronze Layer

The Bronze layer preserves the raw source datasets before transformation, providing the starting point for downstream processing.

### Silver Layer

Data from the Bronze layer is processed using **PySpark**. Transformations are applied across the AdventureWorks datasets to prepare them for analytical workloads.

The processed datasets are written to the Silver layer in **Parquet format**.

The PySpark implementation is included in the repository under the `Notebooks` directory.

### Gold Layer

Azure Synapse Analytics is used to query the processed data and create analytical structures such as SQL views and external tables.

The Gold layer contains data prepared for downstream analytics and reporting.

### Analytics

**Power BI** is used as the final reporting layer to transform the processed customer and sales data into business-facing analytics and visualizations.

## Repository Structure

```text
Azure-customer-analytics-pipeline/
│
├── data/          # source datasets
├── Notebooks/     # PySpark transformation notebook
├── Workflow/      # Project implementation workflow
└── README.md
```

## Key Concepts Demonstrated

- End-to-end ETL pipeline development
- Azure cloud data engineering
- Medallion Architecture
- Data ingestion and orchestration
- PySpark DataFrame transformations
- ADLS Gen2 data lake design
- Parquet-based data processing
- Azure Synapse Analytics
- SQL views and external tables
- Power BI analytics and reporting

## Project Note

The Azure infrastructure used for this project was provisioned under a personal cloud subscription and is not maintained as a publicly accessible environment. The repository contains the source datasets, transformation implementation and supporting project documentation required to demonstrate the completed workflow.

**Raghul Sureshbabu**  
