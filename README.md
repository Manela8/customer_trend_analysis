# 🛍️ Customer Shopping Behavior Analysis — Python • SQL • Power BI

## 📌 Project Overview

This project analyzes transactional data from 3,900 customers to uncover spending patterns, product preferences, customer segments, and subscription behavior — simulating the end-to-end workflow of a professional data analyst.

---

## 📂 Dataset

| Property | Details |
|----------|---------|
| **Rows** | 3,900 transactions |
| **Columns** | 18 |
| **Categories** | Clothing, Accessories, Footwear, Outerwear |
| **Features** | Demographics, purchase details, shipping, discounts, review ratings, subscription status |
| **Missing Data** | 37 null values in Review Rating — imputed using category-wise median |

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| **Python** (pandas, SQLAlchemy, PyMySQL) | Data cleaning, EDA, database pipeline |
| **Jupyter Notebook** | EDA and data preparation |
| **MySQL** | Business queries — CTEs, window functions, segmentation |
| **Power BI** | Interactive dashboard |

---

## 🗂️ Project Structure

```
Customer_shopping_behaviour/
├── data/
│   ├── raw_data.csv                              # Original dataset
│   └── clean_data.csv                            # Cleaned dataset
├── notebooks/
│   └── data_cleaning_and_EDA.ipynb               # EDA and cleaning
├── SQL_scripts/
│   └── customer_trend_analysis.sql               # Business queries
├── customer_behavior_dashboard.pbix              # Power BI dashboard
├── Customer Shopping Behavior Analysis.pdf       # Project report
└── README.md
```

---

## 🔄 Workflow

### Phase 1 — Data Cleaning & EDA (Python)
- Imputed 37 missing Review Ratings using category-wise median
- Standardized all column names to snake_case
- Engineered `age_group` column by binning customer ages
- Engineered `purchase_frequency_days` from purchase frequency field
- Verified `discount_applied` and `promo_code_used` were redundant — dropped `promo_code_used`
- Loaded cleaned DataFrame into MySQL via SQLAlchemy pipeline

### Phase 2 — Business Analysis (SQL)
10 business queries covering:
- Revenue by gender and age group
- High-spending discount users (customers spending above average despite discounts)
- Top 5 products by average review rating
- Shipping type comparison — Standard vs Express
- Subscribers vs Non-subscribers revenue and spend
- Discount-dependent products (highest % of discounted purchases)
- Customer segmentation — New, Returning, Loyal (based on purchase history)
- Top 3 products per category using window functions
- Repeat buyers and subscription likelihood

### Phase 3 — Dashboard (Power BI)
Interactive single-page dashboard with slicers for Subscription Status, Gender, Category and Shipping Type:
- KPI cards — 3.9K customers, $59.76 avg purchase, 3.75 avg rating
- Subscription status split (donut chart)
- Revenue and sales by category and age group

---

## 💡 Key Findings

1. **Clothing dominates with $104,264 in revenue (1,737 transactions)** — nearly 3x Footwear and 5x Outerwear, making it the highest priority category for inventory and marketing.

2. **73% of customers (2,847) are non-subscribers yet spend more on average ($59.87 vs $59.49)** — subscriptions aren't driving higher spend, pointing to a need to re-evaluate loyalty benefits.

3. **3,116 out of 3,900 customers (80%) are classified as Loyal** — a strong retention base, but only 958 of repeat buyers (>5 purchases) hold subscriptions, a missed upsell opportunity.

4. **Discounts show no meaningful lift** — 839 customers spent above average even with discounts applied, while non-discount customers averaged $60.13 vs $59.28 with discounts, suggesting margin is being eroded unnecessarily.

5. **Young Adults generate the highest revenue ($62,143)** while Seniors ($55,763) are the most underleveraged segment — targeted campaigns for Seniors could unlock untapped revenue.

---

## 📋 Business Recommendations

- **Re-evaluate discount policy** — discounts are not lifting spend; consider targeted offers over blanket discounts
- **Boost subscription value** — 73% non-subscribers with equal or higher spend signals weak subscription incentives
- **Loyalty rewards for repeat buyers** — 3,116 loyal customers are an asset; reward programs could convert them to subscribers
- **Focus on Clothing and Accessories** — together they account for ~77% of total revenue
- **Target Senior segment** — lowest revenue contribution but a largely untapped demographic

---

## 🚀 How to Run

1. Run `data_cleaning_and_EDA.ipynb` to clean data and load into MySQL
2. Execute `customer_trend_analysis.sql` in MySQL Workbench
3. Open `customer_behavior_dashboard.pbix` in Power BI Desktop and refresh connection
4. View `Customer Shopping Behavior Analysis.pdf` for a static report snapshot

---
