
# **Customer Behavior Analysis**

### *Unlocking Insights From 3,900 Retail Transactions Using Python & SQL. The goal is to uncover insights about **spending behavior, product preferences, customer segments, and subscription trends**.*

<p align="center">

<!-- Project Badges -->
<br>

<img src="https://img.shields.io/badge/Project-Data%20Analytics-4B9CD3?style=flat" />
<img src="https://img.shields.io/badge/Tech-Python%20%7C%20SQL%20%7C%20PostgreSQL-6C63FF?style=flat" />
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



## 6. Tools & Technologies

* **Python**: pandas, numpy, seaborn, SQLAlchemy
* **Database**: PostgreSQL
* **Visualization**: Power BI 
* **Version Control**: GitHub

---
