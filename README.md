Retail Sales Analysis SQL Project

Project Overview

Project Title: Retail Sales AnalysisLevel: BeginnerDatabase: p1_retail_db

This project showcases essential SQL skills for data analysis by exploring, cleaning, and analyzing retail sales data. It involves setting up a database, performing exploratory data analysis (EDA), and deriving business insights through SQL queries. Ideal for those starting in data analytics, this project strengthens SQL proficiency while tackling real-world sales data challenges.

Objectives

Database Setup: Create and populate a retail sales database.

Data Cleaning: Identify and handle missing or null values.

Exploratory Data Analysis (EDA): Understand dataset trends and patterns.

Business Insights: Use SQL queries to extract meaningful insights.

Project Structure

1. Database Setup

Database Creation: The retail sales database p1_retail_db is created.

Table Structure: A table retail_sales is defined with relevant columns.

CREATE DATABASE p1_retail_db;

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

2. Data Exploration & Cleaning

Key SQL queries to analyze and clean the dataset:

SELECT COUNT(*) FROM retail_sales;
SELECT COUNT(DISTINCT customer_id) FROM retail_sales;
SELECT DISTINCT category FROM retail_sales;

DELETE FROM retail_sales
WHERE sale_date IS NULL OR sale_time IS NULL OR customer_id IS NULL;

3. Data Analysis & Insights

Example SQL queries used for analysis:

Total sales per category:

SELECT category, SUM(total_sale) AS net_sale, COUNT(*) AS total_orders
FROM retail_sales
GROUP BY category;

Top 5 customers by total sales:

SELECT customer_id, SUM(total_sale) AS total_sales
FROM retail_sales
GROUP BY customer_id
ORDER BY total_sales DESC
LIMIT 5;

Monthly sales trend analysis:

SELECT EXTRACT(YEAR FROM sale_date) AS year,
       EXTRACT(MONTH FROM sale_date) AS month,
       AVG(total_sale) AS avg_sale
FROM retail_sales
GROUP BY year, month
ORDER BY year, month;

Key Findings

Customer Insights: Identified key demographics and spending behavior.

Sales Trends: Seasonal and category-wise performance trends observed.

High-Value Transactions: Patterns in large purchases revealed.

Reports

Sales Summary: Comprehensive analysis of sales data.

Customer Segmentation: Understanding different buyer personas.

Peak Sales Analysis: Identifying high-revenue periods.

How to Use

Clone Repository: Download the project from GitHub.

Database Setup: Execute SQL scripts to create and populate tables.

Run Queries: Use the provided SQL scripts for insights.

Modify & Explore: Adapt queries for deeper analysis.
