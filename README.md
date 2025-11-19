
# **Customer Behavior Analysis**

### *Unlocking Insights From 3,900 Retail Transactions Using Python & SQL, exploring spending behavior, product preferences, customer segments, and subscription trends.*

<p align="center">

<!-- Project Badges -->
<br>

<img src="https://img.shields.io/badge/Project-Data%20Analytics-4B9CD3?style=flat" />
<img src="https://img.shields.io/badge/Tech-Python%20%7C%20%7C%20PostgreSQL-6C63FF?style=flat" />
<img src="https://img.shields.io/badge/EDA-Exploratory%20Data%20Analysis-brightgreen?style=flat" />
<img src="https://img.shields.io/badge/PowerBI-Reporting%20%26%20Dashboards-F2C811?style=flat" />
<img src="https://img.shields.io/badge/Status-Completed-success?style=flat" />


<br>

<br>

<!--  Name Badge  -->

<img src="https://img.shields.io/badge/Jeseena Parveen K-Data%20Analyst-pink?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTIiIGhlaWdodD0iMTIiIHZpZXdCb3g9IjAgMCAxMiAxMiIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48Y2lyY2xlIGN4PSI2IiBjeT0iNiIgcj0iNiIgZmlsbD0iI0ZGRiIvPjwvc3ZnPg==" />

<!--  LinkedIn Badge -->

<a href="https://www.linkedin.com/in/jeseena-parveen-k/">
<img src="https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat-square&logo=linkedin" />
</a>

</p>

---

## 1. Project Overview

This project analyzes customer shopping behavior using a structured workflow across Python (EDA + cleaning) and SQL (Business analysis).
Insights help the business understand **who their customers are, what they buy, and what drives revenue**.

## 2. Dataset Summary

| Property         | Details                                        |
| ---------------- | ---------------------------------------------- |
| **Rows**         | 3,900                                          |
| **Columns**      | 18                                             |
| **Data Types**   | Demographics, product info, behavioral metrics |
| **Missing Data** | 37 null values in *review_rating*              |

### **Key Features**

* **Demographics**: age, gender, location, subscription status
* **Purchase Details**: item, category, color, size, season
* **Behavioral Metrics**: purchase amount, discount applied, previous purchases, frequency, review rating
* **Engineered Fields**: `age_group`, `purchase_frequency_days`

## 3. Exploratory Data Analysis (Python)

### Data Loading

```python
df = pd.read_csv('data.csv')
df.info()
df.describe()
```

### Missing Data Handling

* Detected 37 missing ratings
* Filled using **median rating per category** for more meaningful imputation

### Column Cleaning

* Converted all column names to **snake_case**
* Standardized inconsistent category/text fields

### Feature Engineering

* **Age Grouping**: binned age into segments using `pd.cut()`
* **Purchase Frequency (Days)**: derived from purchase behavior
* Dropped `promo_code_used` after confirming it duplicates `discount_applied`

### Database Integration

* Loaded cleaned dataset into **PostgreSQL** using SQLAlchemy for advanced SQL analysis.
---
## 4. SQL Analysis & Business Insights

### **1. Revenue by Gender**

** Question:**

> Which gender group contributes more to total revenue?

**Result:**

* **Female:** 75,191
* **Male:** 157,890

**Insight:** Male customers contribute **2× more revenue**, indicating stronger purchasing power or more frequent purchases.

### **2. High-Spending Discount Users**

** Question:**

> Which customers use discounts yet still spend above the average amount?

**Insight:** This segment is **price-sensitive but high value**, ideal for personalized promotions.

### **3. Top 5 Products by Rating**

** Question:**

> Which products have the highest average review ratings?

**Result:**
- Accessories → Gloves (3.86)
- Footwear → Sandals (3.84)
- Footwear → Boots (3.82)
- Accessories → Hat (3.80)
- Clothing → Skirt (3.78)

**Insight:** Accessories and Footwear dominate product satisfaction.

### **4. Shipping Type Comparison**

** Question:**

> Does shipping type impact purchase amount?

**Result:**

* Standard: 58.46
* Express: 60.48

**Insight:** Express customers spend slightly more, suggesting urgency is tied to higher-value purchases.

### **5. Subscribers vs. Non-Subscribers**

** Question:**

> Do subscribers spend more than non-subscribers?

**Result:**
Subscribers spend **59.49** avg vs **59.87** for non-subscribers.

**Insight:** Spending is similar, but subscribers provide recurring value and loyalty retention.

### **6. Discount-Dependent Products**

** Question:**

> Which products are most purchased with discounts?

Top items: Hat (50%), Sneakers (49.66%), Coat (49.07%).

**Insight:** These products rely heavily on discounting strategies to drive sales.

### **7. Customer Segmentation via Purchase History**

** Question:**

> How many customers are New, Returning, or Loyal?

**Result:**

* Loyal: 3,116
* Returning: 701
* New: 83

**Insight:** The business has a strong **loyal customer base**, meaning retention strategies are working.

### **8. Top 3 Products per Category**

** Question:**

> What are the most purchased items within each category?

**Insight:** Helps identify **best-sellers** and optimize inventory planning.

### **9. Repeat Buyers & Subscriptions**

** Question:**

> Are frequent buyers (>5 purchases) more likely to be subscribers?

**Result:**

* Non-subscribers: 2,518
* Subscribers: 958

**Insight:** Heavy buyers still remain mostly non-subscribers → **opportunity for subscription campaigns**.

