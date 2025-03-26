# 🏙️ City of Vancouver Data Analytics Platform (DAP)

This repository showcases a real-world, cloud-native Data Analytics Platform (DAP) implementation for the City of Vancouver. The project demonstrates how AWS services can be leveraged for efficient, secure, and scalable data analytics — all without the use of local notebooks, instead relying on fully managed cloud tools.

---

## 🚀 Project Types

The portfolio includes six major types of data analytics and operations:

| Type                           | Description                                                                                          | Link |
|--------------------------------|------------------------------------------------------------------------------------------------------|------|
| 🧱 Design DAP Architecture      | Draw.io design of a scalable, secure Data Analytics Platform using AWS services                     | [View](./Design-Data-Analytics-Platform/Design.png) |
| 🔍 Exploratory & Descriptive   | Understand patterns in rental complaints, analyze totals per geo-local area                         | [View](./Descriptive-Analysis/Descriptive_Insights.md) |
| 🩺 Diagnostic Analysis          | Identify data outliers and root causes for anomalies using Athena                                   | [View](./Diagnostic-Analysis/Diagnostic_Analysis_Athena.md) |
| 🧹 Data Wrangling               | Clean and transform raw datasets using DataBrew & Glue ETL                                          | [View](./Data-Wrangling/Data_Wrangling_Report.md) |
| ✅ Data Quality Control         | Evaluate rule-based data validation (uniqueness, completeness) using Glue ETL                       | [View](./Data-Quality-Control/Data-Quality-Check.md) |
| 🔐 Data Security & Monitoring   | Encrypt, version, replicate and monitor data using KMS, S3, and CloudWatch                          | [View](./Data-Security/Data_Security_KMS.md) |

---

## 🛠️ AWS Services Used

- **Amazon S3** – Raw, transformed, and curated storage
- **AWS Glue & Glue DataBrew** – ETL jobs and visual data cleaning
- **Amazon Athena** – SQL-based querying
- **AWS KMS** – Encryption and key management
- **Amazon CloudWatch & CloudTrail** – Monitoring and activity logging

---

## 📂 Repository Structure

```bash
├── Data-Quality-Control/
│   ├── Data-Quality-Check.md
│   └── Screen-Shots/
│       ├── failed_folder.png
│       ├── monitoring_dashboard.png
│       ├── passed_folder.png
│       ├── quality_check_pipeline.png
│       └── quality_check_result.png

├── Data-Security/
│   ├── Data_Security_KMS.md
│   └── Screen-Shots/
│       ├── curated_versioning.png
│       ├── kms_key_creation.png
│       ├── raw_versioning.png
│       └── transformed_versioning.png

├── Data-Wrangling/
│   ├── Data_Wrangling_Report.md
│   └── Screen-Shots/
│       ├── Amazon_S3_Buckets.png
│       ├── Data_Profiling_Overview.png
│       ├── Job_Run_History.png
│       ├── Null_Value_Filter_Step.png
│       ├── Raw_Data_Ingestion.png
│       ├── Recipe_Steps.png
│       ├── System_Output_(Parquet).png
│       └── User_Output_(CSV).png

├── Descriptive-Analysis/
│   └── Descriptive_Insights.md

├── Design-Data-Analytics-Platform/
│   ├── Design.png
│   ├── Project 2 Design - Sujans Shrestha (2319052) Rental Issue.drawio
│   └── dap_architecture.drawio

├── Diagnostic-Analysis/
│   ├── Diagnostic_Analysis_Athena.md
│   ├── Query1.png
│   ├── Query2.png
│   ├── Result1.png
│   └── Result2.png

└── README.md  ← Main landing page
