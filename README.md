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

├── Data-Security/
│   ├── Data_Security_KMS.md
│   └── Screen-Shots/

├── Data-Wrangling/
│   ├── Data_Wrangling_Report.md
│   └── Screen-Shots/

├── Descriptive-Analysis/
│   └── Descriptive_Insights.md

├── Design-Data-Analytics-Platform/
│   ├── Design.png
│   ├── Project 2 Design - Sujans Shrestha (2319052) Rental Issue.drawio
│   └── dap_architecture.drawio

├── Diagnostic-Analysis/
│   └── Diagnostic_Analysis_Athena.md

└── README.md  ← Main landing page

