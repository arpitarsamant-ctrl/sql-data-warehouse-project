# sql-data-warehouse-project
# SQL Data Warehouse from Scratch (SQL Server) — End-to-End DW + ETL

Build a modern **SQL Server** data warehouse that consolidates sales data for analytics and reporting: ingest → clean/transform → model for BI. This repo is structured like a real-world project (architecture, ETL layers, dimensional model, documentation).  
Inspired by the YouTube project: **“SQL Data Warehouse from Scratch | Full Hands-On Data Engineering Project”**.

---

## What this project does

- Ingests raw data from source systems/files into a **landing/staging layer**
- Applies **data cleansing + transformations** to create analytics-ready datasets
- Builds a **dimensional model** (star schema) optimized for reporting
- Produces **documentation** (ERD + data dictionary + lineage notes)

> Goal: a portfolio-ready warehouse you can demo with SQL queries and BI dashboards.  

---

## Architecture (Layered Warehouse)

A practical “layered” approach (a.k.a. Bronze/Silver/Gold / Staging→Warehouse→Mart):

- **Bronze / Staging**: raw tables (as-is from sources)
- **Silver / Warehouse**: cleaned + standardized + conformed entities
- **Gold / Data Mart**: star schema + aggregates for BI

```mermaid
flowchart LR
  A[Source Data\n(CRM/ERP/Files)] --> B[Bronze / Staging\nRaw Landing Tables]
  B --> C[Silver / Warehouse\nClean + Conform + Integrate]
  C --> D[Gold / Data Mart\nStar Schema + Aggregates]
  D --> E[BI / Analytics\nPower BI / Tableau / SQL]
