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
```
### 🧠 Insight

- **West End** had a **Z-score of 3.74**, suggesting it is significantly above the mean.
- This could indicate:
  - A true density anomaly
  - Or a possible outlier inflating the average


##🔍 Query 2: Z-Score for Total Outstanding Issues

```sql
SELECT 
  "GeoLocalArea",
  AVG("TotalOutstanding") as avg_total_outstanding,
  STDDEV_POP("TotalOutstanding") as stddev_outstanding,
  COUNT(*) as count_area,
  MAX("TotalOutstanding") as max_outstanding,
  ROUND((MAX("TotalOutstanding") - AVG("TotalOutstanding")) / STDDEV_POP("TotalOutstanding"), 2) as z_score
FROM cov_ren_trf_system
GROUP BY "GeoLocalArea"
ORDER BY z_score DESC;
```
### 🧠 Insight

- **Downtown** and **Strathcona** had the highest Z-scores for Total Outstanding.
- This could indicate:
  - 🛠️ Data issues (e.g., duplicate complaints, incorrect values)
  - 📈 Real-world escalation in rental issues in those areas


### ⚠️ Diagnostic Outcomes
| Area        | Z-Score | Possible Cause                      |
|-------------|---------|--------------------------------------|
| West End    | 3.74    | Density skew or data outlier         |
| Strathcona  | High    | Systemic issue or duplicate          |
| Downtown    | High    | Repeated reports or high severity    |

