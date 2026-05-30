# Data Analytics Project Using Python, PostgreSQL and Power BI

## Overview

This project is a complete end-to-end Data Analytics Project that covers the full data analysis workflow.

The project starts with loading a dataset in Python, performing Exploratory Data Analysis, cleaning the data, running SQL queries using PostgreSQL, and finally building an interactive dashboard in Power BI.

The main objective of this project is to analyze raw data and convert it into meaningful business insights through Python, SQL, PostgreSQL, and Power BI.

This project is suitable for showcasing practical data analytics skills to recruiters.

---

## Project Objective

The main objectives of this project are:

- Load and understand the dataset using Python
- Perform Exploratory Data Analysis
- Clean and prepare the data for analysis
- Store and manage data using PostgreSQL
- Run SQL queries to extract useful insights
- Build an interactive Power BI dashboard
- Present key findings in a simple and professional way

---

## Dataset
The dataset used in this project contains customer and shopping-related information.
Example dataset name:

```text
customer_shopping_behavior.csv
The dataset includes information related to:
Customers
Products
Categories
Purchase behavior
Payment methods
Locations
Sales-related details

This dataset was used for data cleaning, exploratory data analysis, SQL querying, and dashboard creation.
Tool and Technologies Used
Tool / Technology	Purpose
Python	Data loading, cleaning, and analysis
Pandas	Data manipulation
NumPy	Numerical operations
Matplotlib	Data visualization
Seaborn	Data visualization
Jupyter Notebook	Writing and running Python code
PostgreSQL	Database management
SQL	Querying and analysis
SQLAlchemy	Connecting Python with PostgreSQL
Power BI	Dashboard creation
GitHub	Project hosting and documentation
Project Workflow
Dataset
   ↓
Python Data Loading
   ↓
Exploratory Data Analysis
   ↓
Data Cleaning
   ↓
PostgreSQL Database
   ↓
SQL Queries
   ↓
Power BI Dashboard
   ↓
Business Insights
Steps Performed
1. Data Loading

The dataset was loaded using Python and Pandas.

import pandas as pd

df = pd.read_csv("customer_shopping_behavior.csv")

After loading the dataset, basic checks were performed to understand the structure of the data.

df.head()
df.shape
df.info()
df.describe()
2. Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the dataset properly.
EDA included:
Checking number of rows and columns
Checking column names
Checking data types
Finding missing values
Finding duplicate records
Understanding numerical columns
Understanding categorical columns
Analyzing customer behavior
Analyzing product categories
Understanding purchase patterns
Example:
df.isnull().sum()
df.duplicated().sum()
df.nunique()
3. Data Cleaning

Data cleaning was performed to improve data quality and prepare it for analysis.
Cleaning steps included:
Removing duplicate records
Handling missing values
Renaming columns
Standardizing column names
Correcting data types
Removing unnecessary columns
Preparing data for SQL and Power BI
Example:
df columns = df.columns.str.lower().str.replace(" ", "_")
df.drop_duplicates(inplace=True)
4. PostgreSQL Database Connection

After cleaning the data, it was uploaded into a PostgreSQL database.
Python was connected with PostgreSQL using SQLAlchemy.
from sqlalchemy import create_engine
engine = create_engine(
    "postgresql+psycopg2://postgres:your_password@localhost:5432/your_database"
)
df.to_sql("customer", engine, if_exists="replace", index=False)

5. SQL Analysis
SQL queries were written to analyze the data from PostgreSQL.
Some SQL analysis performed in this project:
Total number of customers
Total number of orders
Category-wise order analysis
Most purchased products
Top performing categories
Payment method analysis
Customer behavior analysis
Location-wise analysis
Example SQL query:
SELECT category, COUNT(*) AS total_orders
FROM customer
GROUP BY category
ORDER BY total_orders DESC;

Another example:
SELECT payment_method, COUNT(*) AS total_transactions
FROM customer
GROUP BY payment_method
ORDER BY total_transactions DESC;
Example using ranking:
WITH item_counts AS (
    SELECT 
        category,
        item_purchased,
        COUNT(customer_id) AS total_orders,
        ROW_NUMBER() OVER (
            PARTITION BY category 
            ORDER BY COUNT(customer_id) DESC
        ) AS item_rank
    FROM customer
    GROUP BY category, item_purchased
)

SELECT 
    item_rank,
    category,
    item_purchased,
    total_orders
FROM item_counts
WHERE item_rank <= 3;
6. Power BI Dashboard

A Power BI dashboard was created to visualize the final insights.

The dashboard includes:

Total customers
Total orders
Category-wise sales
Product performance
Payment method distribution
Customer purchase behavior
Location-wise analysis
Interactive slicers and filters
KPI cards
Charts and graphs

The dashboard helps users understand overall business performance and customer shopping behavior in a simple visual format.

Dashboard Features

The Power BI dashboard contains:

KPI Cards
Bar Charts
Column Charts
Pie Charts / Donut Charts
Slicers
Filters
Category-wise analysis
Customer behavior analysis
Interactive report pages
Results

After completing the analysis, the following insights were generated:

Identified top-performing product categories
Found the most purchased items
Analyzed customer buying behavior
Understood payment method preferences
Found category-wise order trends
Created useful business insights through SQL queries
Built an interactive dashboard for better decision-making

This project shows how raw data can be converted into meaningful insights using Python, SQL, PostgreSQL, and Power BI.

Key Insights

Some key insights from the project include:

Which product categories are most popular
Which items are purchased the most
Which payment methods are commonly used
How customer behavior changes across different categories
Which categories contribute more to business performance
How SQL and Power BI can be used together for data analytics
How to Run This Project

Follow these steps to run this project on your system.

1. Clone the Repository
git clone https://github.com/your-username/your-repository-name.git
2. Open the Project Folder
cd your-repository-name
3. Install Required Python Libraries
pip install pandas numpy matplotlib seaborn sqlalchemy psycopg2-binary jupyter
4. Open Jupyter Notebook
jupyter notebook

Then open the notebook file and run all cells step by step.

5. Setup PostgreSQL Database

Create a database in PostgreSQL.

Example database name:

customer_behaviour

Update the database connection string in the Python notebook.

engine = create_engine(
    "postgresql+psycopg2://postgres:your_password@localhost:5432/customer_behaviour"
)
6. Upload Data to PostgreSQL

Run the Python code to upload the cleaned dataset into PostgreSQL.

df.to_sql("customer", engine, if_exists="replace", index=False)
7. Run SQL Queries

Open pgAdmin or PostgreSQL Query Tool and run the SQL queries used in the project.

8. Open Power BI Dashboard

Open the Power BI dashboard file in Power BI Desktop.

Example:

powerbi_dashboard.pbix
Project Folder Structure
Data-Analytics-Project/
│
├── customer_shopping_behavior.csv
├── data_analysis.ipynb
├── analysis_queries.sql
├── powerbi_dashboard.pbix
├── dashboard_preview.png
└── README.md
Required Libraries

The project uses the following Python libraries:

pandas
numpy
matplotlib
seaborn
sqlalchemy
psycopg2-binary
jupyter

Install them using:

pip install pandas numpy matplotlib seaborn sqlalchemy psycopg2-binary jupyter
Skills Demonstrated

This project demonstrates the following skills:

Python for data analytics
Data cleaning and preprocessing
Exploratory Data Analysis
PostgreSQL database handling
SQL query writing
Window functions in SQL
Power BI dashboard creation
Data visualization
Business insight generation
End-to-end analytics workflow
GitHub project documentation
Future Improvements

This project can be improved further by:

Adding more advanced SQL queries
Creating more dashboard pages
Adding forecasting analysis
Adding customer segmentation
Automating data refresh in Power BI
Adding advanced DAX measures
Adding dashboard screenshots on GitHub
Adding a detailed business case study
Conclusion

This project successfully demonstrates an end-to-end data analytics workflow.

The dataset was loaded and cleaned using Python, analyzed using PostgreSQL and SQL, and visualized using Power BI.

The final dashboard provides clear and useful insights that can help in understanding customer behavior, product performance, and business trends.

This project is suitable for showcasing practical data analytics skills to recruiters and can be added to a resume or portfolio.

Author

Shashwat Pratap Singh

B.Tech Computer Science Student
Data Analytics | Python | SQL | PostgreSQL | Power BI

Connect With Me
GitHub: https://github.com/shashwatsingh7717
LinkedIn:(https://www.linkedin.com/in/shashwat-pratap-singh-458862293?utm_source=share_via&utm_content=profile&utm_medium=member_android)
Email: shashwatsingh7717@gmail.com
