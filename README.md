# Project 2 — Exploratory Data Analysis (EDA)

This is Project 2 of my Data Analytics Internship at DecodeLabs.

Project 1 was about cleaning and validating the dataset. In this project, I will use that cleaned and validated dataset to explore what the data is actually telling me by looking for patterns, trends, distributions, and useful observations.

The work is being completed step by step, starting with understanding the purpose of the EDA before moving into the analysis.

## What I Will Explore

- Basic descriptive statistics such as count, mean, median, and the five-number summary
- The shape and distribution of numerical variables
- Differences between mean and median
- Trends and patterns in the data
- Potential outliers using IQR and Z-score methods
- Relationships between variables using correlation analysis
- Visualizations that help explain the findings
- Key observations and the business meaning behind them
- Actionable recommendations where the analysis supports them

## Dataset

The starting point for this project is the cleaned dataset produced in Project 1.

The cleaned dataset contains 1,200 records and 14 columns and is stored in:

`data/input/cleaned_dataset.xlsx`

Using the cleaned dataset keeps this project focused on analysis rather than repeating the data-cleaning work from Project 1.

## Project Approach

The analysis will follow a simple process:

**Question → Exploration → Evidence → Insight**

The first three tasks established the purpose of the EDA, examined the numerical fields, and investigated trends and unusual observations.

## Tools Used

- Python
- Pandas
- Jupyter Notebook
- Matplotlib
- Seaborn
- SciPy

## Project Structure

```text
exploratory-data-analysis/
├── data
│   └── input
│       └── cleaned_dataset.xlsx
├── images
│   ├── 01_quantity_distribution.png
│   ├── 02_unit_price_distribution.png
│   ├── 03_items_in_cart_distribution.png
│   ├── 04_total_price_distribution.png
│   ├── 05_monthly_order_trend.png
│   ├── 06_monthly_total_sales_trend.png
│   ├── 07_boxplot_quantity.png
│   ├── 08_boxplot_unit_price.png
│   ├── 09_boxplot_items_in_cart.png
│   └── 10_boxplot_total_price.png
├── notebooks
│   └── exploratory_data_analysis.ipynb
├── CHANGE_LOG.md
├── README.md
├── requirements.txt
└── SUMMARY.md
```

## Descriptive Statistics — Chart Preview

### 1. Quantity Distribution

![Quantity Distribution](images/01_quantity_distribution.png)

This histogram shows how many items were purchased in each order. The values stay within a small range of 1 to 5.

### 2. Unit Price Distribution

![Unit Price Distribution](images/02_unit_price_distribution.png)

This chart shows the spread of unit prices across the orders. The mean and median are close, so the centre of the distribution is fairly stable.

### 3. Items in Cart Distribution

![Items in Cart Distribution](images/03_items_in_cart_distribution.png)

This histogram shows the number of items in the cart for each order and how the observations are spread across the 1 to 10 range.

### 4. Total Price Distribution

![Total Price Distribution](images/04_total_price_distribution.png)

This chart shows the distribution of total order values. The mean is higher than the median, which is consistent with some higher-value orders pulling the average upward.

## Trends and Outliers — Chart Preview

### 5. Monthly Order Trend

![Monthly Order Trend](images/05_monthly_order_trend.png)

This line chart shows monthly order activity from January 2023 to June 2025. The number of orders moves up and down across the period, with June 2024 recording the highest monthly order count at 53.

### 6. Monthly Total Sales Trend

![Monthly Total Sales Trend](images/06_monthly_total_sales_trend.png)

This chart shows how total monthly sales changed over the same period. Sales fluctuate noticeably, with the highest monthly total sales recorded in June 2024 at 68,068.54.

### 7. Quantity Boxplot

![Quantity Boxplot](images/07_boxplot_quantity.png)

The boxplot shows the spread of `Quantity`. The IQR method did not identify any potential outliers for this variable.

### 8. Unit Price Boxplot

![Unit Price Boxplot](images/08_boxplot_unit_price.png)

This boxplot shows the spread of `UnitPrice`. No potential outliers were identified using the IQR method.

### 9. Items in Cart Boxplot

![Items in Cart Boxplot](images/09_boxplot_items_in_cart.png)

This boxplot shows the spread of `ItemsInCart`. The IQR method did not flag any observations as potential outliers.

### 10. Total Price Boxplot

![Total Price Boxplot](images/10_boxplot_total_price.png)

The `TotalPrice` boxplot highlights the small number of unusually high-value orders identified by the IQR method. Eight records were flagged for further investigation.

## Final Output

The final notebook will contain the completed exploratory analysis, visual evidence, key observations, and conclusions from the dataset.

### Current Progress

**Task 1 — Project Purpose: Completed**

The cleaned dataset from Project 1 has been loaded successfully and confirmed as the starting point for the EDA. The dataset contains 1,200 records and 14 columns.

**Task 2 — Descriptive Statistics: Completed**

The numerical fields were analyzed using count, mean, median, and the five-number summary. Distribution charts were created for Quantity, UnitPrice, ItemsInCart, and TotalPrice, and skewness was used to support the distribution analysis.

The comparison between mean and median showed that `TotalPrice` has the largest gap. Its mean is 1053.97 compared with a median of 823.62, while the other variables have much smaller differences.

**Task 3 — Trends and Outliers: Completed**

Monthly order activity and total sales were analyzed from January 2023 to June 2025. June 2024 had the highest order count at 53 and the highest total sales at 68,068.54. January 2025 had the lowest monthly order count at 27, while April 2023 had the lowest monthly total sales at 27,751.71.

The IQR method identified eight potential outliers in `TotalPrice`, representing 0.67% of the dataset. No IQR outliers were found for Quantity, UnitPrice, or ItemsInCart. The eight high-value records were checked against the expected `Quantity × UnitPrice` calculation and all passed the check.

The Z-score method identified no observations above the threshold of 3. The IQR-identified TotalPrice records had Z-scores between 2.78 and 2.93, so they were unusual but not extreme under the Z-score rule.

The eight records will be retained for the remaining analysis because the investigation did not find evidence of a calculation or pricing inconsistency.

The remaining parts of Project 2 will be added separately as each task is completed and verified.

## Internship

**Program:** Data Analytics Internship  
**Organization:** DecodeLabs  
**Project:** Project 2 — Exploratory Data Analysis (EDA)
