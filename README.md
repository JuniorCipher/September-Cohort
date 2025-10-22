# RETAIL SALES ANALYSIS

## Table of contents

- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Data Quality Assessment](#data-quality-assessment)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [Recommendation](#recommendation)
- [Limitations](#limitations)
- [Reference](#reference)

### Project Overview

This project focuses on analyzing a retail sales dataset to uncover meaningful insights into customer behavior, sales trends, and product performance. The dataset contains important information such as Transaction ID, Date, Customer ID, Gender, Age, Product Category, Quantity, Price per Unit, and Total Amount.

The main goal of this analysis is to identify patterns that can help improve sales strategies, understand demographic influences on purchasing behavior, and provide data-driven recommendations for business growth.

### Data Source

The data for this project was sourced from Kaggle.
**Dataset Name:** Retail Sales Datasets 
**Author/Creator:** Mohammad Talib
**License:** CC0: Public Domain
**Link:** https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset?resource=download

**Overview**: This dataset represents a fictional retail environment that captures various aspects of customer transactions and sales activities, enabling a broad exploration of retail operations and customer behavior.

### Data Quality Assessment

A thorough data quality assessment was carried out to ensure the dataset was suitable for analysis. During this process, I checked for missing values, duplicates, incorrect data types, and any logical inconsistencies.

The dataset was found to be clean - there were no missing or duplicate values, and all data types were correctly formatted. This allowed me to move directly to the analysis and visualization stages without any major cleaning operations.

### Tools

The analysis and visualization were performed using Power BI, which was used to explore the dataset, create calculated columns, and develop interactive dashboards for better insights.

### Data Cleaning and Preparation

Before proceeding with visualization and analysis, I performed a comprehensive data quality assessment to ensure the reliability of my findings. The dataset was found to be remarkably clean, which allowed me to proceed directly to analysis.

### **Methods used for assessment:**

Before analysis, I verified that the dataset met quality standards by:

- Checking for missing or duplicate records.

- Ensuring data types were correctly assigned.

- Confirming that calculations such as Quantity × Price per Unit = Total Amount were accurate.

- Identifying any possible outliers or unusual patterns.

- After review, the dataset was confirmed to be clean and analysis-ready.


### Exploratory Data Analysis

The EDA stage aimed to understand sales trends and customer purchasing behavior. I explored patterns such as:

- How customer age and gender affect buying decisions.

- Seasonal trends in sales performance.

- Which product categories generate the most revenue.

- Relationships between age, spending habits, and product preferences.

- Variations in purchasing behavior based on transaction size and frequency.

 This stage provided an overview of how customers interact with different products and time periods throughout the dataset.

**Key Business Questions this analysis will answer:**
- How does customer age and gender influence their purchasing behavior?
- Are there discernible patterns in sales across different time periods?
- Which product categories hold the highest appeal among customers?
- What are the relationships between age, spending, and product preferences?
- How do customers adapt their shopping habits during seasonal trends?
- Are there distinct purchasing behaviors based on the number of items bought per transaction?
- What insights can be gleaned from the distribution of product prices within each category?


### Data Analysis 

Several DAX formulas were used in Power BI to create calculated columns that enhanced the analysis.

1. Creating a Month Column
This converts the numeric month value into a short month name.

```Power Query
Month = 
SWITCH(
    TRUE(),
    MONTH([Date]) = 1, "Jan",
    MONTH([Date]) = 2, "Feb",
    MONTH([Date]) = 3, "Mar",
    MONTH([Date]) = 4, "Apr",
    MONTH([Date]) = 5, "May",
    MONTH([Date]) = 6, "Jun",
    MONTH([Date]) = 7, "Jul",
    MONTH([Date]) = 8, "Aug",
    MONTH([Date]) = 9, "Sep",
    MONTH([Date]) = 10, "Oct",
    MONTH([Date]) = 11, "Nov",
    MONTH([Date]) = 12, "Dec"
)
```

2. Categorizing Seasons Based on Month

```DAX Measures
Season = 
SWITCH(
    TRUE(),
    MONTH([Date]) >= 3 && MONTH([Date]) <= 5, "Spring",
    MONTH([Date]) >= 6 && MONTH([Date]) <= 8, "Summer",
    MONTH([Date]) >= 9 && MONTH([Date]) <= 11, "Autumn",
    MONTH([Date]) = 12 || MONTH([Date]) <= 2, "Winter"
)
```

3. Grouping Customers by Age Range

```
dax
AgeGroup = 
IF([Age] <= 25, "18-25",
    IF([Age] <= 35, "26-35",
        IF([Age] <= 45, "36-45",
            IF([Age] <= 55, "46-55", "56+")
        )
    )
)
```
These calculated columns helped me analyze seasonal trends, age-based purchasing behavior, and product performance throughout the dataset.

### Results

From my analysis, several key findings emerged:

- Beauty products recorded the highest revenue in 2024 due to their higher prices and strong customer demand.

- The 26–35 age group (Early Working Adults) made the most purchases in the Clothing category, reflecting their active lifestyle and fashion interest.

- The 46–55 age group (Mature Adults) generated a total of $101k in purchases, showing their higher purchasing power.

- The Winter season recorded the highest sales of $126k, likely due to increased demand for warm clothing and seasonal items.

- Across the dataset, the company sold 2,514 items, generating a total revenue of $456k over two years.

- The 18–25 and 56+ age groups had the lowest total spending, possibly due to lower income levels or fewer purchasing needs.

These results reveal that the company’s strongest customer base lies within the 26–55 age group, and that seasonal patterns - especially during winter play a major role in driving sales.

[Sales PORTFOLIO.pbix…]()

### Recommendation

Based on the insights obtained, I recommend the following actions:

- **Focus on High-Value Categories** – Prioritize marketing campaigns for Beauty and Clothing products to maximize revenue.

- **Target Working Adults (26–55)** – Create promotions and loyalty programs aimed at this high-spending group.

- **Leverage Seasonal Opportunities** – Increase inventory and marketing during the Winter season when sales are highest.

- **Engage Younger and Older Shoppers** – Introduce student and senior discounts to encourage more purchases among low-spending age groups.

- **Continue Data Monitoring** – Regularly update and analyze sales data to detect new trends and opportunities.

### Limitations

Although the dataset was clean and comprehensive, it represents fictional data and may not fully capture real-world market fluctuations. In addition, the dataset does not include customer location or payment method details, which could provide deeper insights into regional preferences and spending behavior.

### Reference

1. [Kaggle](https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset?resource=download)
[Talib, M. (n.d.). Retail Sales Dataset. Kaggle.
Retrieved from](https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset?resource=download)

