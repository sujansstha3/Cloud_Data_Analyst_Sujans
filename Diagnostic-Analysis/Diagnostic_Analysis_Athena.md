# 🩺 Diagnostic Analysis: Investigating Outliers in Rental Data

## 🎯 Objective

To perform a **diagnostic analysis** on the Rental Standard Current Issues dataset using **Amazon Athena**, aiming to identify **outliers** that could skew insights derived from average-based summarization.

---

## 📌 Business Questions

1. **Are there any outliers in the Total Units per Geo Local Area?**
2. **Are there any outliers in the Total Outstanding Issues per Geo Local Area?**
3. **Do these outliers represent data issues (duplicates, incorrect values) or real-world anomalies?**

---

## 📂 Dataset

- 📄 **Title**: Rental Standard Current Issues
- 🌍 **Source**: [City of Vancouver Open Data Portal](https://opendata.vancouver.ca)
- 🧾 **Fields**: Total Units, Total Outstanding, Geo Local Area, etc.
- 📜 **License**: Open Government Licence – Vancouver

---

## 🧪 Diagnostic Methodology

### ✅ Tool Used: **Amazon Athena**
Athena enables SQL-based queries directly on data stored in S3, without provisioning servers.

### ✅ Outlier Detection Technique: **Z-Score**
- Z-score indicates how many standard deviations a data point is from the mean.
- Used to flag potential **anomalies** in Total Units and Outstanding values.

---

## 🔍 Query 1: Z-Score for Total Units

```sql
SELECT 
  "GeoLocalArea",
  AVG("TotalUnits") as avg_total_units,
  STDDEV_POP("TotalUnits") as stddev_total_units,
  COUNT(*) as count_area,
  MAX("TotalUnits") as max_units,
  MIN("TotalUnits") as min_units,
  ROUND((MAX("TotalUnits") - AVG("TotalUnits")) / STDDEV_POP("TotalUnits"), 2) as z_score
FROM cov_ren_trf_system
GROUP BY "GeoLocalArea"
ORDER BY z_score DESC;

