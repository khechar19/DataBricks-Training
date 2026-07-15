# Databricks SQL Practice Assignment - Day 1

This repository contains a comprehensive collection of SQL queries designed for **Day 1** of my practice with fundamental to intermediate data manipulation and querying using Databricks (Spark SQL). 

## 📌 Overview
This Day 1 assignment revolves around a mock `Employees` dataset. It includes the SQL script to create the table structure, populate it with sample data, and solve a series of analytical questions categorized by SQL clauses and operators.

## 🗄️ Database Schema
The queries are run against a single table named `Employees` with the following schema:
* `emp_id` (INT) - Unique ID for the employee
* `emp_name` (VARCHAR) - Name of the employee
* `department` (VARCHAR) - The department they work in (e.g., IT, HR, Finance)
* `salary` (INT) - Annual salary
* `city` (VARCHAR) - City of residence/work
* `experience` (INT) - Years of professional experience

## 🚀 Topics Covered (Day 1)
The SQL script covers a wide range of foundational SQL concepts, divided into the following categories:
* **Basic Retrieval:** `SELECT` statements
* **Filtering:** `WHERE` clause
* **Aggregation:** `GROUP BY`, `SUM()`, `AVG()`, `COUNT()`, `MAX()`, `MIN()`
* **Conditional Aggregation:** `HAVING` clause
* **Limiting Results:** `LIMIT` (Used in Databricks in place of SQL Server's `TOP`)
* **Unique Values:** `DISTINCT`
* **Comparison Operators:** `=`, `>`, `<`, `>=`, `<=`, `<>`
* **Logical Operators:** `AND`, `OR`, `NOT`
* **Set Operators:** `IN`, `NOT IN`
* **Range Operators:** `BETWEEN`, `NOT BETWEEN`
* **Pattern Matching:** `LIKE` (with `%` wildcards)

## 💻 How to Use in Databricks
1. Clone or download this repository.
2. Open your Databricks workspace and create a new **SQL Notebook**.
3. Ensure your notebook is attached to a running **Compute Cluster**.
4. Copy the table creation and insertion script to initialize the dataset.
5. Run the queries! 
   * *Note: If you paste all queries into a single cell, Databricks will execute them all but only display the output of the final query. It is recommended to place the `CREATE/INSERT` statements in one cell, and test individual `SELECT` queries in separate cells.*

## 📝 Example Query
```sql
-- Find average salary in each department where the average is greater than 60,000
SELECT department, AVG(salary) AS avg_salary 
FROM Employees 
GROUP BY department 
HAVING AVG(salary) > 60000;
