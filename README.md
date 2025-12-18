# Sales Analysis | Global Electronics Retailer
*A data analysis project leveraging Python to uncover insights for retail sales optimization and customer retention strategies.*

#### Table of Contents
- [Project Background](#project-background)
- [Key Insights](#key-insights)
  - [I. Revenue Trends \& Performance](#i-revenue-trends--performance)
  - [II. Product Overview](#ii-product-overview)
  - [III. Customer Behavior](#iii-customer-behavior)
  - [IV. Geographic Performance](#iv-geographic-performance)
- [Strategic Questions for Further Analysis](#strategic-questions-for-further-analysis)
- [Notebooks](#notebooks)


## Project Background
This project analyzes transactional, customer, product, and store-level data for a fictitious global electronics retailer, examining five years of transaction data (2016-2021) to identify what drives revenue, where customers come from, product and category performance, and customer behavior. The analysis combines time series, product and category level aggregation, customer segmentation, and geographic breakdowns to surface actionable insights for strategic data-driven business decisions. The findings highlight revenue drivers, seasonal demand patterns, customer lifetime behavior, and regional strengths and weaknesses.

### Tools Used: 
```Python 3.13.2```:
 - ```Plotly```, ```NumPy```, ```pandas```

### Data Schema

The dataset is organized as a relational sales model with relationships following a star-schema, with Sales as the central fact table joined to Customers, Products, Stores, and Exchange Rates.

<img src="Static Charts/ERDiagram.png" width="50%"/>


Dataset source: https://mavenanalytics.io/data-playground/global-electronics-retailer




## Key Insights

### I. Revenue Trends & Performance

#### Recurring seasonal volatility:
The business exhibits a consistent seasonal pattern across all years, with **revenue declining sharply by 70-90% every March-April**, followed by dramatic recovery spikes of **up to 1,400% month-over-month growth in May**. This pattern reflects strong holiday and winter demand (November-February peaks) followed by a predictable spring slump and robust recovery.

While 2020 exhibited the typical March-April revenue decline, the expected May recovery and subsequent growth failed to materialize, likely due to sustained COVID-19 pandemic impacts on consumer demand and in-store traffic.

#### Pre-pandemic growth trajectory:

Prior to the COVID-19 pandemic disruption, the business showed strong expansion with **2018 revenue up 72.3%** and **2019 up 42.8%** year-over-year.
<br>
<br>
<img src="Static Charts/monthly_rev_time.png" width="55%"/>
<img src="Static Charts/mom_growth_rate.png" width="40%"/>
<br>
<br>

**Recommendations:**
- Capitalize on predictable spring slumps with targeted reactivation campaigns, limited-time offers, and flash sales to convert inactive customers in spring using email and social retargeting.

- Reduce in-store dependency by expanding online product discovery and improving digital customer experience.

---

### II. Product Overview

#### Concentration of revenue:

 A small set of products drive a large share of revenue. The top SKUs include **Adventure Works Desktop PC2.33 XD233** and **WWI Desktop PC2.33 X2330**, with the highest grossing SKU at **~$1.8M in profit**.

#### Category mix and margins:
- **Computers** account for the largest share of revenue at **34.6%**.

- **Home appliances** contribute **~19.4%**.

- **Games and toys** are a small portion at **~1.3%**.

- Some high-revenue categories (Desktops, Projectors, Water Heaters, Televisions) have **lower profit margins**, while lower-revenue categories (Coffee Machines, Microwaves, Monitors, Cameras) show **higher margins**.

<br>
<img src="Static Charts/top_products_treemap.png" width="60%"/>

*Click on the chart to view an interactive version of the visualization.*
<br>
<br>

**Recommendations:**
- Reduce dependence on top-performing desktop products through strategic expansion into adjacent categories and diversified product development.

- Increase penetration of high-margin categories through prominent placement, bundled offers, and targeted email campaigns to existing customers

- Expand promotion and cross-sell strategies within high-margin categories.
---

### III. Customer Behavior

#### Order frequency and value:
**Customers with 4+ orders** have a **40% higher median average order value (AOV)** than one-time buyers (**$768 vs $552**). However, one-time and occasional buyers show significant outliers (up to $22,400 and $13,400 AOV respectively), suggesting high-value bulk purchasers and possible B2B partnership opportunities.
<br>
<br>

<img src="Static Charts/segmented_aov.png" width="35%"/>

*Click on the chart to view an interactive version of the visualization.*
<br>
<br>

#### New vs. returning performance:

New customer acquisition follows seasonal patterns with December peaks but **remains stagnant following the March 2020 decline**. 
<br>

<img src="Static Charts/new_returning_time.png" width="50%"/>

*Click on the chart to view an interactive version of the visualization.*
<br>
<br>

#### Retention by channel and region:
- **United States** shows the highest retention at **61.2%** of users that make at least a second purchase.

- **Online** channel retention is low at **~19.2%**, indicating weaker repeat purchase behavior for online customers.

- **Canada** has moderate retention at **~46.3%** despite strong city-level revenue contributions.
<br>

<img src="Static Charts/retention_rate_region.png" width="45%"/>

<br>


**Recommendations:**
- Prioritize online retention through loyalty programs, personalized email automation, and post-purchase engagement.

- Target high-frequency customers with personalized promotions.

- Assess large one-time orders to determine if there are wholesale opportunites that could be converted into a B2B channel.

- Accelerate customer acquisition investment to recover pre-pandemic acquisition rates.

---

### IV. Geographic Performance

#### Regional revenue split:
- **United States** contributes the largest share at **~42.6%** of total revenue.

- **Online orders** are the second-largest revenue source at **~20.45%**.

- Other notable markets include the **United Kingdom, Germany, and Canada**.

#### City-level concentration:
 City-level analysis reveals **strong metropolitan clustering** with **Toronto leading at ~$600K**, followed by **New York (~$490K)** and **Los Angeles (~$470K)**. Notably, Canadian cities demonstrate exceptional urban penetration with Toronto, Montreal, Calgary, Ottawa, and Vancouver all ranking in top-performing cities despite Canada's smaller overall market size.

<img src="Static Charts/top_cities.png" width="45%"/>
<img src="Static Charts/total_rev_region.png" width="45%"/>
<br>
<br>

 **Recommendations:**
- Prioritize top-performing metropolitan markets through localized marketing and optimized fulfillment.

- Develop market-specific retention campaigns for high-revenue, low-retention regions to maximize customer lifetime value.


## Strategic Questions for Further Analysis
*Clarifying questions I would ask business stakeholders or database administrators to deepen findings:*

1. **Seasonal Anomaly:** What drives the extreme March-April revenue dip and subsequent May surge? Is this operational (inventory/sales cycles), industry-wide (electronics market seasonality), or company-specific (promotional calendar)?

2. **High-Value One-Time Buyers:** What characterizes customers with high order values who never return? Are these wholesale relationships, corporate bulk purchases, or retail customers? Could these represent untapped B2B channel opportunities?

3. **2020 Recovery Failure:** Why did the typical May recovery fail to materialize in 2020 despite occurring in prior years? Beyond pandemic disruption, were there supply chain, operational, or competitive factors that prevented the seasonal rebound?

## Notebooks
Full visualizations and source code available in Jupyter notebooks:

[Data Cleaning](data_cleaning.ipynb) | [Analysis](analysis.ipynb)