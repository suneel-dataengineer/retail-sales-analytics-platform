# 🛒 Retail Sales Analytics Platform

## Project Overview
End-to-end Azure Data Engineering pipeline for retail sales analytics using Medallion Architecture (Bronze → Silver → Gold).

## Architecture
```
300 Stores (CSV Files)
        ↓
ADLS Gen2 — Bronze Layer (Raw Data)
        ↓
Azure Databricks — Silver Layer (Cleaned + Delta)
        ↓
Azure Databricks — Gold Layer (KPIs + Aggregations)
        ↓
Azure SQL Database (Reporting)
        ↓
Power BI Dashboards
```

## Tech Stack
| Tool | Purpose |
|------|---------|
| Azure Data Factory | Orchestration + Ingestion |
| ADLS Gen2 | Data Lake Storage |
| Azure Databricks | PySpark Transformations |
| Delta Lake | Reliable Data Storage |
| Azure SQL Database | Reporting Layer |
| GitHub | Version Control |

## Pipeline Design
**pl_master_orchestration:**
- Get Metadata → Auto detect store files
- ForEach + Copy → Bronze to SQL
- Databricks → Bronze to Silver (cleaning)
- Databricks → Silver to Gold (KPIs)
- Schedule Trigger → Daily 11PM automated
- Alerts → Success/Failure notifications

## KPIs Generated
- Daily Revenue per Store
- Product Category Performance
- Store Performance by Region

## Folder Structure (ADLS)
```
retailproject/
├── bronze/    → Raw CSV files
├── silver/    → Cleaned Delta tables
└── gold/      → Business KPI Delta tables
```

## Author
Suneel Kumar — Azure Data Engineer
