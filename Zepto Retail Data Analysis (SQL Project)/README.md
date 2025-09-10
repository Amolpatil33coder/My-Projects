# My-Projects
# 🛒 Zepto E-commerce SQL Data Analyst Portfolio Project

This is a real-world Data Analyst Portfolio Project based on an e-commerce inventory dataset inspired by Zepto, one of India’s fastest-growing quick-commerce startups.

The project simulates an end-to-end data analyst workflow — from raw dataset setup, data cleaning, and exploratory analysis to deriving business-driven insights using SQL.

🎯 Project Goals

The main objective is to replicate real-world data analyst tasks in the e-commerce/retail domain using SQL:

✅ Build a structured inventory database from raw data

✅ Perform Exploratory Data Analysis (EDA) to understand categories, stock, and pricing

✅ Clean messy data (null values, incorrect prices, unit conversions)

✅ Write SQL queries to answer business-oriented questions on stock, pricing, discounts, and revenue

📂 Dataset Overview

Source: Scraped product listings from Zepto, available on Kaggle

Unit of Data: Each row = a unique SKU (Stock Keeping Unit)

Special Case: Same product may appear multiple times due to different packaging/weights/discounts

🧾 Columns
Column	Description
sku_id	Unique identifier (Primary Key)
name	Product name
category	Product category (Snacks, Beverages, Fruits, etc.)
mrp	Maximum Retail Price (in ₹)
discountPercent	Discount percentage on MRP
discountedSellingPrice	Final price after discount (₹)
availableQuantity	Inventory count
weightInGms	Product weight in grams
outOfStock	Boolean flag for availability
quantity	Units per package
🔧 Project Workflow
1️⃣ Database & Table Creation

Created a SQL table with appropriate data types:

CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);

2️⃣ Data Import

Imported dataset (zepto.csv) into PostgreSQL using \copy command.

Fixed UTF-8 encoding issues by saving the file in CSV UTF-8 format.

3️⃣ Data Exploration

Counted total records

Viewed random samples to check structure

Detected null/missing values

Checked distinct categories & stock availability

Identified duplicate products (multiple SKUs for same item)

4️⃣ Data Cleaning

Removed rows with MRP or selling price = 0

Converted prices from paise → rupees

Ensured consistent data types across columns

5️⃣ Business Insights (SQL Queries)

📊 Top 10 best-value products (highest discount %)

📉 High-MRP items that are out of stock

💰 Revenue estimation per category

🔍 Expensive products (MRP > ₹500) with low discount

🏷️ Top 5 categories by average discount offered

⚖️ Price per gram → best value-for-money products

📦 Inventory weight grouped into Low / Medium / Bulk categories

🚀 How to Run

Clone the repository

git clone https://github.com/your-username/zepto-sql-project.git
cd zepto-sql-project


Open zepto_sql_analysis.sql in pgAdmin / DBeaver / any PostgreSQL client

Create a new database and run the SQL file

Import dataset (data/zepto.csv) ensuring UTF-8 encoding

Run the queries step by step

⚙️ Tech Stack

Database: PostgreSQL

Tools: pgAdmin / DBeaver

Skills Covered: SQL Queries, Data Cleaning, EDA, Business Insights

📌 Use Case

This project is highly useful for:

📊 Data Analyst aspirants building a portfolio

📚 Learners practicing SQL hands-on

💼 Preparing for e-commerce/retail/product analyst interviews
