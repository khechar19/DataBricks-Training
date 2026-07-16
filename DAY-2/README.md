# Databricks SQL Practice Assignment - Day 2

This repository contains **Day 2** of my SQL practice journey using Databricks (Spark SQL). This phase heavily emphasizes advanced relational data operations, specifically focusing on **Joins** and **Set Operators**.

## 📌 Overview
The Day 2 assignment is split into two distinct parts:
1. **Joins:** Working with a normalized organizational database structure (`Employees`, `Departments`, `Projects`, `EmployeeProjects`) to map out complex relationships.
2. **Set Operators:** Working with segregated data logic (e.g., `CurrentEmployees` vs `FormerEmployees`, `OnlineOrders` vs `StoreOrders`) to manipulate sets of data vertically.

Every single query in the SQL script is preceded by a comment stating the exact assignment question, making it easy to read and review.

## 🗄️ Database Schemas

### Part 1: Joins
*   **Departments:** `DepartmentID`, `DepartmentName`, `Location`
*   **Employees:** `EmployeeID`, `EmployeeName`, `DepartmentID`, `Salary`, `ManagerID`, `JoiningDate`
*   **Projects:** `ProjectID`, `ProjectName`, `DepartmentID`, `Budget`
*   **EmployeeProjects:** `EmployeeID`, `ProjectID` (Mapping Table)

### Part 2: Set Operators
*   **Employee History:** `CurrentEmployees`, `FormerEmployees`
*   **Customer Geography:** `DomesticCustomers`, `InternationalCustomers`
*   **Sales Channels:** `OnlineOrders`, `StoreOrders`

## 🚀 Topics Covered (Day 2)

### 1. SQL Joins
*   **INNER JOIN:** Finding strictly matching records across tables.
*   **LEFT & RIGHT JOIN:** Preserving all records from the primary table while matching what exists in the secondary table.
*   **FULL OUTER JOIN:** Preserving all records from both sides, matching where possible.
*   **ANTI JOINS (Left/Right/Full):** Identifying "orphan" records—finding rows in one table that specifically *do not* exist in another (e.g., employees without departments).
*   **SELF JOINS:** Querying hierarchical data (e.g., finding an employee's Manager).

### 2. Set Operators
*   **UNION:** Combining vertically and removing duplicates.
*   **UNION ALL:** Combining vertically and keeping all duplicates (faster performance).
*   **EXCEPT (MINUS):** Subtracting the result set of one query from another.
*   **INTERSECT:** Finding the overlapping/common records between two queries.

## 💻 How to Use in Databricks
1. Clone or download this repository.
2. Open your Databricks workspace and create a new **SQL Notebook**.
3. Attach the notebook to your running **Compute Cluster**.
4. Paste the `CREATE` and `INSERT` blocks at the top of the script into a cell to build the tables.
5. The assignment queries are grouped by topic and difficulty. You can run them one by one to see how the joins and set operations manipulate the results. 
   *(Tip: Ensure you run queries in separate cells if you want to view the visual output table for each one.)*
