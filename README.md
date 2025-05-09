# RetailSales_SQL_Project
A Retail Sales database analysis using Postgressql

This project  explores, clean, and analyze retail sales data. The project involves setting up a retail sales database, performing exploratory data analysis (EDA), and answering specific business questions through SQL queries. 

# Objectives
- Set up a retail sales database: Create and populate a retail sales database with the provided sales data.
- Data Cleaning: Identify and remove any records with missing or null values.
- Exploratory Data Analysis (EDA): Perform basic exploratory data analysis to understand the dataset.
- Business Analysis: Use SQL to answer specific business questions and derive insights from the sales data.

```sql
CREATE DATABASE retaildb;

CREATE TABLE retail_sales
(
    transactions_id INT PRIMARY KEY,
    sale_date DATE,	
    sale_time TIME,
    customer_id INT,	
    gender VARCHAR(10),
    age INT,
    category VARCHAR(35),
    quantity INT,
    price_per_unit FLOAT,	
    cogs FLOAT,
    total_sale FLOAT
);

```
# Data Exploration & Cleaning
Record Count: Determine the total number of records in the dataset.
Customer Count: Find out how many unique customers are in the dataset.
Category Count: Identify all unique product categories in the dataset.
Null Value Check: Check for any null values in the dataset and delete records with missing data.

'''sql
SELECT COUNT(*) FROM retail_sales;
SELECT COUNT(DISTINCT customer_id) FROM retail_sales;
SELECT DISTINCT category FROM retail_sales;

SELECT * FROM retail_sales
WHERE 
    sale_date IS NULL OR sale_time IS NULL OR customer_id IS NULL OR 
    gender IS NULL OR age IS NULL OR category IS NULL OR 
    quantity IS NULL OR price_per_unit IS NULL OR cogs IS NULL;

DELETE FROM retail_sales
WHERE 
    sale_date IS NULL OR sale_time IS NULL OR customer_id IS NULL OR 
    gender IS NULL OR age IS NULL OR category IS NULL OR 
    quantity IS NULL OR price_per_unit IS NULL OR cogs IS NULL;
'''

# 3. Data Analysis & Findings
The following SQL queries were developed to answer specific business questions:

Write a SQL query to retrieve all columns for sales made on '2022-11-05:

```sql
SELECT *
FROM retail_sales
WHERE sale_date = '2022-11-05';
```
# Write a SQL query to find the average age of customers who purchased items from the 'Beauty' category.:
```sql
SELECT
    ROUND(AVG(age), 2) as avg_age
FROM retail_sales
WHERE category = 'Beauty'
```

And more 









