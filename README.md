# Exploratory Data Analysis in MySQL

## 📌 Project Overview

This project focuses on performing Exploratory Data Analysis (EDA) using **MySQL and SQL** to uncover meaningful business trends and insights from a structured dataset.

The analysis uses SQL aggregation, filtering, grouping, ranking, and window functions to understand patterns in the data and generate insights that can support data-driven business decisions.

---

## 🎯 Project Objectives

The key objectives of this project were to:

* Explore and understand the structure of the dataset.
* Identify important business trends and patterns.
* Analyze key metrics using aggregate functions.
* Filter and segment data using `WHERE` and `HAVING`.
* Compare performance across different categories.
* Rank records using SQL window functions.
* Identify top-performing and underperforming segments.
* Generate actionable business insights from the analysis.

---

## 🛠️ Tools & Technologies

* **Database:** MySQL
* **Language:** SQL
* **Techniques:**

  * `SELECT`
  * `WHERE`
  * `GROUP BY`
  * `HAVING`
  * `ORDER BY`
  * Aggregate Functions
  * Subqueries
  * Common Table Expressions (CTEs)
  * Window Functions
  * `RANK()`
  * `ROW_NUMBER()`
  * `PARTITION BY`

---

## 📂 Project Structure

```text
exploratory-data-analysis-mysql/
│
├── README.md
├── data/
│   ├── raw/
│   └── cleaned/
│
├── sql/
│   ├── 01_database_setup.sql
│   ├── 02_data_cleaning.sql
│   ├── 03_exploratory_analysis.sql
│   ├── 04_window_functions.sql
│   └── 05_business_insights.sql
│
├── analysis/
│   └── analysis_summary.md
│
├── screenshots/
│   ├── database_schema.png
│   ├── query_results.png
│   └── key_insights.png
│
└── docs/
    └── data_dictionary.md
```

---

## 🔍 Analysis Performed

### 1. Data Exploration

Performed an initial exploration of the dataset to understand:

* Number of records
* Number of columns
* Data types
* Unique values
* Missing values
* Distribution of important variables

### 2. Aggregate Analysis

Used SQL aggregate functions such as:

```sql
COUNT()
SUM()
AVG()
MIN()
MAX()
```

to calculate important business metrics and identify overall trends.

### 3. Category-Level Analysis

Used `GROUP BY` to analyze metrics across different categories, segments, regions, or other relevant dimensions.

Example:

```sql
SELECT 
    category,
    COUNT(*) AS total_records,
    SUM(sales) AS total_sales,
    AVG(sales) AS average_sales
FROM dataset
GROUP BY category
ORDER BY total_sales DESC;
```

### 4. Filtering & Business Conditions

Used `WHERE` and `HAVING` to filter records and identify groups meeting specific business conditions.

Example:

```sql
SELECT 
    category,
    SUM(sales) AS total_sales
FROM dataset
GROUP BY category
HAVING SUM(sales) > 100000
ORDER BY total_sales DESC;
```

### 5. Ranking Analysis

Applied window functions such as `RANK()` to identify top-performing records within different groups.

```sql
SELECT
    category,
    product,
    sales,
    RANK() OVER (
        PARTITION BY category 
        ORDER BY sales DESC
    ) AS sales_rank
FROM dataset;
```

### 6. Row-Level Segmentation

Used `ROW_NUMBER()` to assign sequential rankings and identify the highest-performing records within each segment.

```sql
SELECT
    category,
    product,
    sales,
    ROW_NUMBER() OVER (
        PARTITION BY category
        ORDER BY sales DESC
    ) AS row_num
FROM dataset;
```

---

## 💡 Business Questions Addressed

The analysis was designed to answer questions such as:

1. What are the overall key metrics in the dataset?
2. Which categories generate the highest performance?
3. Which segments contribute the most to overall results?
4. Which categories have significantly higher average values?
5. What are the top-performing records within each category?
6. How does performance vary across different segments?
7. Which groups meet specific performance thresholds?
8. What patterns and trends can be identified from the data?

---

## 📊 Key SQL Concepts Demonstrated

| SQL Concept       | Application                 |
| ----------------- | --------------------------- |
| `SELECT`          | Data retrieval              |
| `WHERE`           | Row-level filtering         |
| `GROUP BY`        | Category-level analysis     |
| `HAVING`          | Aggregate-level filtering   |
| `ORDER BY`        | Sorting results             |
| `COUNT()`         | Record analysis             |
| `SUM()`           | Total metric calculation    |
| `AVG()`           | Average performance         |
| `MIN()` / `MAX()` | Range analysis              |
| `RANK()`          | Ranking records             |
| `ROW_NUMBER()`    | Sequential ranking          |
| `PARTITION BY`    | Segment-level analysis      |
| CTEs              | Structuring complex queries |
| Subqueries        | Multi-step analysis         |

---

## 📈 Key Insights

The analysis generated business insights by identifying:

* High-performing categories and segments.
* Top-ranked records within individual categories.
* Differences in average performance across groups.
* Groups exceeding predefined performance thresholds.
* Patterns that can help support data-driven decision-making.

> **Note:** The specific numerical insights are documented in `analysis/analysis_summary.md` based on the dataset used in the project.

---

## 🚀 How to Run the Project

### Step 1: Install MySQL

Install MySQL Server and MySQL Workbench.

### Step 2: Create the Database

Run:

```sql
CREATE DATABASE exploratory_data_analysis;
USE exploratory_data_analysis;
```

### Step 3: Load the Dataset

Import the dataset into MySQL using MySQL Workbench or the provided SQL setup script.

### Step 4: Run the SQL Scripts

Execute the scripts in the following order:

```text
01_database_setup.sql
02_data_cleaning.sql
03_exploratory_analysis.sql
04_window_functions.sql
05_business_insights.sql
```

### Step 5: Review the Results

The queries generate summary tables and analytical results that can be used to identify business trends and insights.

---

## 👨‍💻 Skills Demonstrated

* SQL
* MySQL
* Exploratory Data Analysis
* Data Cleaning
* Data Aggregation
* Business Analysis
* Window Functions
* Data Segmentation
* Data Ranking
* Analytical Thinking
* Data-Driven Decision Making

---

## 📌 Project Outcome

This project demonstrates the ability to use SQL to move from **raw data → structured analysis → business insights**.

It highlights practical experience with MySQL, advanced SQL querying, data exploration, and analytical problem-solving.
