# Horizon Mart Customer Loyalty Campaign Analysis

Skills: SQL, Tableau

### Table of contents

## Project Background

---

**Horizon Mart** is an omni channel retail company (physical locations and online platforms) based in San Francisco, California servicing the United States nationwide. The company was founded in 1975 with a focus on strong customer service and community.

Over the past 5 years, the company has invested in digital transformation, implementing an online shopping platform, loyalty subscription programs, and promo campaigns all aimed at driving engagement and building community. 

Reporting to the Business Intelligence Team, an in-depth analysis was conducted to evaluate the performance of Horizon Mart’s newest implementations, focusing on customer loyalty and promotional campaigns. This comprehensive review provides valuable insights that cross-functional teams will use to optimize operational efficiency and efficacy. This project uses The key insights and recommendations focus on the following areas: 

### Northstar Metrics

**Evaluating Customer Loyalty given the recently implemented loyalty campaign**

- **Customer Lifetime Value (CLV)**: measures the value of an individual customer by estimating their total revenue over a given lifespan. Average order value * annual purchase frequency (for this project)
- **Average Order Value (AOV)**: measures the average revenue per transaction. Average revenue per each distinct customer ID.
- **Repeat Purchase Rate**: measures the % of customers with more than one purchase. Customers that purchase more frequently than annually / all customers.
- **Subscriber Revenue Share**: % of revenue that comes from customers that are subscribed.

---

## Executive Summary

---

<aside>

## $2,124.17

Customer Lifetime Value

</aside>

<aside>

## $101.11

Average Order Value

</aside>

<aside>

## 81.3%

Repeat Purchase Rate

</aside>

<aside>

## 32.89%

Subscriber Revenue Share

</aside>

1. **Customer Loyalty Campaign Performance**
    
    *Subscription Program*
    
    - Subscribers make up 36% of the customer pool indicating that the recent campaign has been penetrating and functioning successfully
    - Subscribers see much higher **AOV** values ($123 to $91) and higher **CLV** values ($3,096 to $1,771)
    
    *Discounts and Promo Codes*
    
    - Discount and Promo Codes produce high **CLV** values ($2,575 and $2,644 respectively)
    - However, their **AOV** results are unchanging with little differences between customers that utilize discounts and promo codes and customers that don’t
    
    *Repeat Purchase Rate*
    
    - Repeat Purchase Rate of **81.3%** is impressively high, however, there is little deviation across segments (gender, subscribers, categories, promo codes, discounts, etc.) We interpret this result cautiously due to a limited dataset.

1. **Revenue Performance**
    - **Subscriber Revenue Share** is marginally lower than the customer subscriber pool (33% to 36%). While this isn’t alarming, it does indicate that the subscription program has not yet been fully optimized for revenue capture.
    - We can be confident about the trajectory of the subscription campaign given positive **AOV and CLV** results. Great news: there is still strong upside potential
    - Discounts and promo codes make up a much greater share of revenue in comparison to the subscription program
    - **Revenue** is dominated by two product categories: clothing and accessories. It is dominated by age groups between 26-45 and has a predominantly male audience

1. **Key Takeaways and Recommendations**
    - Customer Lifetime Performance is healthy and well above typical retail industry benchmarks
    - Customer Lifetime Value is **21x** Average Order Value indicating strong repeat spending patterns and long term value relative to individual purchases
    - The Subscription Program performs best in **CLV** and **AOV,** while discounts and promo codes perform best in **CLV** and **Revenue.**
        - Subscription Status = higher value customers
        - Discounts/promo codes = higher volume
    - Repeat Purchase Rate should be revisited with more robust data in order to confidently interpret its results
    - Despite an attempt to target specific locations, there doesn’t seem to be any clear patterns geographically
    - ***Expand and optimize subscription program.** Convert promo code and discount users to subscribers. Convert high-volume areas to subscribers.*
    - ***Support high-value and high-volume.** Bundle high-value categories with high-volume categories to boost high-value sales while stabilizing the high-volume areas.*
    - ***Leverage high value segments: clothing, accessories, males, 26-45 ages groups.** It will be effective leveraging promo codes and discounts in these areas specifically, higher margins and **AOV.** Also acts as a strong preliminary step in creating higher quality customers by exposing them to the subscription program.*
    

