# BUSA8000 – Assessment 01: Data Analysis for Dibs

**Student:** Saloni Borwankar  
**Student ID:** 48120901  
**Unit:** Techniques in Business Analytics

---

## Overview

This project involves end-to-end exploratory data analysis on a customer shopping dataset for a retail client called **Dibs**. The work covers data cleansing, descriptive statistics, visualisation, and business recommendations based on the findings.

The dataset contains roughly 99,000 transaction records across 10 columns including customer demographics, product categories, purchase prices, payment methods, and shopping mall locations.

---

## What's Covered

### 1. Data Cleansing
- Loaded and inspected the raw dataset (99,461 rows × 10 columns)
- Handled 2 missing prices (median imputation) and 1 missing payment method (filled as 'Cash')
- Identified and removed 1 invalid customer ID (`C2061##`) using regex pattern matching
- Converted `invoice_date` to `datetime64` format; flagged 15 unparseable dates
- Removed 3 duplicate records based on `invoice_no` and `customer_id`
- Standardised inconsistent category names (e.g. 'Toy' → 'Toys', 'Boks' → 'Books') and corrected payment method labels
- Visualised distributions of age, quantity, and price using histograms and boxplots
- Detected 5,024 price outliers via IQR — retained since they reflect genuine high-value category purchases (particularly Technology)
- Applied log transformation to price to address right-skew (skewness reduced from 2.25 to -0.23)

### 2. Descriptive Statistics & Data Exploration
- Compared spending distributions between male and female customers by category
- Scatter plot of age vs. spending revealed no meaningful relationship (correlation = 0.00)
- Segmented customers into age bands (18–25, 26–35, 36–45, 46–55, 56+) and compared average spending — the 36–45 group spent the most on average (~$700)
- Ranked product categories by average spending: Technology ($3,157) >> Shoes ($1,807) >> Clothing ($901) >> others

### 3. Recommendations
- Broke down total sales by payment method — Cash (44.8%), Credit Card (35.1%), Debit Card (20.1%)
- Plotted monthly sales trend from Jan 2021 to Jan 2023, identifying a sharp sales drop in early 2023
- Provided business recommendations around customer segmentation, loyalty programs, and category-focused marketing

---

## Libraries Used

- `pandas` — data loading, cleaning, and aggregation
- `numpy` — numerical operations and log transformation
- `matplotlib` — base plotting
- `seaborn` — statistical visualisations (boxplots, scatter plots, bar charts)

---

## How to Run

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
3. Place the dataset at `Assignment_/customer_shopping_data.csv`
4. Open and run `A1.ipynb` in Jupyter Notebook or JupyterLab

---

## Key Findings at a Glance

| Category       | Avg. Spend |
|----------------|------------|
| Technology     | $3,157     |
| Shoes          | $1,807     |
| Clothing       | $901       |
| Toys           | $108       |
| Cosmetics      | $122       |
| Books          | $46        |
| Souvenir       | $35        |
| Food & Beverage| $16        |

- Age and gender have minimal impact on overall spending
- Cash is the dominant payment method but digital payments are significant
- Sales were stable through 2021–2022, with a notable decline entering 2023

---

## Acknowledgement

GAITs (e.g., ChatGPT) were used for drafting and proofreading only, in line with assignment instructions.
