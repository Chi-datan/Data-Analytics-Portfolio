# 📊 DataAnalytics-Assessment

### Submission for Data Analyst SQL Assessment  
**Author:** Chinyere Onwusiribe

---

## 🧾 Overview

This repository contains solutions to a structured Data Analyst SQL assessment. Each file is designed to solve a specific real-world analytics challenge using optimized, well-commented MySQL queries. The goal is to demonstrate practical SQL skills that are scalable and efficient, even on large datasets.

---

## 📁 Files Included

| File Name            | Description                                     |
|----------------------|-------------------------------------------------|
| `Assessment_Q1.sql`  | High-Value Customers with Multiple Products     |
| `Assessment_Q2.sql`  | Transaction Frequency Analysis                  |
| `Assessment_Q3.sql`  | Account Inactivity Alert                        |
| `Assessment_Q4.sql`  | Customer Lifetime Value (CLV) Estimation       |

---

## 🔍 Per-Question Breakdown

### 🟡 Question 1: High-Value Customers with Multiple Products  
**Objective:** Identify customers who own at least one savings plan and one investment plan, then calculate their total confirmed deposits.

**Approach:**
- Used `LEFT JOIN` to connect customers, plans, and deposits.
- Used `CASE WHEN` to separate product types.
- Converted `confirmed_amount` from kobo to Naira.
- Filtered only customers with both savings and investment products.
- Sorted results by total deposit value (descending).

---

### 🟠 Question 2: Transaction Frequency Analysis  
**Objective:** Classify customers into Low, Medium, or High Frequency groups based on their average monthly transaction activity.

**Approach:**
- Calculated average monthly transactions using `TIMESTAMPDIFF` and `GREATEST` to avoid division by zero.
- Used `CASE` to categorize customers.
- Aggregated total counts per frequency tier.

---

### 🔴 Question 3: Account Inactivity Alert  
**Objective:** Identify accounts that have had no transactions in the last 365 days, even though they’re still considered active.

**Approach:**
- Used a CTE (`WITH inactive_owners AS (...)`) to isolate inactive customers.
- Joined with account data to fetch plan and customer info.
- Calculated inactivity using `DATEDIFF`.
- Presented the most recent transaction date.

---

### 🟢 Question 4: Customer Lifetime Value (CLV) Estimation  
**Objective:** Estimate CLV using transaction volume and tenure with a profit margin of 0.1%.

**Approach:**
- Calculated tenure in months using `TIMESTAMPDIFF`.
- Used `GREATEST(..., 1)` to prevent division errors for new users.
- Converted transaction amounts from kobo to Naira.
- Applied the simplified CLV formula and rounded to 2 decimal places.

---

## ⚙️ Challenges & Resolutions

### 🔹 Handling Large Datasets
- **Issue:** Timeout errors due to large joins.
- **Fix:** Filtered subqueries and used CTEs before applying heavy aggregations.

### 🔹 MySQL Limitation: `IN` with `LIMIT`
- **Issue:** MySQL doesn’t allow `LIMIT` inside `IN`.
- **Fix:** Switched to a `CTE` with a `JOIN`, which is more efficient.

### 🔹 Division by Zero
- **Issue:** New customers with <1 month tenure caused errors in CLV calculations.
- **Fix:** Used `GREATEST(tenure, 1)` to enforce a minimum divisor.

---

## 🧠 Skills Demonstrated
- Advanced SQL (JOINs, CTEs, subqueries, aggregation)
- Business logic implementation
- Data transformation and conversion
- Query performance optimization

---

## 📬 Contact
Thank you for reviewing this submission.  
Feel free to reach out for clarifications or collaboration.  

**Author:** Chinyere Onwusiribe

---
Updated README for portfolio