###  **10. Revenue by Age Group**

** Question:**

> Which age group generates the most revenue?

| Age Group | Revenue |
| --------- | ------- |
| Youth     | 62,143  |
| Mature    | 59,197  |
| Adult     | 55,978  |
| Senior    | 55,763  |

**Insight:** Youth and mature groups are the strongest revenue drivers.

---

## Overall Insights

### Customer Behavior

* Strong loyalty patterns; returning customers form the majority.
* Discount-driven items reveal price sensitivity in key categories.

### Product & Revenue

* Accessories and Footwear have the highest-rated products.
* Male customers generate substantially more revenue.

### Subscription Strategy

* Subscribers do not drastically outspend non-subscribers → retention is value-driven, not spend-driven.

### Operational Insights

* Express shipping correlates with higher order value.
* Top products per category highlight where inventory should be prioritized.

---
## 4. PowerBI Dashboard

Below are the core DAX measures used in the Power BI dashboard, created against the `public_customer` table:

```
Number_of_Customers = COUNT('public_customer'[customer_id])

Total Sales             = SUM  ('public_customer'[purchase_amount])

Average Purchase Amount = AVERAGE('public_customer'[purchase_amount])

Average Review Rating   = AVERAGE('public_customer'[review_rating])
```

This interactive Power BI dashboard provides a comprehensive view of **Customer Behavior Analysis**, combining customer demographics, sales performance, and purchasing trends.

### Date Model:

<img width="678" height="687" alt="Screenshot 2025-11-18 202535" src="https://github.com/user-attachments/assets/a9892890-623b-45cc-ae42-dffd9f607172" />


The visuals on **Page 1** of the dashboard include:

<img width="938" height="521" alt="Screenshot 2025-11-18 210355" src="https://github.com/user-attachments/assets/b6fd6d90-c400-4c24-83f2-bc0c8111a989" />

### **KPI Cards**

* **Total Customers (3.9K)** — Total unique customers in the dataset.
* **Total Sales (233K)** — Sum of all customer purchase amounts.
* **Average Purchase Amount ($59.76)** — Mean spending per transaction.

### **Donut Chart: % of Customers by Subscription Status**

* Shows distribution of **Subscribers vs. Non-Subscribers**.
* Business insight: Most customers (~73%) are **Non-Subscribers**, indicating opportunity for subscription growth.

###  **Bar Chart: Revenue by Category**

* Displays total revenue for each product category.
* Clothing leads with the highest revenue contribution (104K).

###  **Bar Chart: Sales by Category**

* Shows number of items sold within each category.
* Clothing again dominates with **1,737 sales**, followed by Accessories.

### **Bar Chart: Revenue by Age Group**

* Breaks down revenue contribution by customer age segmentation.
* Youth and Mature groups generate the highest revenue (~62K and 59K).

### **Bar Chart: Sales by Age Group**

* Illustrates the number of purchases by age segment.
* Youth customers make the most purchases (1,028 sales).

The visuals on **Page 2** of the dashboard include:

<img width="933" height="521" alt="Screenshot 2025-11-18 210405" src="https://github.com/user-attachments/assets/57d21e13-2c80-400e-ba3c-78bf8cecf4a9" />

### **Donut Chart: Sales by Gender**

* The chart indicates that 158K customers are male and 75K are female, showing a higher sales volume from male customers.

### **Bar Chart: Most Used Payment Method**

* **Payment Method Usage:** The bar chart highlights the most popular payment methods used by customers. PayPal tops the list with 677 transactions, followed by credit card (671), cash (670), debit card (636), Venmo (634), and bank transfer (612).

### **Bar Chart: Sales by Season**

* **Sales by Season:** The sales data is broken down by season, showing fairly consistent sales across Fall (60K), Spring (59K), Winter (59K), and Summer (56K). Fall has the highest sales volume, while Summer is the lowest, but still significant.

### **Heatmap: Sales by Item Purchased**

* This heatmap shows the sales volume for various products. Some of the top-selling items include:

  * **Blouse, Shirt, Pants (10K each)**
  * **Jewelry, Sweater, Coat (9K each)**
  * **Shoes, Socks, Boots, Sandals (9K each)**

  This section gives a quick overview of product categories that are selling well.

### **Map: Sales by Location**

 This shows the distribution of sales across different states in the U.S. The shading indicates the volume of sales, with darker shades representing higher sales numbers, giving insight into geographic trends.

### **Interactive Slicers**

Filters on the left allow dynamic analysis:

* **Subscription Status** (Yes/No)
* **Gender** (Male/Female)
* **Category** (Accessories, Clothing, Footwear, Outerwear)
* **Shipping Type** (Standard, Express, 2-Day, etc.)

### **Key Insights:**

* **Customer and Sales Overview:** The total number of customers is 3.9K, with a total of 233K sales transactions.
* **Gender and Payment Preferences:** Male customers outnumber female customers, and PayPal is the most used payment method.
* **Seasonal Trends:** Sales are consistent across seasons, with a slight dip in the summer months.
* **Product Popularity:** Certain categories, like blouses, shirts, pants, and shoes, are the top sellers.
* **Geographic Distribution:** Sales appear to be fairly widespread across the U.S., with specific areas having higher sales volumes.

---

## 6. Tools & Technologies

* **Python**: pandas, numpy, seaborn, SQLAlchemy
* **Database**: PostgreSQL
* **Visualization**: Power BI 
* **Version Control**: GitHub

---