---

## Dataset Structure

---

The shopping behavior data consists of one main table: shopping_behavior_clean, originally containing 4,095 records of customer level purchases in the fiscal year 2024 with **18 fields** covering demographic attributes and behavioral indicators. The final cleaned data includes 3,165 records with 17 fields after cleaning null values and assessing usability. 

![Customer Id Gender.png](Customer_Id_Gender.png)

This dataset captures the shopping behavior of Horizon Mart customers in the fiscal year 2024. Each row represents customer level data of a single purchase with the **primary key** being Customer Id. Columns include **demographic attributes** (age, gender, location), **behavioral indicators** (category, subscription status, review rating, discount applied, promo code used, previous purchases, payment method, purchase frequency), and **supplemental columns** I created (age group, subscriber indicator, discount indicator, promo indicator) to aid analysis. 

The SQL queries used to develop this final cleaned dataset can be found here

---

## Insights Deep Dive

---

### 1. Customer Loyalty & Value

While evaluating Customer Loyalty & Value I utilized 3 key metrics: Customer Lifetime Value, Average Order Value, and Repeat Purchase Rate. Additionally, we compared these metrics across the 2 recently implemented campaigns: a subscription service and the discount and promo code campaign. Although both were designed to boost customer value and loyalty, I found that one performance much better than the other. 

---

**Subscription Program:** 

- CLV ****is **21x** that of AOV meaning each customer has roughly 21 orders in the given year. This is a powerful number
- CLV ****of subscribers approximately **74.9%** greater than the CLV ****of non-subscribers
- AOV of subscribers are approximately **35%** greater than the AOV of non-subscribers
- CLV independent of geographic location, no clear patterns emerge.
    - Highest CLV in Alaska, Montana, and Georgia
    - no weather driven relationships or cultural driven relationships
- Repeat Purchase Rate for subscribers and non-subscribers are identical: 81.8% — 81.1%
    - note: interpret this result cautiously due to limited dataset

![CLVbysubstatus.jpg](CLVbysubstatus.jpg)

---

**Discounts and Promo Codes:**

- CLV of discounts and promo codes performed successfully as well
    - Discounts: **43%** greater than customers who did not use discounts
    - Promo Code Used: **49%** greater than customers who did not use promo codes
- AOV of promo codes and discounts are similar to their counterparts, around **11% - 15%** greater than the AOV of non-users
    - discount/promo codes and the subscription program differ in this aspect
- Like the subscription program, repeat purchase rate is identical for users and non-users
    - *still, we interpret this result cautiously due to limited dataset*

---

![aovbysubstatus.jpg](b8c19ec8-e361-4f4a-8819-5884b2d2ab24.png)

![aovbydiscount.jpg](b99053da-e615-4bea-a7bf-7ec3bb5564c2.png)

![aovbypromocode.jpg](31a6cdb4-6b19-4e57-a1d2-191c2e3664bc.png)

---

### 2. Revenue Performance

- Discount and promo code users make up a larger share of revenue than subscribers do
    - Subscribers: **33%** of revenue share
    - Discount users: **45%** of revenue share
    - Promo code users: **44%** of revenue share
- These results indicate a discrepancy between the subscription program and discounts/promo codes driven by volume vs quality
    - Discounts and promo codes making up a larger percentage of revenue can be attributed to the way it increase sales volume indicated by their insignificant AOV numbers
    - Subscription program seems to produce less spending volume but higher quality spending indicated by its higher AOV number
- Revenue is dominated by two product categories: Clothing & Accessories
    - Clothing dominates all making up **44%** of total revenue at **$139,997**
- Revenue is dominated by ages between 26 and 45, (income earners and family builders), making up **53%** of total revenue

![revbysubstatus.jpg](revbysubstatus.jpg)

![revbydiscount.jpg](revbydiscount.jpg)

![revbypromocode.jpg](revbypromocode.jpg)

---

### 3. Customer Behavior and Segmentation

**Demographic Behavior**

