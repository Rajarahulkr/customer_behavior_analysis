📊 Customer Shopping Behavior Analysis – End-to-End Data Analytics Project
📝 Overview

This project provides a complete end-to-end analysis of customer shopping behavior using Python, PostgreSQL, and Power BI.
Using 3,900 purchase records across 18 features (as shown on page 1 of the PDF 

Customer Shopping Behavior Analysis

), the objective was to uncover:

Spending patterns

Customer segments

Product preferences

Subscription behavior

Revenue drivers

Recommendations for business decisions

The project follows a structured analytics pipeline—from raw data to final dashboard & report.

📂 Dataset

Rows: 3,900
Columns: 18
(From dataset description on page 1 

Customer Shopping Behavior Analysis

)

Key Features

Demographics: Age, Gender, Location, Subscription Status

Purchase Details: Item Purchased, Category, Amount, Season, Size, Color

Behavior: Discount Applied, Promo Code Used, Previous Purchases, Frequency

Ratings & Shipping: Review Rating, Shipping Type

Missing Data:

37 missing values in Review Rating (page 1) 

Customer Shopping Behavior Analysis

🛠️ Tools & Technologies

Python → Pandas, NumPy, Matplotlib, Seaborn

PostgreSQL → SQL analysis

Power BI → Dashboard creation

Gamma → Report + PPT

Jupyter Notebook / VS Code

GitHub for documentation & version control

🚀 Project Workflow
1️⃣ Data Loading in Python
import pandas as pd
df = pd.read_csv("customer_data.csv")
df.head()

2️⃣ Exploratory Data Analysis (EDA)

As described in the PDF (page 1–2) 

Customer Shopping Behavior Analysis

:

Reviewed structure using df.info()

Generated summary stats using df.describe()

Analyzed missing values

Examined relationships between demographics, spending, rating & categories

3️⃣ Data Cleaning

Key cleaning steps (page 2) 

Customer Shopping Behavior Analysis

:

Imputed missing review ratings using median per category

Renamed columns to snake_case for consistency

Feature Engineering:

age_group (Young Adult, Middle-aged, Adult, Senior – see page 7)

purchase_frequency_days

Removed redundant column: promo_code_used

Example code:

df['review_rating'] = df.groupby('category')['review_rating'].transform(
    lambda x: x.fillna(x.median())
)

4️⃣ SQL Analysis in PostgreSQL

Data was loaded into PostgreSQL for business-focused queries (page 3–6) 

Customer Shopping Behavior Analysis

.

Key Insights from SQL:

Revenue by Gender: Compared male vs female contribution

Top 5 Highest Rated Products: Gloves, Sandals, Boots, Hat, Skirt (page 4 table)

Shipping Type Impact: Express shipping average = 60.48, higher than Standard = 58.46

Subscribers vs Non-Subscribers:

Subscribers: 1053 customers, revenue 62K

Non-Subscribers: 2847 customers, revenue 170K (page 4)

Top 3 Products per Category: As shown on page 6 (e.g., Jewelry, Sunglasses, Belt)

Example SQL:

SELECT category, SUM(purchase_amount) AS total_revenue
FROM shopping_data
GROUP BY category
ORDER BY total_revenue DESC;

5️⃣ Power BI Dashboard

An interactive Customer Behavior Dashboard was created (shown on page 7) 

Customer Shopping Behavior Analysis

.

Dashboard includes:

Number of customers

Average purchase amount

Average rating

Revenue by category

Revenue by age group

Sales by category

Subscription distribution

Filters: Gender, Category, Shipping Type, Season

6️⃣ Final Report & PPT

Using Gamma, a professional report and presentation was created summarizing:

Project Objective

Dataset Summary

Python EDA Output

SQL Findings

Power BI Visuals

Business Recommendations (page 7–8)

📈 Key Results & Business Insights

From SQL + Power BI analysis:

Young Adults contribute the highest revenue (62K) (page 7)

Express shipping users spend more on average

Subscribers spend slightly less per order, but bring long-term stability

Accessories & Clothing drive major revenue

Top-rated products include Gloves, Sandals & Boots

Repeat buyers have higher subscription likelihood

Discount-driven products can be targeted for margin improvement

▶️ How to Run This Project
1. Clone Repository
git clone https://github.com/yourusername/customer-shopping-analysis.git
cd customer-shopping-analysis

2. Install Python Dependencies
pip install -r requirements.txt

3. Run Python Notebook
jupyter notebook

4. Load Data into PostgreSQL

Create a table

Use COPY or Python psycopg2 to insert

Run queries from sql/queries.sql

5. Open Dashboard

Open the .pbix file inside the powerbi/ folder.

6. View Report & PPT

Open reports/gamma_report.pdf or presentation.pptx.


