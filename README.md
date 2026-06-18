# AWS YouTube Data Pipeline

Production-style AWS data engineering project that ingests YouTube trending video data from both the YouTube Data API and historical Kaggle datasets, processes the data through a Medallion Architecture (Bronze, Silver, Gold), performs automated data quality validation, and produces analytics-ready datasets accessible through Amazon Athena.

![YouTube Trending Data Pipeline](YouTube%20Trending%20Data%20Pipeline.png)

## Overview

This project demonstrates the design and implementation of an end-to-end cloud-native data pipeline on AWS.

The pipeline automates the ingestion, transformation, validation, and aggregation of YouTube trending video data using serverless and managed AWS services. Historical data from Kaggle can be loaded into the Bronze layer for backfilling and testing, while current trending data is continuously collected through the YouTube Data API.

The solution follows the Medallion Architecture pattern:

* **Bronze Layer** – Raw JSON and CSV data stored in Amazon S3
* **Silver Layer** – Cleansed and standardized datasets stored as Parquet files
* **Data Quality Gate** – Automated validation checks before promotion
* **Gold Layer** – Analytics-ready business aggregation tables
* **Athena Query Layer** – SQL-based exploration and analytics

## Architecture

The architecture below illustrates the complete workflow from data ingestion to analytics consumption.

![Architecture Diagram](YouTube%20Trending%20Data%20Pipeline.png)

## Key Features

* End-to-end AWS data pipeline implementation
* Medallion Architecture (Bronze, Silver, Gold)
* Automated orchestration using AWS Step Functions
* Serverless data ingestion using AWS Lambda
* ETL processing with AWS Glue (PySpark)
* Data quality validation framework
* Athena-ready analytics datasets
* Monitoring and alerting using CloudWatch and SNS
* Historical data backfilling using Kaggle datasets
* Support for multiple YouTube regions

## Tech Stack

| Category              | Technology            |
| --------------------- | --------------------- |
| Cloud Platform        | AWS                   |
| Storage               | Amazon S3             |
| ETL                   | AWS Glue (PySpark)    |
| Compute               | AWS Lambda            |
| Orchestration         | AWS Step Functions    |
| Query Engine          | Amazon Athena         |
| Metadata Catalog      | AWS Glue Data Catalog |
| Monitoring            | Amazon CloudWatch     |
| Notifications         | Amazon SNS            |
| Programming Languages | Python, SQL, PySpark  |
| Data Formats          | JSON, CSV, Parquet    |

## Architecture Components

### Data Sources

* YouTube Data API v3 (Live Trending Data)
* Kaggle YouTube Trending Dataset (Historical Data)

### Bronze Layer

* Stores raw JSON and CSV files in Amazon S3
* Preserves original source data
* Serves as the data lake landing zone

### Silver Layer

* Cleanses and standardizes raw datasets
* Converts data into optimized Parquet format
* Applies schema enforcement and transformations

### Data Quality Gate

Automated validation checks include:

* Row count validation
* Null value validation
* Schema validation
* Data freshness checks
* Value range validation

### Gold Layer

Business-ready analytical datasets:

* `trending_analytics`
* `channel_analytics`
* `category_analytics`

### Analytics Layer

The Gold datasets are registered in AWS Glue Data Catalog and queried using Amazon Athena for downstream analytics and reporting.
