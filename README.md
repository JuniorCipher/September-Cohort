# RETAIL SALES ANALYSIS
## Table of contents


### Project Overview

This data analysis project aims to provide insights performance of a etail landscape, capturing essential attributes that drive retail operations and customer interactions. It includes key details such as Transaction ID, Date, Customer ID, Gender, Age, Product Category, Quantity, Price per Unit, and Total Amount. These attributes enable a multifaceted exploration of sales trends, demographic influences, and purchasing behaviors.


### Data Source

The data for this project was sourced from Kaggle.
Dataset Name: Retail Sales Datasets 
Author/Creator: Mohammad Talib
License: CC0: Public Domain
Link: https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset?resource=download

**Overview**: This dataset is a snapshot of a fictional retail landscape, capturing essential attributes that drive retail operations and customer interactions. It includes key details such as Transaction ID, Date, Customer ID, Gender, Age, Product Category, Quantity, Price per Unit, and Total Amount. These attributes enable a multifaceted exploration of sales trends, demographic influences, and purchasing behaviors.

### Data Quality Assessment

After conducting a thorough data quality assessment, I confirmed the dataset was analysis-ready with no missing values, duplicates, or data type inconsistencies. This allowed me to focus directly on exploratory data analysis and visualization to answer key business questions.

### Tools

- Excel - Data cleaning
  - [Download here](https://microsoft.com)
- Power BI - Data Visualization & report


### Data Cleaning & Preparation

Before proceeding with visualization and analysis, I performed a comprehensive data quality assessment to ensure the reliability of my findings. The dataset was found to be remarkably clean, which allowed me to proceed directly to analysis.

**Methods used for assessment:**
- Checked for missing values in all columns
- Verified data types were appropriate for each field
- Identified and examined potential outliers
- Checked for duplicate entries
- Validated logical consistency (e.g., Quantity × Price per Unit = Total Amount)

**Findings:** The dataset required no cleaning operations, as it contained no missing values, no duplicates, and all data types were correctly formatted.

### Exploratory Data Analysis

To analyze a fictional retail company's sales data to uncover key business trends, understand customer purchasing behavior, and derive actionable insights to drive sales and marketing strategies.

**Key Business Questions this analysis will answer:**
- How does customer age and gender influence their purchasing behavior?
- Are there discernible patterns in sales across different time periods?
- Which product categories hold the highest appeal among customers?
- What are the relationships between age, spending, and product preferences?
- How do customers adapt their shopping habits during seasonal trends?
- Are there distinct purchasing behaviors based on the number of items bought per transaction?
- What insights can be gleaned from the distribution of product prices within each category?


### Data Analysis 

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

### Results


