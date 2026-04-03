# 📊 Customer Sales Data Analysis using SQL

## 📌 Project Description
This project focuses on analyzing customer sales data using SQL to extract meaningful business insights. It includes customer spending analysis, segmentation, and sales performance evaluation.

---

## 🎯 Objectives
- Analyze customer purchase behavior  
- Calculate total spending of each customer  
- Identify customer lifespan  
- Segment customers into different categories  
- Generate business insights using SQL queries  

---

## 🛠️ Tools & Technologies
- SQL (MySQL)  
- Excel / CSV Dataset  

---

## 📂 Project Structure
```
Customer-Sales-Analysis
│── dataset/
│ └── sales_data.csv
│── sql/
│ └── queries.sql
│── README.md
```

---

## 📊 Key Analysis Performed

### 🔹 1. Customer Spending Analysis
- Calculated total sales per customer  
- Identified first and last order date  
- Measured customer lifespan using date functions  

### 🔹 2. Customer Segmentation
Customers are classified using SQL logic:

- **VIP** → High spending and long lifespan  
- **Regular** → Moderate spending  
- **New** → Recent customers  

---

### 🔹 3. Sample SQL Query
```sql
WITH customer_spending AS (
    SELECT 
        customer_id,
        SUM(sales) AS total_spending,
        MIN(order_date) AS first_order,
        MAX(order_date) AS last_order,
        TIMESTAMPDIFF(MONTH, MIN(order_date), MAX(order_date)) AS lifespan
    FROM fact_sales
    GROUP BY customer_id
)

SELECT
    customer_id,
    total_spending,
    lifespan,
    CASE 
        WHEN total_spending > 5000 AND lifespan >= 12 THEN 'VIP'
        WHEN total_spending <= 5000 AND lifespan < 12 THEN 'Regular'
        ELSE 'New'
    END AS customer_segment
FROM customer_spending;
```
---

## 🧠 SQL Concepts Used
- Common Table Expressions (CTE)  
- Aggregate Functions (SUM, MIN, MAX)  
- CASE Statements  
- GROUP BY  
- Date Functions (TIMESTAMPDIFF)  

---

## 🚀 How to Run the Project
1. Import dataset into MySQL  
2. Run the SQL queries provided  
3. Analyze the output tables  

---

## 📌 Key Learnings
- Writing structured SQL queries  
- Customer segmentation techniques  
- Working with real-world sales data  
- Using SQL for business insights  

---

## 👨‍💻 Author
**Mehul Vishwakarma**  
🔗 GitHub: https://github.com/MehulVi  

---
