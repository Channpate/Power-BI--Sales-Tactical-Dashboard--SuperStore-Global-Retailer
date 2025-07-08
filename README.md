# [Power BI] Sales Tactical Dashboard - SuperStore Global Retailer 

Author: Mai Ngoc Chau  
Date: 2025-03-26  
Tools Used: Power BI

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview  

### Objective:
### What is this project about? 

 This project analyzes sales situation at SuperStore Company using Power BI. The objective is:

✔️ Identify the overview sales scenario, with key metric Net Revenue.  
✔️ Identify potential markets and strategic product to expand market.  
✔️ Provide actionable insights through Power BI dashboards.  

### Who is this project for?  

- Data analysts & business analysts
- Sales/ Marketing Decision-makers & stakeholders  

---

## 📂 Dataset Description & Data Structure  

### Data Source  
- Source: (Mention where the dataset is obtained from—Kaggle, company database, government sources, etc.)  
- Size: 3 tables, the fact table contains 51290 rows, 20 columns  
- Format: .csv 

### 📊 Data Structure & Relationships  

#### 1️⃣ Tables Used: 3 tables
| Table Name | Rows | Columns |  
|----------|-------------|-------------| 
| Orders       |51290  | 20 |
| People       | 26 | 2 |
| Returns      | 1172 | 2 |

#### 2️⃣ Table Schema & Data Snapshot  

**Table 1: Orders** 

| Column        | Data Type | Description                                                             |
|---------------|-----------|-------------------------------------------------------------------------|
| Order ID      | String    | Unique identifier for each order placed.                                |
| Order Date    | Date      | Date when the order was placed.                                         |
| Ship Date     | Date      | Date when the order was shipped.                                        |
| Ship Mode     | String    | Shipping method used (e.g., Same Day, First Class).                     |
| Customer ID   | String    | Unique identifier for each customer.                                    |
| Customer Name | String    | Full name of the customer.                                              |
| Segment       | String    | Customer segment (e.g., Consumer, Corporate, Home Office).              |
| City          | String    | City of the customer.                                                   |
| State         | String    | State or province of the customer.                                      |
| Country       | String    | Country of the customer.                                                |
| Postal Code   | String    | Postal code of the customer’s address.                                  |
| Market        | String    | Market region (e.g., US, EU, APAC, Africa).                             |
| Region        | String    | Sub-region within the market (e.g., East, Central, Oceania).            |
| Product ID    | String    | Unique identifier for the product sold.                                 |
| Category      | String    | High-level classification of the product (e.g., Furniture, Technology). |
| Sub-Category  | String    | More specific classification under the main category.                   |
| Product Name  | String    | Full name or description of the product.                                |
| Sales         | Float     | Total sales amount for the line item (in local currency).               |
| Quantity      | Integer   | Number of units sold.                                                   |
| Profit        | Float     | Profit earned from the transaction. May be negative if there is a loss. |

| Order ID        | Order Date | Ship Date  | Ship Mode    | Customer ID | Customer Name    | Segment     | City          | State           | Country       | Postal Code | Market  | Region           | Product ID      | Category   | Sub-Category                              | Product Name                                                       | Sales   | Quantity | Profit   |
|-----------------|------------|------------|--------------|-------------|------------------|-------------|---------------|-----------------|---------------|-------------|---------|------------------|-----------------|------------|-------------------------------------------|--------------------------------------------------------------------|---------|----------|----------|
| CA-2012-124891  | 7/31/2012  | 7/31/2012  | Same Day     | RH-19495    | Rick Hansen      | Consumer    | New York City | New York        | United States | 10024       | US      | East             | TEC-AC-10003033 | Technology | Accessories                               | Plantronics CS510 - Over-the-Head monaural Wireless Headset System | 2309.65 | 7        | 762.1845 |
| IN-2013-77878   | 2/5/2013   | 2/7/2013   | Second Class | JR-16210    | Justin Ritter    | Corporate   | Wollongong    | New South Wales | Australia     | APAC        | Oceania | FUR-CH-10003950  | Furniture       | Chairs     | Novimex Executive Leather Armchair, Black | 3709.395                                                           | 9       | -288.765 |          |
| IN-2013-71249   | 10/17/2013 | 10/18/2013 | First Class  | CR-12730    | Craig Reiter     | Consumer    | Brisbane      | Queensland      | Australia     | APAC        | Oceania | TEC-PH-10004664  | Technology      | Phones     | Nokia Smart Phone, with Caller ID         | 5175.171                                                           | 9       | 919.971  |          |
| ES-2013-1579342 | 1/28/2013  | 1/30/2013  | First Class  | KM-16375    | Katherine Murray | Home Office | Berlin        | Berlin          | Germany       | EU          | Central | TEC-PH-10004583  | Technology      | Phones     | Motorola Smart Phone, Cordless            | 2892.51                                                            | 5       | -96.54   |          |
| SG-2013-4320    | 11/5/2013  | 11/6/2013  | Same Day     | RH-9495     | Rick Hansen      | Consumer    | Dakar         | Dakar           | Senegal       | Africa      | Africa  | TEC-SHA-10000501 | Technology      | Copiers    | Sharp Wireless Fax, High-Speed            | 2832.96                                                            | 8       | 311.52   |          |

**Table 2: People** 

| Column Name  | Data Type        | Description|
| ------------ | ---------------- | -------------|
| Person         | char        | Person in charge of each region     |
| Region         | char   | Market region (ex: Canada, AMEA,..)         |