*Age*

- Ages between 26-45 dominate both **AOV** and **Revenue**
    - ages 26-45 making up **53%** of total revenue
    - ages 26-45 are the only age group with an **AOV** greater than $100

*Gender*

- Male **AOV ($104.35)** vs. Female **AOV ($85.87)**
- **Revenue** dominated by male customers **(68% of total revenue)**
- Male customers > Female customers

**Category-level Behavior**

- Clothing and Accessories are the strongest revenue drivers
    - Clothing: **44%** of total revenue
    - Accessories: **26%** of total revenue
- Footwear has the highest **AOV ($125.81)**
- We can infer that clothing and accessories are the high volume, revenue stabilizing, and customer popular categories and footwear is a more premium, higher value product that customers buy less of

![revebyagegroup.jpg](a555801a-75e6-4822-b731-2020a45df643.png)

![revbygender.jpg](92acaa55-7225-4639-9017-4d59460f0a4b.png)

![revenueby category.jpg](487bbe8f-2fbb-4235-a4d4-2395935dbfcb.png)

![aovbycategory.jpg](967ab41f-cb79-454d-ac85-e1a81751bf52.png)

---

### 4. Customer Value Drivers Summary

**What drives high CLV?**

- Subscription status is bar far the most important driver as subscribers have a **CLV** of nearly double non-subscribers
- Promo code and Discount users also reveal strong **CLV**

**What drives high AOV?**

- Subscription status boosts **AOV, $123** to **$91**
- Promo codes and Discounts not nearly as effective and results were quite similar to customers that didn’t use them

**What drives revenue volume?**

- We see healthy revenue ratios for subscribers, promo code users, and discount users
- Ages 26-45 are by far the greatest revenue drivers among all age groups
- Clothing and accessories are the greatest revenue drivers among category of products sold

---

## Recommendations

---

**Based on the uncovered insights, here are actionable items that the Business Strategy team can take away from my analysis.** 

### 1. Expand and optimize the Subscription Program

The subscription program has been the highly successful and the most powerful profitability driver as it has contributed to **higher AOV, higher CLV, and high quality revenue.** Great news, however, there is still room for optimization. The subscription program lacks in areas surrounding revenue, evident in the contrast between subscriber revenue share and promo code/discount revenue shares. We want to transfer the volume of sales from promo codes/discount to subscribers and this can be done by **converting promo code/discount users to subscribers. Direct marketing campaigns (emails, texts, etc.) to convert frequent promo code and discount users to subscribe.** We recommend additional research to establish the best strategy for subscriber conversion. 

### 2. Support High-Value & High-Volume

The insights reveal product categories that excel in **AOV** and others in **revenue.** We want to stabilize the strong revenue accumulation from our high-volume categories (clothing & accessories) and push to maximize high-value categories (footwear) at the same time. A **cross-category** strategy that bundles footwear on top of clothing and accessories items may push footwear sells. **Clothing → suggest complementary footwear. Accessories → suggest complementary footwear.** We may also leverage the high **AOV** of subscribers and can bundle footwear promotions for subscribers. Ex: “points for footwear purchases” or “special prices for footwear.” Again, we recommend additional research to establish the best strategy for supporting high-value and high-volume. 

### 3. Leverage High-Value Segments

This recommendation is crucial and acts as a preliminary step to the recommendations above. The insights reveal this high-value customer segment: males ages 26-45. We can leverage our high volume categories (promo codes, discount, clothing and accessory promotions) and maximize margins, improve **AOV**, and support conversion into subscribers. 

---

## Notes and Caveats

---

**Throughout the analysis some data design choices were made to manage challenges with the data. They are noted below:**

- Sample size and data limitations: this analysis utilized data from the past 3 months and this posed challenges in repeat purchase rate results, purchase frequency, and lack of a time dimension. As a result purchase frequency was determined on a qualitative basis, broken up into weekly, bi-weekly, quarterly, monthly, and annual buyers. The KPIs that relied on this purchase frequency dimension was established on this.
- No time-based trends: data represents a single purchase aligned with a customer id to the purchase, limiting analysis on visualizing pattern changes over time