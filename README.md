🛒 E-Commerce Sales Analytics & Recommendation System
===================================================

OVERVIEW
--------
An end-to-end data science project built on the UCI Online Retail dataset
containing 541,909 transactions from a UK-based online retailer between
December 2010 and December 2011. After cleaning, 396,046 records were used
for analysis across 9 columns.

Dataset Source: UCI Machine Learning Repository — Online Retail Dataset
Tools Used: Python, Pandas, NumPy, Matplotlib, Seaborn, SQLite, Scikit-learn,
            Statsmodels, MLxtend, Jupyter Notebook

---

PROJECT STRUCTURE
-----------------
Module 1 — Data Loading & Cleaning
Module 2 — SQLite Integration
Module 3 — Exploratory Data Analysis
Module 4 — Visualisations
Module 5 — RFM Customer Segmentation
Module 6 — Time Series Forecasting (ARIMA)
Module 7 — Market Basket Analysis (Apriori)
Module 8 — Recommendation System

---

MODULE DETAILS
--------------

Module 1 — Data Loading & Cleaning
- Loaded raw dataset (541,909 rows, 8 columns)
- Removed null values in CustomerID and Description
- Filtered out cancelled orders (InvoiceNo starting with 'C')
- Removed negative Quantity and UnitPrice values
- Cast CustomerID to integer
- Engineered TotalAmount = Quantity x UnitPrice
- Extracted YearMonth and Hour from InvoiceDate
- Final clean dataset: 396,046 rows, 9 columns

Module 2 — SQLite Integration
- Stored cleaned dataframe into SQLite database (RetailData.db)
- Performed SQL queries for customer analysis, hourly patterns,
  monthly revenue, and country-wise performance

Module 3 — Exploratory Data Analysis
- Total Revenue: £8,745,847
- Total Orders: 18,401
- Total Customers: 4,334
- Total Products: 3,658
- Date Range: April 2011 to September 2011
- UK contributes 83% of total revenue
- Peak order hour: 12 PM
- Highest revenue month: November 2011

Module 4 — Visualisations
- Monthly revenue trend (line chart)
- Top 10 countries by revenue (bar chart)
- Top 10 products by quantity sold (bar chart)
- Orders by hour of day (bar chart)
- Order value distribution (histogram, log scale)

Module 5 — RFM Customer Segmentation
- Scored 4,334 customers on Recency, Frequency, Monetary (scale 1-5)
- Snapshot date: one day after last transaction
- Segments: Champions, Loyal Customers, Recent Customers, At Risk, Lost
- Champions: 1,100+ customers (largest high-value segment)
- Lost: largest overall segment — retention opportunity

Module 6 — Time Series Forecasting (ARIMA)
- Verified non-stationarity using ADF test
- Seasonal decomposition (additive, period=6) — identified upward
  trend and repeating 6-month seasonal pattern
- ARIMA(1,1,1) model fitted on 13 months of monthly revenue data
- 3-month forecast: Jan 2012 (£643,595) → Feb 2012 (£684,651)
  → Mar 2012 (£697,539)
- Forecast shows gradual recovery after December seasonal dip

Module 7 — Market Basket Analysis
- Filtered to UK transactions, top 100 most purchased products
- Built binary invoice-product matrix (13,123 x 100)
- Applied Apriori algorithm (min_support=0.02, low_memory=True)
- Generated 82 association rules (min_lift=2.0)
- Strongest rule: WOODEN STAR CHRISTMAS SCANDINAVIAN ->
  WOODEN HEART CHRISTMAS SCANDINAVIAN
  (Support: 0.023, Confidence: 74.8%, Lift: 22.5)

Module 8 — Recommendation System
- Content-Based: recommends products using association rules
  (based on what is frequently bought together)
- Collaborative Filtering: builds customer-product matrix,
  computes cosine similarity between customers, recommends
  products bought by similar customers but not yet by target customer
- Example: Customer 12346 recommended —
  SMALL CERAMIC TOP STORAGE JAR, JAM JAR WITH PINK LID,
  PARTY BUNTING, RED PUDDING SPOON,
  WOODEN HEART CHRISTMAS SCANDINAVIAN

---

KEY RESULTS
-----------
- UK dominates with £7.25M revenue (83% of total)
- November 2011 peak revenue: £1.14M
- Top customer (ID 14646): £279,138 revenue across 72 orders
- ARIMA forecast: revenue recovery to £697K by March 2012
- Strongest product association: Lift of 22.5 (Christmas items)
- Recommendation system successfully personalised suggestions
  for individual customers using collaborative filtering

---

LIBRARIES USED
--------------
pandas
numpy
matplotlib
seaborn
sqlite3
statsmodels
scikit-learn
mlxtend

---

AUTHOR
------
Rishika Sinha
GitHub  : https://github.com/rishika-sinha1315
Email   : rishikasinha1395@gmail.com
