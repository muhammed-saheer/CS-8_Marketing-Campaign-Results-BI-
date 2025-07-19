# 📊 Marketing Campaign Analysis (Power BI)

This Power BI project analyzes marketing data from 2,240 customers of Maven Marketing. It explores customer demographics, purchase behavior, and marketing performance across multiple channels and products.

---

## 📁 Dataset Overview

The dataset contains the following key columns:[Link](https://www.kaggle.com/datasets/deepaksaw/marketing-dataset)

- **Customer Profiles**: Age, Education, Income, Marital Status, Number of Children
- **Product Spend**: MntWines, MntMeatProducts, MntFruits, MntFishProducts, MntSweetProducts, MntGoldProds
- **Channel Performance**: NumWebPurchases, NumStorePurchases, NumCatalogPurchases, NumDealsPurchases
- **Campaign Performance**: AcceptedCmp1 to AcceptedCmp5, Response
- **Date/Time**: Year_Birth, Dt_Customer

---

## 🧪 Data Preparation

### ✅ Cleaning
- Removed **24 rows** with null values in `Income`
- Converted columns to appropriate data types

### 🛠 Created New Columns:
- `Customer_Age = 2024 - Year_Birth`
- `Total_Children = Kidhome + Teenhome`
- `Amount_Spent = SUM(MntWines + MntMeatProducts + ...)` (via Unpivoting)
- `Age_Group` bucketed for better analysis

---

## 🧠 Business Questions Answered

---

### 🔍 Q1. What is the age distribution of customers?

**🎯 Goal**: Understand customer age groups  
**📊 Visuals**: Bar chart, pie chart, cards (Min, Max, Avg Age)  
**📝 Steps**:
- Created `Customer_Age` column
- Grouped ages into ranges (`20-29`, `30-39`, etc.)
- Added cards to show min (29), max (84), and average (56) age

**📷 Visual**:  
![Customer Age Distribution](https://github.com/muhammed-saheer/CS-8_Marketing-Campaign-Results-BI-/blob/main/images/Customer%20Age%20Distribution.png)

**✅ Conclusion**:  
Most customers are aged **50+**, with **60+ being the largest segment**. Very few under 30.

---

### 🔍 Q2. How does education level impact customer spending?

**🎯 Goal**: See if higher education correlates with higher spending  
**📊 Visuals**: Bar + Pie chart  
**📝 Steps**:
- Unpivoted product columns
- Aggregated `Amount_Spent` by `Education`
- Sorted and visualized in bar and pie charts

**📷 Visual**:  
![Education vs Spending](https://github.com/muhammed-saheer/CS-8_Marketing-Campaign-Results-BI-/blob/main/images/Education%20%26%20Spending.png)

**✅ Conclusion**:  
Customers with **Graduation and PhD** spend the most. Those with only **Basic education** spend the least.

---

### 🔍 Q3. What is the age profile of high spenders?

**🎯 Goal**: Identify which age ranges spend the most  
**📊 Visuals**: Line chart (Age vs Avg Spending)  
**📝 Steps**:
- Plotted `Customer_Age` vs average `Amount_Spent`
- Used line graph to observe spending trends

**📷 Visual**:  
![High Spender Age Profile](https://github.com/muhammed-saheer/CS-8_Marketing-Campaign-Results-BI-/blob/main/images/High%20Spender%20Age%20Profile.png)

**✅ Conclusion**:  
High spending is seen among **30–35** and **80–85** year olds. The spike at older age might be due to fewer but wealthier customers.

---

### 🔍 Q4. Which products are performing best?

**🎯 Goal**: Identify top-selling product categories  
**📊 Visuals**: Bar + Pie chart  
**📝 Steps**:
- Unpivoted product columns to get `Product_Type` and `Amount_Spent`
- Summed and ranked total spending

**📷 Visual**:  
![Product Performance](https://github.com/muhammed-saheer/CS-8_Marketing-Campaign-Results-BI-/blob/main/images/Product%20Performance%20(2).png)

**✅ Conclusion**:  
**Wines** and **Meat Products** dominate customer spending. **Fruits and sweets** are least purchased.

---

### 🔍 Q5. Which marketing channels are underperforming?

**🎯 Goal**: Find out which sales channels are least used  
**📊 Visuals**: Bar chart, Line chart (by age)  
**📝 Steps**:
- Summed values of `NumWebPurchases`, `NumCatalogPurchases`, etc.
- Plotted usage by channel and by age group

**📷 Visual**:  
![Channel Performance](https://github.com/muhammed-saheer/CS-8_Marketing-Campaign-Results-BI-/blob/main/images/Channel%20Performance.png)

**✅ Conclusion**:  
**Store purchases** are highest, followed by **Web**. **Deals and Catalog** are the least used—need attention or promotion.

---

## 🧾 Final Observations

- Older customers dominate the market
- Graduation/PhD holders are key spenders
- Wines and meat products are the best performing categories
- Catalog and deal-based channels need improvement

---

## 📁 File Info

**PBIX File Name**: `Marketing_Campaign_Insights.pbix`  
**Images Folder**: `marketing_case_images_final`  
**CSV Source File**: `marketing_data.csv`, `marketing_data_dictionary.csv`
"""