| Person         | Region  |
|----------------|---------|
| Anna Andreadi  | Central |
| Chuck Magee    | South   |
| Kelly Williams | East    |
| Matt Collister | West    |

**Table 3: Returns**

| Column Name  | Data Type        | Description|
| ------------ | ---------------- | -------------|
| Returned         | char        |is-returned order (Yes/No)     |
| Order ID         | char   | order ID        |

| Returned | Order ID        |
|----------|-----------------|
| Yes      | MX-2013-168137  |
| Yes      | US-2011-165316  |
| Yes      | ES-2013-1525878 |
| Yes      | CA-2013-118311  |
| Yes      | ES-2011-1276768 |


#### 3️⃣ Data Relationships:  

![ERD diagram](https://github.com/Channpate/Power-BI--Sales-Tactical-Dashboard--SuperStore-Global-Retailer/blob/ead8cf148ca9b803a097bbcc56607961032d663e/PJ2-ERD.png)

---

## 🧠 Design Thinking Process  

Explain the step-by-step approach taken to solve the problem.  

👉🏻 Insert a screenshot of the Design Thinking steps (Screenshot your Excel design thinking tables for better presentation).  

1️⃣ Empathize  
2️⃣ Define point of view  
3️⃣ Ideate  
4️⃣ Prototype and review  

---

## ⚒️ Main Process

1️⃣ Data Cleaning & Preprocessing with Power Query 
2️⃣ Data Modeling and Create measures, parameters with DAX
3️⃣ Visualize dashboard 

---

## 📊 Key Insights & Visualizations  

### 🔍 Dashboard Preview  

#### 1️⃣ Dashboard 1 Preview  

![Page 1](https://github.com/Channpate/Power-BI--Sales-Tactical-Dashboard--SuperStore-Global-Retailer/blob/89630e1c225aa8d9fc3841b524d43793bb9fead5/Dashboard%20Capture/Dashboard%20-%20Page%201%20-%20Overview.png)

📌 Analysis 1:  
- **Observation:**
  - Net revenue has shown consistent growth over the years, but **monthly growth rate fluctuations** occur approximately
every two months.
  - **2013 recorded the highest growth rate (28.66%)**, indicating effective business strategies during that period.
  - Return rates are inconsistent and have increased in certain regions, particularly in the **EU and US.**  

- **Recommendation:**
  - **Analyze revenue cycles in detail** to identify key influencing factors (seasonality, promotions, supply chain, customer
behavior, etc.).
  - **Adjust sales strategies based on trends** to reduce volatility.
  - Implement **sales promotions in low-revenue months** to maintain stable growth.
  - Develop **post-peak discount campaigns** to sustain purchasing momentum.
  - **Review return policies** to better control return rates, particularly in the EU and US

#### 2️⃣ Dashboard 2 Preview  

![Page2](https://github.com/Channpate/Power-BI--Sales-Tactical-Dashboard--SuperStore-Global-Retailer/blob/89630e1c225aa8d9fc3841b524d43793bb9fead5/Dashboard%20Capture/Dashboard%20Page%202%20Market%20%26%20Product.png)

📌 Analysis 2:   
- **Observation:**
  - **APAC is the most promising market,** with strong revenue growth and the lowest return rate.
  - **EU, US, and LATAM have potential** but require better return rate management.
  - **Return rates in the US are gradually increasing,** necessitating closer monitoring and mitigation strategies.
  - **Canada has high order value but low overall revenue,** indicating a willingness to spend among customers.
    
- **Recommendation:**
  - **Expand in APAC** by focusing on high-demand, low-return products.
  - **Refine return policies in the EU and US**, possibly shifting toward product exchanges instead of refunds.
  - Develop new customer acquisition strategies in Canada, leveraging promotional campaigns or local business partnerships.

#### 3️⃣ Dashboard 3 Preview  

![Page 3](https://github.com/Channpate/Power-BI--Sales-Tactical-Dashboard--SuperStore-Global-Retailer/blob/89630e1c225aa8d9fc3841b524d43793bb9fead5/Dashboard%20Capture/Dashboard%20Page%203%20Customer.png)

📌 Analysis 3:  
- **Observation:**
  - Customer count is growing steadily each year, with no significant differentiation across customer segments.
  - Consumers are the primary customer group, but market-specific preferences are unclear.
  - Standard shipping is the most common mode, with little variation across regions.
  - Order value in Canada has consistently increased, despite low overall revenue.
  - On-time delivery rate could impact preferred shipping modes, requiring further analysis.
  
- **Recommendation:**
  - Analyze customer behavior by region to personalize sales strategies.
  - Increase customer acquisition efforts in Canada to raise order volume.
  - Optimize shipping modes by region, possibly experimenting with lower express shipping fees to assess its impact on sales.
  - Enhance on-time delivery rates to improve customer satisfaction and reduce return rates

---

## 🔎 Final Conclusion & Recommendations  

Based on the comprehensive sales, customer, and market analysis, the following conclusions and actionable strategies are recommended for stakeholder consideration:

✔️ Expand in APAC – Focus on high growth and low return regions to maximize revenue.

✔️ Control return rates – Improve payment policy changes in EU and US to minimize costs.

✔️ Target Canada smartly – Harness high purchasing power with appropriate engagement and incentives.

✔️ Stabilize monthly revenue – Reduce service delivery fluctuations during low season.

✔️ Improve Delivery Performance – Optimize priority protocols and increase on-time transaction rates to retain customers.
