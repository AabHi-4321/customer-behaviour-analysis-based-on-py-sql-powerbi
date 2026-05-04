# Customer Behavior Analysis (Python + SQL + Power BI)

## Project Overview

This project focuses on analyzing **customer purchasing behavior** using an end-to-end data pipeline:

*  Data Cleaning using Python
*  Data Analysis using SQL
*  Data Visualization using Power BI

The goal is to extract meaningful insights about **customer preferences, spending patterns, and business performance**.

---

##  Tools & Technologies Used

* Python (Pandas, NumPy)
* MySQL
* Microsoft Power BI
* CSV Dataset

---

##  Dataset

 [View Dataset](https://github.com/AabHi-4321/customer-behaviour-analysis-based-on-py-sql-powerbi/blob/main/py_sql_powerbi/data/customer_shopping_behavior.csv)

---

##  Data Cleaning (Python)

Performed data preprocessing using Pandas:

### ✔ Handling Missing Values

```python id="v3l2k1"
df['Review Rating'] = df.groupby('Category')['Review Rating']\
                       .transform(lambda x: x.fillna(x.median()))
```

### ✔ Column Standardization

```python id="b91wqk"
df.columns = df.columns.str.lower().str.replace(' ', '_')
df = df.rename(columns={'purchase_amount_(usd)': 'purchase_amount'})
```

### ✔ Feature Engineering (Age Group)

```python id="z0md9x"
df['age_group'] = pd.qcut(df['age'], q=4, 
                         labels=['Young Adult','Adult','Middle-aged','Senior'])
```

---

## SQL Analysis

Key business questions solved using SQL:

* Revenue by gender
* High-value customers using discounts
* Top-rated products
* Shipping type vs spending
* Subscription impact on revenue
* Discount usage across products
* Customer segmentation (New / Returning / Loyal)
* Top products per category
* Repeat buyers vs subscription
* Revenue by age group

📁 Full queries available in repository (`queries.sql`)

---

## Power BI Dashboard

![Dashboard](https://github.com/AabHi-4321/customer-behaviour-analysis-based-on-py-sql-powerbi/blob/main/py_sql_powerbi/dashboard_image/dashboard_image.png)

---

## Key Insights from Dashboard

### Customer Spending Behavior

* Average purchase amount is **$59.76**, indicating moderate spending behavior
* Average review rating is **3.75**, suggesting overall satisfactory customer experience

---

### Customer Distribution

* Total customers: **~4,000**
* Only **7.3% customers are subscribed**, while **92.7% are non-subscribers**

👉 Indicates a **huge opportunity to improve subscription adoption**

---

### Category Performance

* **Clothing** generates the highest revenue and sales
* Followed by **Accessories**, while **Footwear & Outerwear** contribute less

👉 Suggests:

* Focus on high-performing categories
* Improve marketing for weaker categories

---

### Age Group Insights

* **Young Adults** contribute the highest revenue and sales
* Followed by **Middle-aged customers**
* Seniors contribute comparatively less

👉 Targeting **young adults** can maximize business growth

---

### Sales Pattern

* Sales distribution across categories aligns with revenue trends
* Indicates consistent pricing and purchasing behavior

---

### Subscription Insight

* Very low subscription rate (**7.3%**)

👉 Suggests:

* Weak subscription model OR
* Lack of awareness/benefits

---

## Conclusion

This project demonstrates:

* End-to-end data analysis workflow
* Data cleaning using Python
* Business insights using SQL
* Interactive visualization using Power BI


