# 🚨 RedFlag – Fraud Detection Using SQL

## 📌 Project Overview

**RedFlag** is a SQL-based fraud detection project designed to identify suspicious transaction patterns using **MySQL**.

The project analyzes transaction data and applies different rule-based detection techniques to identify potentially fraudulent users, transactions, and merchants.

This project was developed as **Minor Project-4**.

---

## 🎯 Objectives

The main objectives of this project are:

* Detect unusual transaction behavior.
* Identify users with suspicious transaction patterns.
* Analyze transaction frequency, amount, time, and location.
* Detect potential fraud indicators using SQL queries.
* Practice advanced SQL concepts such as CTEs, window functions, subqueries, aggregation, and date/time functions.

---

## 🛠️ Technologies Used

* **MySQL**
* **SQL**
* Common Table Expressions (CTEs)
* Window Functions
* Aggregate Functions
* `CASE` statements
* Subqueries
* `EXISTS`
* Date & Time Functions

---

## 🔍 Fraud Detection Patterns

The project implements **12 different fraud detection patterns**.

### 1. ⚡ Velocity Fraud

Identifies users with **30 or more transactions on a single day**.

This can indicate automated scripts, account takeover, or transaction churning.

---

### 2. 💰 Round-Amount Clustering

Identifies users making **15 or more transactions** using exact round-number amounts such as ₹100, ₹500, ₹1,000, ₹5,000, and ₹10,000.

The analysis identifies **25 suspicious users**.

---

### 3. 💳 Card Testing

Detects users making **30 or more transactions below ₹10 in a single day**.

This pattern can indicate possible card-testing activity. The analysis identifies **20 suspicious user-days**.

---

### 4. ❌ Failed-Then-Succeeded Behavior

Identifies users with **20 or more FAILED transactions**.

Repeated failed transaction attempts can indicate retry or card-testing behavior.

---

### 5. 🌙 Odd-Hour Concentration

Identifies users with:

* At least **30 transactions**
* At least **80% of transactions occurring between 2 AM and 5 AM**

The analysis identifies **20 suspicious users**.

---

### 6. 🏦 Mule Accounts

Detects users where a **CREDIT transaction is followed by a DEBIT within 30 minutes**, with the debit amount being at least **70% of the credit amount**.

Users with at least **5 qualifying instances** are identified as suspected mule accounts. The analysis identifies **30 suspected accounts**.

---

### 7. 🔄 Refund Abuse

Identifies users who:

* Have at least **20 total transactions**
* Have more than **40% of transactions classified as REFUND**

Approximately **24–25 users** are identified by this pattern.

---

### 8. 🏪 Merchant Collusion

Identifies merchants where the **top 5 users contribute more than 60% of the merchant's total transaction value**.

The analysis identifies **15 suspicious merchants**.

---

### 9. 💵 Just-Under-Threshold Structuring

Identifies users making **10 or more transactions exactly at ₹9,999**, which is just below the ₹10,000 threshold.

The analysis identifies **20 suspicious users**.

---

### 10. 💤 Dormant-Then-Active

Detects users who have a **90+ day gap between consecutive transactions**, followed by at least **15 transactions after the gap**.

Approximately **25–27 users** are identified.

---

### 11. 📈 Velocity Spike

Identifies users whose:

* Peak monthly transaction count is at least **20**
* Peak monthly transaction count is at least **5 times their average monthly transaction count**

Approximately **35–45 users** are identified.

---

### 12. 🌍 Geographic Impossibility

Identifies users whose consecutive transactions occur in **different cities within 60 minutes**.

This pattern can indicate potentially impossible physical movement between locations. The analysis identifies **15 suspicious users**.

---

## 🧠 SQL Concepts Demonstrated

This project helped demonstrate practical usage of:

```text
SELECT
WHERE
GROUP BY
HAVING
ORDER BY
CASE
SUM()
COUNT()
AVG()
MAX()
ROUND()
LAG()
ROW_NUMBER()
EXISTS
CTEs
JOIN
DATE()
HOUR()
DATE_FORMAT()
DATE_ADD()
TIMESTAMPDIFF()
```

---

## 📊 Project Findings

The SQL analysis successfully identified suspicious activity across multiple fraud patterns, including:

| Fraud Pattern            | Suspicious Cases |
| ------------------------ | ---------------: |
| Velocity Fraud           | ~45–55 user-days |
| Round-Amount Clustering  |         25 users |
| Card Testing             |     20 user-days |
| Failed Transactions      |         25 users |
| Odd-Hour Concentration   |         20 users |
| Mule Accounts            |         30 users |
| Refund Abuse             |     ~24–25 users |
| Merchant Collusion       |     15 merchants |
| Structuring              |         20 users |
| Dormant-Then-Active      |     ~25–27 users |
| Velocity Spike           |     ~35–45 users |
| Geographic Impossibility |         15 users |

## These findings are based on the detection rules and results documented in the project SQL submission.

## 📁 Project Structure

```text
RedFlag/
│
├── RedFlag_Umadevi_B.sql
└── README.md
```

---

## ▶️ How to Run the Project

### Step 1: Install MySQL

Install **MySQL Server** and **MySQL Workbench**.

### Step 2: Create/Select the Database

The SQL script uses the following database:

```sql
USE redflag;
```

### Step 3: Load the SQL File

Open:

```text
RedFlag_Umadevi_B.sql
```

in MySQL Workbench.

### Step 4: Execute the Queries

Run the queries individually or execute the complete SQL script.

Each section corresponds to a different fraud detection pattern.

---

## 📌 Key Learning Outcomes

Through this project, I gained practical experience in:

* Writing complex SQL queries.
* Performing transaction-level data analysis.
* Using CTEs to structure complex queries.
* Applying window functions for transaction history analysis.
* Working with date and time data.
* Identifying suspicious behavioral patterns.
* Using SQL for rule-based fraud detection.
* Translating real-world fraud scenarios into database queries.

---

## 🚀 Future Enhancements

Possible future improvements include:

* Building a **fraud detection dashboard**.
* Connecting the SQL analysis with **Python**.
* Applying **Machine Learning** for fraud prediction.
* Creating automated fraud alerts.
* Adding transaction risk scores.
* Visualizing suspicious users and merchants.
* Developing a real-time fraud monitoring system.

---



⭐ If you found this project interesting, feel free to explore the SQL queries and learn how different transaction patterns can be used to identify potential fraud.
