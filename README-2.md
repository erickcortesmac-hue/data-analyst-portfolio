# Erick Cortés — Data Analyst Portfolio

Hi, I'm Erick Sue Cortés Machado — a Business Administration graduate turned data enthusiast. My journey into data started from curiosity and a simple belief: that understanding numbers is one of the most powerful skills you can have in any business.

This repository contains all the projects, exercises and analyses I have completed throughout my self-taught data analyst journey. Every project uses real-world datasets and covers the full analyst workflow — from raw messy data to clean, actionable insights.

**Tools & Skills:** Python · SQL (MySQL) · Tableau · Excel · AWS

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/erick-cortes-a76a65272)

---

## Repository Structure

```
data-analyst-portfolio/
│
├── SQL/
│   ├── data_cleaning_layoffs.sql
│   └── exploratory_data_analysis.sql
│
├── Python/
│   ├── amazon_price_tracker.ipynb
│   ├── bmi_calculator.ipynb
│   ├── coinmarketcap_api_collector.ipynb
│   ├── exploratory_data_analysis.ipynb
│   └── olist_ecommerce_analysis.ipynb
│
├── Tableau/
│   ├── airbnb_tableau_dashboard.twbx
│   └── airbnb_presentation.pptx
│
└── README.md
```

---

## Projects

### SQL

#### Data Cleaning — Tech Layoffs Dataset
**File:** `SQL/data_cleaning_layoffs.sql`

A full data cleaning pipeline built entirely in MySQL on a real-world dataset tracking tech industry layoffs. Raw data was preserved throughout by working exclusively on staging tables while the original remained untouched.

**What was done:**
- Identified and removed duplicate records using `ROW_NUMBER()` with `PARTITION BY`
- Standardised inconsistent text — trimming whitespace, fixing industry name variations, removing trailing punctuation from country names
- Converted date strings to proper SQL `DATE` format using `STR_TO_DATE()`
- Recovered missing industry values intelligently using self-joins rather than simply deleting null rows
- Removed records with no usable data and dropped helper columns on completion

**Skills demonstrated:** MySQL · Window Functions · CTEs · Self-Joins · Data Type Conversion · Null Handling · Staging Table Methodology

---

#### Exploratory Data Analysis — Tech Layoffs Dataset
**File:** `SQL/exploratory_data_analysis.sql`

A deep exploratory analysis on the cleaned tech layoffs dataset, answering key business questions about which companies, industries and time periods were most impacted.

**What was done:**
- Identified companies with 100% workforce reductions and ranked by total headcount lost
- Analysed total layoffs by company, industry, country, funding stage and year
- Extracted month-by-month trends using `SUBSTRING()` on date columns
- Built a rolling total of layoffs over time using a window function `SUM() OVER`
- Ranked the top 5 companies by layoffs per year using `DENSE_RANK()` and a two-level CTE

**Skills demonstrated:** MySQL · Aggregations · GROUP BY · Window Functions · CTEs · DENSE_RANK · Rolling Totals · Date Functions

---

### Python

#### Amazon Price Tracker
**File:** `Python/amazon_price_tracker.ipynb`

An automated web scraper that monitors the price of a product on Amazon and sends an email alert when the price drops below a target threshold. Runs automatically every 24 hours and saves a timestamped price history to a CSV file.

**What was done:**
- Scraped live product data using `requests` and `BeautifulSoup`
- Cleaned and formatted extracted price and title text
- Appended timestamped records to a growing CSV dataset
- Automated the process with a loop and `time.sleep()`
- Configured email alerts using `smtplib` triggered by a price condition

**Skills demonstrated:** Python · Web Scraping · BeautifulSoup · requests · CSV File Handling · Automation · smtplib

---

#### BMI Calculator
**File:** `Python/bmi_calculator.ipynb`

An interactive Python application that calculates Body Mass Index from user input and classifies the result into health categories. A foundational project demonstrating core Python programming concepts.

**What was done:**
- Collected user input for name, weight (lbs) and height (inches) using `input()`
- Applied the standard BMI formula: `(weight × 703) / (height²)`
- Classified results into 6 health categories using nested `if/elif/else` logic
- Validated input to handle invalid entries gracefully

**Skills demonstrated:** Python · User Input · Arithmetic Operations · Conditional Logic · if/elif/else

---

#### CoinMarketCap API — Automated Data Collector
**File:** `Python/coinmarketcap_api_collector.ipynb`

An automated data pipeline that connects to the CoinMarketCap API and collects live cryptocurrency price data every minute, building a growing historical dataset over time.

**What was done:**
- Connected to a live REST API using `requests` with authentication headers
- Parsed nested JSON responses using `json.loads()` and `pd.json_normalize()`
- Added timestamps to each data collection and appended to a master dataframe using `pd.concat()`
- Automated collection with a `for` loop and `time.sleep()`
- Used `global` variables to persist data across function calls

**Skills demonstrated:** Python · REST APIs · JSON Parsing · pandas · Data Automation · pd.json_normalize()

---

#### Olist Brazilian E-Commerce Analysis
**File:** `Python/olist_ecommerce_analysis.ipynb`

An end-to-end exploratory data analysis on the Olist Brazilian E-Commerce public dataset — 100,000 real orders from 2016 to 2018 across 8 relational tables. Covers the full analyst workflow from raw data to business insights.

**What was done:**
- Loaded and audited 8 relational tables using `df.info()`, `isnull().sum()`, and `describe()`
- Calculated total revenue ($15.8M), total orders (98,666) and average order value ($160.58)
- Identified top 10 states by unique customer count — São Paulo leads with 41,746 customers
- Merged 3 tables to find top 10 product categories by total revenue
- Calculated average delivery time per state and identified fastest and slowest regions
- Analysed payment method distribution — credit card accounts for 73.9% of all orders
- Built a 5-table merge chain to find product categories with the worst review scores
- Created a monthly revenue pivot table showing year-over-year trends
- Built a complete seller performance report using `.agg()` and classified sellers as Top, Average or Poor using `np.select()`

**Skills demonstrated:** Python · pandas · Data Cleaning · Merging · groupby · pivot_table · melt · np.select · Boolean Filtering · Data Visualisation

---

### Tableau

#### Airbnb Dashboard
**Files:** `Tableau/airbnb_tableau_dashboard.twbx` · `Tableau/airbnb_presentation.pptx`

An interactive Tableau dashboard analysing Airbnb listing data, accompanied by a presentation summarising the key findings and business insights.

**Skills demonstrated:** Tableau · Data Visualisation · Dashboard Design · Business Storytelling

---

## About This Portfolio

All projects in this repository use real-world datasets and follow the professional data analyst workflow:

1. **Define the question** — what does the business need to know?
2. **Load and audit** — understand the data before touching it
3. **Clean** — duplicates, text, types, dates, nulls — in that order
4. **Analyse** — merge, group, pivot, filter
5. **Communicate** — turn numbers into insights

This portfolio is actively growing as I continue building skills across Python, SQL, Tableau, and cloud tools.

---

*Built with curiosity and a lot of coffee. Always learning.*
