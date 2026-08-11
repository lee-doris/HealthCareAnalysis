# HealthCareAnalysis
# 🏥 Healthcare Insurance Claims Analysis

## 📌 Project Overview
This project performs an Exploratory Data Analysis (EDA) and statistical hypothesis testing on healthcare insurance claims data. The objective is to identify **high-cost medical specialties**, examine the **impact of patient demographics (e.g., marital status) on claim approval rates and claim amounts**, and optimize data quality to provide actionable insights for insurance risk control and policy pricing.

---

## 🛠️ Tech Stack & Tools
* **Programming Language**: Python
* **Data Processing & Cleaning**: Pandas, NumPy
* **Statistical Analysis & Testing**: SciPy (`scipy.stats`)
* **Data Visualization**: Seaborn, Matplotlib

---

## 🔍 Key Analysis & Methodology

### 1. Data Cleaning & Time Series Preprocessing
* **Type Conversion**: Converted `ClaimDate` to `datetime64` format and resampled data (`resample('ME')`) to analyze monthly trends in total claim amounts and claim counts.
* **Outlier Treatment**: Applied standard deviation and Interquartile Range (IQR) methods to identify and label extreme high-value claims, preventing skewed averages.
* **Missing Value Handling**: Utilized `.dropna()` to ensure analytical precision and avoid errors in downstream statistical testing.

### 2. High-Cost Specialty Ranking
* Grouped data by `ProviderSpecialty` (`groupby`) to calculate **total claim amount**, **average claim amount**, and **total claim volume**, identifying high-risk and high-cost medical specialties.

### 3. Statistical Hypothesis Testing
To rigorously verify whether patient demographic characteristics significantly influence claim outcomes, two statistical tests were conducted:
* **Chi-Square Test of Independence**:
  * **Objective**: Evaluate whether `PatientMaritalStatus` is independent of `ClaimStatus` (e.g., Approved, Denied).
  * **Output**: Calculated the Chi2 statistic and p-value to test the significance of marital status on claim approval likelihood.
* **One-Way ANOVA Test**:
  * **Objective**: Determine whether mean `ClaimAmount` differs significantly across different marital status groups.
  * **Output**: Used `stats.f_oneway()` to compute the F-statistic and p-value for precise risk profiling.

---

## 📊 Visualizations

### Average Claim Amount by Specialty Ranking

---

## 💡 Key Business Insights
1. **Specialty Risk Control**: For specialties exhibiting the highest average claim amounts, insurers can adjust underwriting criteria or implement tailored premium tiers.
2. **Demographic-Based Risk Assessment**: Statistical test results offer empirical evidence for underwriting and actuarial teams to refine risk classification models.
