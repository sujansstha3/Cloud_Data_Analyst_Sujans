# 🏙️ City of Vancouver Data Analytics Platform (DAP)

This repository showcases a real-world, cloud-native Data Analytics Platform (DAP) implementation for the City of Vancouver. The project demonstrates how AWS services can be leveraged for efficient, secure, and scalable data analytics — all without the use of local notebooks, instead relying on fully managed cloud tools.

---

## 🚀 Project Types

The portfolio includes six major types of data analytics and operations:

| Type                           | Description                                                                                          | Link |
|--------------------------------|------------------------------------------------------------------------------------------------------|------|
| 🧱 Design DAP Architecture      | Draw.io design of a scalable, secure Data Analytics Platform using AWS services                    | [View](./Design-Data-Analytics-Platform/README.md) |
| 🔍 Exploratory & Descriptive   | Understand patterns in rental complaints, analyze totals per geo-local area                         | [View](./Descriptive-Analysis/README.md) |
| 🩺 Diagnostic Analysis          | Identify data outliers and root causes for anomalies using Athena                                   | [View](./Diagnostic-Analysis/README.md) |
| 🧹 Data Wrangling               | Clean and transform raw datasets using DataBrew & Glue ETL                                          | [View](./Data-Wrangling/README.md) |
| ✅ Data Quality Control         | Enforce completeness, uniqueness using visual ETL and quality rules                                 | [View](./Data-Quality-Control/README.md) |
| 🔐 Data Security & Monitoring   | Encrypt data, version S3 buckets, replicate and track metrics via CloudWatch                        | [View](./Data-Security/README.md) |

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
│   └── README.md
├── Data-Security/
│   └── README.md
├── Data-Wrangling/
│   └── README.md
├── Descriptive-Analysis/
│   └── README.md
├── Design-Data-Analytics-Platform/
│   └── README.md
├── Diagnostic-Analysis/
│   └── README.md
└── README.md  ← Main landing page
