## sql-data-warehouse-project
Modern SQL Server data warehouse architecture with production‑grade ETL pipelines, curated dimensional models, and analytical datasets powering dashboards, KPIs, and data‑driven decision-making.

#### SQL Data Warehouse Project
A SQL-based data warehouse built on the Medallion Architecture (Bronze, Silver, Gold), ingesting data from CRM and ERP source systems and delivering clean, business-ready datasets for BI reporting, ad-hoc analysis, and machine learning.
Project Overview
This project builds a structured data warehouse from the ground up using SQL as the primary transformation language. Data flows from two source systems through three progressive layers, each with a clear responsibility, before landing in a consumption-ready format for analysts, dashboards, and data science teams.
The architecture follows the Medallion pattern:
Bronze - raw data, no changes, full auditability
Silver - cleansed, standardized, and enriched data
Gold - business-ready views with dimensional models and applied business logic

Source data arrives as flat CSV files from a CRM and an ERP system. By the time it reaches the Gold layer it has been validated, normalized, joined across domains, and shaped into star schema, flat table, and aggregated table formats ready for downstream consumption.
# Requirements
Technical requirements to run this project locally:
SQL Server 2019+ or PostgreSQL 13+
A SQL client (SSMS, DBeaver, or Azure Data Studio)
Git
Sample CSV source files included in the /datasets folder


### Specifications
Source Systems
SystemFormatDelivery MethodCRMCSVFiles and foldersERPCSVFiles and folders
Layer Specifications
LayerObject TypeLoad StrategyTransformationsBronzeTablesFull load, truncate and insertNoneSilverTablesFull load, truncate and insertCleansing, standardization, normalization, derived columns, enrichmentGoldViewsNo load, computed at runtimeData integration, aggregation, business logic, dimensional modeling

### Data Models in Gold
Star Schema - fact and dimension tables optimized for BI tools
Flat Table - denormalized wide tables for ad-hoc analyst queries
Aggregated Table - pre-summarized metrics for dashboards and ML feature sets

All Bronze and Silver loads follow a truncate-and-insert approach on each batch run. Gold views are defined once and computed dynamically on top of Silver at query time.
BI: Analytics & Reporting
The Gold layer is the direct source for all downstream consumption.
BI & Reporting
Power BI and Tableau connect directly to Gold views. The star schema is optimized for this - fact tables join cleanly to dimension tables, and DAX measures sit on top of already-clean data. No transformations happen inside the BI tool.
Ad-hoc SQL
Analysts query Gold views directly for exploratory analysis, one-off requests, and data validation. The data returned is already cleansed and standardized.
Machine Learning
Aggregated Gold tables serve as feature datasets for model training pipelines with consistent feature definitions across runs.

### License
MIT License. Free to use, copy, modify, and distribute for personal or commercial purposes. Attribution appreciated but not required.


### About Me
Oladeji Suleman - BI and Data Analyst with 8+ years building data pipelines, analytics solutions, and reporting systems across financial, healthcare, and energy sectors. This project is grounded in real patterns applied across enterprise analytics programs.
