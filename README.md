## RappiPlus: Business Profitability & Conversion Funnel Analysis

### 🎯 Proposed and Answered Business Questions

This project addresses key business questions related to revenue, operational costs, marketing expenditure, sales behavior, and user conversion funnels.   

#### 1. Business Profitability KPIs 
What is the total revenue?.   What is the total cost?. How much has been invested in marketing?. Is the business profitable?    

#### 2. Sales Behavior & Product Performance

What is the average ticket per order?. What is the average quantity of products per order?. What is the best-selling product?. How much was spent on marketing per channel?

### 🛠️ Process Description

The analysis is broken down into three main pipeline steps:

#### Step 1: Data Loading & Quality Validation

*Data Ingestion: Loaded raw datasets including rappiplus_orders_raw.csv, rappiplus_catalog.csv, and rappiplus_marketing_spend.csv.   

##### Data Cleaning & Normalization:

*Standardized date formats and renamed timestamp columns.  

*Corrected negative numerical values using absolute functions and fixed formatting errors in categorical columns.  

*Handled missing values across datasets by imputing with modes or mapping missing product categories based on product name prefixes.  

*Removed duplicate records and dropped rows with missing mandatory fields (~0.1% of the orders dataset).   

*Export: Cleaned datasets were exported to orders_clean.csv, catalog_clean.csv, and marketing_clean.csv for downstream use.   

#### Step 2: Profitability & Sales Behavior Analysis

*Data Merging:Combined orders and catalog data to calculate item-level and total costs against sales amounts.   

*Metric Computation: Aggregated core financial KPIs (revenue, costs, marketing spend, and profit) and evaluated product-level margins.   

*Visualization: Generated plots comparing net profit per product and marketing spend distribution across acquisition channels.   

#### Step 3: User Conversion Funnel Analysis

*Database Connection: Established a secure connection to a PostgreSQL production database using SQLAlchemy credentials. 

*Funnel Construction: Queried the events table to isolate unique users across various steps of the user journey (first_visit, select_item, add_to_cart, begin_checkout, add_payment_info, purchase). 

*Segmentation: Analyzed conversion performance globally as well as segmented by country to track where users drop off.   

### ⚙️ Implemented Technologies & Libraries

*Python: Core programming language used for data manipulation and analysis.   

*Pandas & NumPy: For data ingestion, cleaning, transformation, and vector calculations.   

*Seaborn & Matplotlib: For creating visual plots, distribution charts, and customized financial metrics graphs.  

*Plotly: For interactive data visualization.   Statsmodels (statsmodels.stats.proportion): For statistical proportion z-tests.   

*SQLAlchemy: For establishing database connectivity and running complex SQL queries against PostgreSQL.   

*PostgreSQL: Production database backend hosted on AWS RDS for user event log analysis.   
