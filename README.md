# Task-1-SofiaAhmed
Repository for Task 1 ( Data Cleaning and Preparation )


# E-Commerce Data Cleaning & Preparation Project

## 📌 Project Overview

This repository contains a comprehensive data cleaning and preparation project focused on transforming a raw, messy e-commerce dataset into an analysis-ready asset. The project systematically resolves critical data quality issues—such as missing values, duplicate records, structural inconsistencies, and formatting errors—using Python and standard industry data practices.

By establishing a robust data cleaning pipeline, the raw dataset was successfully validated to ensure 100% compliance with business logic and quality assurance standards, making it highly reliable for downstream business intelligence, dashboarding, and exploratory data analysis.

## 🛠️ Tools & Technologies

* **Language:** Python 


* **Libraries:** Pandas , NumPy 


* **Environment:** Jupyter Notebook 



## 📊 Dataset Profile

* **Dataset Name:** E-Commerce Orders Dataset 


* **Volume:** 1,200 records | 14 columns 


* **Key Features:** `OrderID`, `Date`, `CustomerID`, `Product`, `Quantity`, `UnitPrice`, `TotalPrice`, `ShippingAddress`, `PaymentMethod`, `OrderStatus`, `Tracking Number`, `ItemsInCart`, `CouponCode`, and `Referral Source`.



## ⚙️ Data Cleaning Pipeline (Change Log)

The following data engineering and remediation steps were executed to resolve data quality issues:

* **Missing Value Imputation:** Identified missing fields across the dataset. Imputed missing numerical values using column **medians** and missing categorical values using column **modes** to preserve data integrity without losing records.


* **Date Standardization:** Converted varied date entries into a unified `YYYY-MM-DD` format and eliminated invalid formatting errors.


* **Text & Format Normalization:** Stripped leading/trailing whitespaces and standardized text fields into a consistent case format, reducing category duplication caused by inconsistent data entry.


* **Deduplication:** Dropped identical duplicate rows and resolved duplicate `OrderID` entries to ensure every record represents a unique transaction.


* **Type Casting:** Enforced appropriate numeric data types across columns to enable seamless calculations and mathematical analysis.


* **Business Logic Validation:** Validated and programmatically recalculated the `TotalPrice` column using the formula:

$$\text{TotalPrice} = \text{Quantity} \times \text{UnitPrice}$$


This step effectively mitigated discrepancies and improved financial data accuracy.



## 🧪 Final Quality Assurance & Validation

A rigorous final validation script was executed to guarantee that the cleaned dataset met all data governance requirements:

```python
# Final validation checks
print("Total Missing Values:", df.isnull().sum().sum())
print("Duplicate Rows:", df.duplicated().sum())
print("Duplicate IDs:", df["OrderID"].duplicated().sum())

date_check = pd.to_datetime(df["Date"], errors="coerce").isnull().sum()
print("Incorrect Dates:", date_check)

```

### 📈 Validation Results:

* **Total Missing Values:** 0 


* **Duplicate Rows:** 0 


* **Duplicate IDs (OrderID):** 0 


* **Incorrect Dates:** 0 


* **Status:** **`PASS`** 



## 🚀 Key Takeaways

This project demonstrates a rigorous approach to the data cleaning phase of the data analytics lifecycle. It underscores how programmatic preprocessing ensures that underlying data is reliable, stable, and completely optimized to support accurate, data-driven business decision-making.
