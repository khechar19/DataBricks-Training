# Databricks PySpark Practice Assignment

This repository contains my PySpark data engineering practice using Databricks. It features a comprehensive, 98-question assignment transitioning from standard SQL logic to the **PySpark DataFrame API**.

## 📌 Overview
The project is built around creating mock PySpark DataFrames from scratch and applying various transformations, actions, date calculations, window functions, and joins. The Databricks notebook is cleanly partitioned using Markdown cells (`%md`) and Python execution cells (`%python`).

## 🗄️ Datasets Built in the Notebook
*   **`employee_df`**: Core employee information (`emp_id`, `name`, `age`, `department`, `salary`, `city`, `joining_date`, `manager_id`).
*   **`department_df`**: Department locations (`dept_name`, `location`).
*   **`manager_df`**: Manager details (`manager_id`, `manager_name`).
*   **`new_employee_df`**: Auxiliary dataset used for practicing Union operations.

## 🚀 Topics Covered
The 98 assignment questions are categorized into the following parts:
*   **Part A:** DataFrame Creation & Schema Definition
*   **Part B & C:** Select Operations & Column Transformations (`select`, `withColumn`, `when().otherwise()`)
*   **Part D & E:** Column Renaming & Filtering (`withColumnRenamed`, `filter`)
*   **Part F & G:** Sorting & Missing Data Handling (`orderBy`, `fillna`, `dropna`)
*   **Part H:** Date & Timestamp Functions (`to_date`, `datediff`, `year`, `month`)
*   **Part I & J:** Relational Joins & Set Operations (`inner`, `left`, `right`, `outer`, `left_anti`, `union`)
*   **Part K & L:** Aggregations & String Manipulations (`groupBy`, `lower`, `substring`, `concat_ws`)
*   **Part M & N / Challenge:** Advanced Window Functions & Analytical Reporting (`Window.partitionBy`, `rank`, `dense_rank`)

## 💻 How to Use in Databricks
1. Clone this repository or upload the notebook file into your Databricks workspace.
2. Attach your notebook to an active PySpark compute cluster.
3. **Important:** Run **Part A** first to load the base DataFrames (`employee_df`, `department_df`, `manager_df`) into the Spark session memory.
4. Execute the subsequent cells sequentially to inspect outputs using `.show()`.

## 📝 Example PySpark Snippet
```python
# Rank employees by salary within each department using PySpark Window functions
window_spec = Window.partitionBy("department").orderBy(col("salary").desc())
employee_df.withColumn("salary_rank", F.rank().over(window_spec)).show()
