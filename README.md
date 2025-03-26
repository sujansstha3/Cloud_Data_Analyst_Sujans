# 🏙️ City of Vancouver Data Analytics Platform (DAP)

This repository showcases a real-world, cloud-native Data Analytics Platform (DAP) implementation for the City of Vancouver. The project demonstrates how AWS services can be leveraged for efficient, secure, and scalable data analytics — all without the use of local notebooks, instead relying on fully managed cloud tools.

---

## 🚀 Project Types

The portfolio includes five major types of data analytics and operations:

| Type                           | Description                                                                                          | Link |
|--------------------------------|------------------------------------------------------------------------------------------------------|------|
| 🔍 Exploratory & Descriptive   | Understand patterns in rental complaints, analyze totals per geo-local area                         | [View](./descriptive-analysis/README.md) |
| 🩺 Diagnostic                  | Identify data outliers and root causes for anomalies using Athena                                    | [View](./diagnostic-analysis/README.md) |
| 🧹 Data Wrangling              | Clean and transform raw datasets using DataBrew & Glue ETL                                          | [View](./data-wrangling/README.md) |
| ✅ Data Quality Control        | Enforce completeness, uniqueness using visual ETL and quality rules                                 | [View](./data-quality-control/README.md) |
| 📊 Monitoring & Security       | Track AWS resource usage, encrypt data, and ensure cost-efficiency using KMS, Versioning, and CloudWatch | [View](./data-security/README.md) |

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
├── descriptive-analysis/
│   └── README.md
├── diagnostic-analysis/
│   └── README.md
├── data-wrangling/
│   └── README.md
├── data-quality-control/
│   └── README.md
├── data-security/
│   └── README.md
└── README.md  ← Main landing page
