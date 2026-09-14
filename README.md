# SQL Data Analytics Project

A comprehensive collection of SQL scripts for exploring, analyzing, and reporting on data in a relational data warehouse. The project walks through a full analytics workflow — from initial database exploration to polished customer and product reports — using a `gold`-layer sales dataset (customers, products, and sales facts).

The goal is to demonstrate best practices for writing clear, well-documented SQL for business intelligence and analytics work, and to serve as a reusable reference toolkit for common analytical patterns.

---

## 📂 Project Structure

```
sql-data-analytics-project/
│
├── datasets/                          # Source data for the project
│   ├── DataWarehouseAnalytics.bak     # SQL Server database backup
│   └── flat-files/                    # CSV versions of the same data
│       ├── dim_customers.csv
│       ├── dim_products.csv
│       └── fact_sales.csv
│
├── scripts/                           # SQL analysis scripts (run in order)
│   ├── 00_init_database.sql
│   ├── 01_database_exploration.sql
│   ├── 02_dimensions_exploration.sql
│   ├── 03_date_range_exploration.sql
│   ├── 04_measures_exploration.sql
│   ├── 05_magnitude_analysis.sql
│   ├── 06_ranking_analysis.sql
│   ├── 07_change_over_time_analysis.sql
│   ├── 08_cumulative_analysis.sql
│   ├── 09_performance_analysis.sql
│   ├── 10_data_segmentation.sql
│   ├── 11_part_to_whole_analysis.sql
│   ├── 12_report_customers.sql
│   └── 13_report_products.sql
│
├── docs/                              # Supporting documentation
│   ├── Project Roadmap.png / .pdf
│   └── Project_Notes_Sketches.pdf
│
├── LICENSE
└── README.md
```

---

## 🗃️ Dataset

The scripts operate on a `gold` schema with three tables representing a simplified sales data mart:

| Table | Description |
|---|---|
| `gold.dim_customers` | Customer dimension — names, demographics, location, etc. |
| `gold.dim_products` | Product dimension — category, subcategory, cost, etc. |
| `gold.fact_sales` | Sales fact table — orders, quantities, sales amounts, dates |

Data is provided two ways:
- **`datasets/DataWarehouseAnalytics.bak`** — a full SQL Server database backup you can restore directly.
- **`datasets/flat-files/*.csv`** — the same data as flat CSV files, useful for loading into other database engines.

---

## 🚀 Getting Started

1. **Set up the database.**
   Run `scripts/00_init_database.sql` to create the `DataWarehouseAnalytics` database and the `gold` schema.
   ⚠️ **Warning:** this script drops and recreates the database if it already exists — back up any existing data first.

2. **Load the data.**
   Restore `datasets/DataWarehouseAnalytics.bak` into your SQL Server instance, or import the CSV files from `datasets/flat-files/` into the `gold` schema tables on your platform of choice.

3. **Work through the scripts in order.**
   Scripts `01` through `13` are numbered to reflect a logical analytical progression, from basic exploration to advanced reporting. Each can also be run independently once the data is loaded.

---

## 📊 Script Overview

| # | Script | What it covers |
|---|---|---|
| 01 | Database Exploration | Lists tables, schemas, and column metadata via `INFORMATION_SCHEMA` |
| 02 | Dimensions Exploration | Unique values within dimension tables (e.g., countries, categories) |
| 03 | Date Range Exploration | First/last order dates and the overall time span of the data |
| 04 | Measures Exploration | Key aggregate metrics — totals, averages, counts |
| 05 | Magnitude Analysis | Grouped totals across dimensions (e.g., customers by country) |
| 06 | Ranking Analysis | Top/bottom performers using `RANK()`, `DENSE_RANK()`, `ROW_NUMBER()` |
| 07 | Change Over Time Analysis | Trends and seasonality using date functions |
| 08 | Cumulative Analysis | Running totals and moving averages with window functions |
| 09 | Performance Analysis | Year-over-year / month-over-month comparisons using `LAG()` |
| 10 | Data Segmentation | Custom `CASE`-based segmentation (e.g., cost ranges, customer tiers) |
| 11 | Part-to-Whole Analysis | Category contribution to overall totals |
| 12 | Customer Report | Consolidated customer-level report (segments, orders, sales, recency) |
| 13 | Product Report | Consolidated product-level report (segments, orders, sales, performance) |

The **Customer Report** (12) and **Product Report** (13) scripts are the capstone deliverables — each builds a reusable view that consolidates dozens of metrics and business segments into a single, report-ready dataset.

---

## 🛠️ Requirements

- A SQL Server instance (scripts use T-SQL syntax such as `DATETRUNC`, `DATEDIFF`, and `TOP`).
- SQL Server Management Studio (SSMS) or Azure Data Studio, or any T-SQL-compatible client.
- To use the flat files instead, adapt the syntax for your target database engine (PostgreSQL, MySQL, etc.).

---

## 📖 Documentation

See the `docs/` folder for a visual project roadmap and accompanying notes/sketches that outline the analytical approach behind the scripts.

---

## 🛡️ License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and share this project with proper attribution.

## 🌟 About Me

Hi there! I'm **Baraa Khatib Salkini**, also known as **Data With Baraa**. I'm an IT professional and passionate YouTuber on a mission to share knowledge and make working with data enjoyable and engaging!

Let's stay in touch! Feel free to connect with me on the following platforms:

[![YouTube](https://img.shields.io/badge/YouTube-red?style=for-the-badge&logo=youtube&logoColor=white)](http://bit.ly/3GiCVUE)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/baraa-khatib-salkini)
[![Website](https://img.shields.io/badge/Website-000000?style=for-the-badge&logo=google-chrome&logoColor=white)](https://www.datawithbaraa.com)
[![Newsletter](https://img.shields.io/badge/Newsletter-FF5722?style=for-the-badge&logo=substack&logoColor=white)](https://bit.ly/BaraaNewsletter)
[![PayPal](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/baraasalkini)
[![Join](https://img.shields.io/badge/Join-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@datawithbaraa)
