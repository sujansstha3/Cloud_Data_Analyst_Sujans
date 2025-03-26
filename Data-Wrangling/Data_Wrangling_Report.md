# 🧹 Data Wrangling: Cleaning and Preparing Rental Issues Data for Analysis

## 📘 Project Description

This project focuses on the data wrangling of the **Rental Standard Current Issues** dataset from the City of Vancouver. By cleaning and transforming the dataset using AWS services such as **S3** and **Glue DataBrew**, the objective is to generate high-quality, structured data ready for analysis.

---

## 🏷️ Project Title

**Data Wrangling for Analytical Readiness of Rental Issue Dataset in the City of Vancouver**

---

## 🎯 Objective

To perform comprehensive data wrangling through ingestion, profiling, cleaning, and formatting to prepare rental-related data for downstream analysis such as descriptive summaries and outlier detection.

---

## 🏙️ Background

The City of Vancouver maintains rental issue data as part of its operational workflow. This raw data contains inconsistencies, missing values, and non-standard schemas that hinder accurate analysis. To overcome this, we developed a **data wrangling pipeline** using **AWS Glue DataBrew**, **Amazon S3**, and **ETL workflows** to clean and organize the data for reliable, actionable insights.

---

## 📊 Dataset

- **Source**: [City of Vancouver Open Data Portal](https://opendata.vancouver.ca/explore/dataset/rental-standards-current-issues/information/)
- **Records**: 475
- **Columns**: 9
- **Key Fields**: `Geo Local Area`, `Total Units`, `Total Outstanding`, etc.
- **File Format**: CSV
- **Data Types**: String, Integer, Double

---

## ⚙️ Methodology

### 1. 📥 Data Collection (Data Ingestion)

Data was ingested manually into an **Amazon S3 bucket** due to the absence of a cloud-based operational environment. Three S3 buckets were created to segment data processing stages:

| S3 Bucket Name  | Purpose |
|-----------------|---------|
| `cov-raw-suj`   | Stores raw ingested data from the operational environment |
| `cov-trf-suj`   | Stores transformed data post-cleaning and quality processing |
| `cov-cur-suj`   | Stores curated data containing final business insights and summaries |

> ⬇️ Amazon S3 Buckets  
![S3 Buckets Overview](./s3_bucket_overview.png)

