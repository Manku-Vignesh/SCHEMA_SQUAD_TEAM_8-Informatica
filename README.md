# 📡 Telecom ETL & Revenue Analytics Pipeline

## 📌 Project Overview

This project implements an **end-to-end ETL pipeline** for processing Telecom Call Detail Records (CDR). The solution extracts raw data from CSV files, performs data cleaning and transformation, and generates analytical insights such as **customer revenue contribution and top customers**.

---

## 🎯 Objectives

* Clean and transform raw telecom data
* Handle missing and inconsistent values
* Remove duplicate records and track rejects
* Calculate revenue per call
* Build analytical outputs:

  * Revenue per customer
  * % contribution to total revenue
  * Top 2 customers

---

## 🗂️ Source Data

### 1. CDR_RAW_Telecom.csv

| Column         | Description             |
| -------------- | ----------------------- |
| CallID         | Unique call identifier  |
| CallerReceiver | Caller phone number     |
| Duration       | Call duration (seconds) |
| CallType       | LOCAL / STD / INT       |
| TowerID        | Tower identifier        |
| Timestamp      | Call time               |

---

## ⚙️ ETL Process

### 🔹 1. Extract

* Read CSV files using Informatica IICS

---

### 🔹 2. Transform

#### ✔ Data Cleaning

* Replace NULL duration with `0`
* Fix timestamp format
* Remove duplicate records

#### ✔ Derived Fields

* **Revenue Calculation**

[
Revenue = Duration \times 0.02
]

* **International Flag**

```sql
ISINTERNATIONAL = IIF(CallType = 'INT', 1, 0)
```

---

### 🔹 3. Load

#### ✔ Staging Table: `STG_CDR`

Stores cleaned and transformed data

#### ✔ Reject Table: `REJECT_CDR`

Stores duplicate records with reason:

```text
REJECT_REASON = 'DUPLICATE'
```

---

t Table
```

---



---



## 🛠️ Technologies Used

* **Informatica IICS** (ETL)
* **SQL / Oracle / MySQL**
* **CSV Files (Input Data)**

---

## 🔥 Key Highlights

* Real-world ETL pipeline design
* Data cleaning & validation
* Duplicate handling with reject tracking
* Revenue analytics with ranking
* Scalable and modular mapping

---

## 📢 Conclusion

This project demonstrates how raw telecom data can be transformed into meaningful business insights using ETL techniques. It highlights practical implementation of **data engineering concepts**, including transformation logic, aggregation, and analytical reporting.

---


---

## 📌 Future Enhancements

* Dashboard using Power BI / Tableau
* Real-time data processing
* Alert system for high usage customers

---
