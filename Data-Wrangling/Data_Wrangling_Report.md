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

⬇️ Amazon S3 Buckets  
![S3 Buckets Overview](./s3_bucket_overview.png)

⬇️ Raw Data Ingestion  
![Data Upload to S3](./s3_data_upload.png)

**Reason:**  
Since the operational system is not hosted on AWS, a manual upload ensures the data is accessible in S3 for transformation while simulating an eventual automated pipeline.

---

### 2. 🔍 Data Assessment (Data Profiling)

Using **AWS Glue DataBrew**, a data profile was generated for initial insights:

- Column data types  
- Missing/null values  
- Correlation and outlier detection via boxplots

⬇️ **Upload Screenshot**: Data Profiling Overview  
![Data Profiling](./data_profiling_overview.png)

**Key Insight:**

- `GeoLocalArea` contained 8 null values (~1%)  
- Most fields were string, followed by double and integer  
- These insights helped define the cleaning recipe

---

### 3. 🧼 Data Cleaning

#### 📋 Recipe Development

A **DataBrew recipe** was created with steps for:

- Converting column names to **CamelCase**  
- Removing rows with null values in `GeoLocalArea`  
- Trimming extra spaces and unifying text cases

⬇️ **Upload Screenshot**: Recipe Steps  
![Data Cleaning Recipe](./recipe_steps.png)

**Why CamelCase?**  
Industry best practice. Improves compatibility with Athena, ETL pipelines, and dashboards.

---

#### 🧹 Null Value Handling

`GeoLocalArea` was selected for cleaning due to its analytical importance in segmentation and group-by operations.

⬇️ **Upload Screenshot**: Null Value Filter Step  
![Null Filter](./null_filter_step.png)

---

### 4. 🚀 Job Execution & Output

A **DataBrew Job** was created and run to apply the cleaning recipe. Runtime statistics were captured to evaluate cost and performance.

⬇️ **Upload Screenshot**: Job Run History  
![Job Run History](./job_run_history.png)

---

### 5. 💾 Data Export & Output Formats

| Output Type     | Format             | Location              | Purpose                           |
|-----------------|--------------------|-----------------------|-----------------------------------|
| **User Output** | CSV (Uncompressed) | `cov-trf-suj/User`    | For accessibility, downloads      |
| **System Output** | Parquet (Snappy) | `cov-trf-suj/System`  | For analysis, compression-enabled |

⬇️ **Upload Screenshot**: User Output (CSV)  
![CSV User Output](./user_output_csv.png)

⬇️ **Upload Screenshot**: System Output (Parquet)  
![Parquet System Output](./system_output_parquet.png)

**Why Parquet + Snappy?**  
Efficient storage and partitioning for downstream analysis in Glue and Athena.

---

## 🧰 Tools & Technologies

| Tool                  | Purpose                                      |
|-----------------------|----------------------------------------------|
| **Amazon S3**         | Storage buckets for data lifecycle           |
| **AWS Glue DataBrew** | Visual tool for profiling and cleaning data  |
| **DataBrew Recipes**  | Reusable step-by-step data transformation    |
| **CSV / Parquet**     | Final formatted outputs                      |

---

## 📦 Deliverables

- ✅ Cleaned CSV and Parquet dataset in S3  
- 📊 Profiling summary from DataBrew  
- 🧾 Cleaning recipe and job history  
- 📝 Full documentation of the wrangling process  

---

## 📅 Timeline

| Phase                   | Duration |
|-------------------------|----------|
| Data Ingestion & Setup  | Week 1   |
| Data Profiling & Recipe | Week 2   |
| Cleaning & Validation   | Week 3   |
| Output & Documentation  | Week 4   |

---

## 📌 Conclusion

By designing a reusable and scalable data wrangling pipeline on AWS, we transformed raw rental issue data into a structured format, enabling further analysis such as descriptive summaries, visual ETL pipelines, and anomaly detection using Z-Score. This cleaned dataset lays the foundation for high-integrity decision-making in urban planning for the City of Vancouver.
