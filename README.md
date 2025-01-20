# Azure Data Engineering Project: End-to-End Data Transformation with Medallion Architecture

## Project Overview
- Implemented an end-to-end data pipeline using **Azure Data Factory (ADF)**, **Azure Databricks**, **Azure Synapse Analytics**, and **Azure Data Lake Gen2**.
- Utilized **Medallion Architecture** (Bronze, Silver, Gold) to structure the data pipeline and ensure incremental data processing and high-quality output.

## Tools and Technologies
- **Azure Data Factory (ADF)**
- **Azure Databricks (PySpark)**
- **Azure Data Lake Gen2**
- **Azure Synapse Analytics (Serverless SQL Pools)**
- **Microsoft Entra ID**
- **Python**
- **SQL**

## Architecture Overview
- **Bronze Layer**: Raw data ingestion.
- **Silver Layer**: Data cleansing and transformation.
- **Gold Layer**: Aggregated, transformed data ready for reporting.
 ![image](https://github.com/Swaleen277/ADE-AdventureWorks-Project/blob/main/Images/Data%20Architecture.jpg?raw=true)

## Project Workflow

AdventureWorks dataset, which is hosted on GitHub, process the data through multiple Azure services. Starting from raw data ingestion to final reporting using Power BI, this project implements a structured and scalable ETL pipeline.
![image](https://github.com/Swaleen277/ADE-AdventureWorks-Project/blob/main/Images/Resource%20Group.JPG?raw=true)

### 1. Data Ingestion (Bronze Layer)
- Ingested data from source using **Azure Data Factory** (ADF).
- Created an **HTTPS linked service** to connect ADF to the source.
- Data was fetched from the **Relative URL** after the linked service was set up.
- Used a **dynamic pipeline** to automate data ingestion into **Azure Data Lake Gen2**.
- Data stored in the **Bronze Layer** for further processing.
 ![image](https://github.com/Swaleen277/ADE-AdventureWorks-Project/blob/main/Images/ADF%20Pipeline%202.JPG?raw=true)
 ![image](https://github.com/Swaleen277/ADE-AdventureWorks-Project/blob/main/Images/ADF%20Pipeline.JPG?raw=true)

### 2. Data Transformation (Silver Layer)
- Data transformation was performed using **Azure Databricks** (PySpark).
- Established a connection between **Azure Data Lake Gen2** and **Databricks** using **Microsoft Entra ID** for authentication (Application ID, Secret Value, and Tenant ID).
- Compared the transformation process to **refining crude oil into petrol**, adding value to the raw data.
- Cleaned, transformed, and enriched the data.
![image](https://github.com/Swaleen277/ADE-AdventureWorks-Project/blob/main/Images/Databricks.JPG?raw=true)  

### 3. Data Storage and Final Output (Gold Layer)
- Created **views** and **external tables** in **Azure Synapse Analytics** (Serverless SQL Pools).
- **External Tables** created on top of the **metadata layer** for a unified view of the data.
- Final, transformed data pushed into the **Gold Layer** for business use and reporting.
  ![image](https://github.com/Swaleen277/ADE-AdventureWorks-Project/blob/main/Images/Synapse%20Analytics.JPG?raw=true)

## Key Takeaways
- **Scalability**: **Dynamic pipelines** in ADF ensure scalability for future data sources.
- **Data Quality**: Data cleansing and transformation ensure high-quality, valuable data.
- **Cost-Effective**: Using **serverless SQL pools** in Synapse Analytics optimizes costs.
- **Medallion Architecture**: Enables structured, incremental data transformation, improving data at each stage.

## Conclusion
- **Dynamic Pipelines**: Parameterized pipelines in ADF automate the ingestion process.
- **Efficient Transformations**: Databricks ensures data quality through transformation logic.
- **Seamless Querying**: Synapse Analytics provides easy access to data using OPENROWSET().
- **Interactive Dashboards**: Power BI offers a user-friendly visualization layer for reporting.

