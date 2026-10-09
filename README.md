# Project 2 — Exploratory Data Analysis (EDA)

This is Project 2 of my Data Analytics Internship at DecodeLabs.

Project 1 was about cleaning and validating the dataset. In this project, I use that cleaned dataset to explore patterns, trends, distributions, unusual observations, and relationships between variables.

The work is being completed step by step, with each task reviewed before moving to the next one.

## What I Will Explore

- Basic descriptive statistics such as count, mean, median, and the five-number summary
- The shape and distribution of numerical variables
- Differences between mean and median
- Monthly trends in order activity and total sales
- Potential outliers using IQR and Z-score methods
- Relationships between numerical variables using Pearson correlation
- Visualizations that help explain the findings
- Key observations and their meaning in context
- Recommendations where the analysis supports them

## Dataset

The starting point is the cleaned dataset produced in Project 1.

- **Records:** 1,200
- **Columns:** 14
- **Input file:** `data/input/cleaned_dataset.xlsx`

Using the cleaned dataset keeps this project focused on analysis rather than repeating the data-cleaning work from Project 1.

## Project Approach

The analysis follows a simple process:

**Question → Exploration → Evidence → Insight**

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
├── data/
│   └── input/
│       └── cleaned_dataset.xlsx
├── images/
│   ├── 01_quantity_distribution.png
│   ├── 02_unit_price_distribution.png
│   ├── 03_items_in_cart_distribution.png
│   ├── 04_total_price_distribution.png
│   ├── 05_monthly_order_trend.png
│   ├── 06_monthly_total_sales_trend.png
│   ├── 07_boxplot_quantity.png
│   ├── 08_boxplot_unit_price.png
│   ├── 09_boxplot_items_in_cart.png
│   ├── 10_boxplot_total_price.png
│   ├── 11_correlation_heatmap.png
│   ├── 12_unitprice_vs_totalprice.png
│   ├── 13_quantity_vs_totalprice.png
│   └── 14_itemsincart_vs_totalprice.png
├── notebooks/
│   └── exploratory_data_analysis.ipynb
├── CHANGE_LOG.md
├── README.md
├── requirements.txt
└── SUMMARY.md
```

## Descriptive Statistics — Chart Preview

### 1. Quantity Distribution

![Quantity Distribution](images/01_quantity_distribution.png)

This histogram shows how many units were purchased in each order. The observed values range from 1 to 5.

### 2. Unit Price Distribution

![Unit Price Distribution](images/02_unit_price_distribution.png)

This chart shows the spread of unit prices. The mean and median are close, so the distribution is centred fairly evenly.

### 3. Items in Cart Distribution

![Items in Cart Distribution](images/03_items_in_cart_distribution.png)

This histogram shows how the number of items in the cart is distributed across the records.

### 4. Total Price Distribution

![Total Price Distribution](images/04_total_price_distribution.png)

The mean `TotalPrice` is higher than its median, which is consistent with higher-value orders pulling the average upward.

## Trends and Outliers — Chart Preview

### 5. Monthly Order Trend

![Monthly Order Trend](images/05_monthly_order_trend.png)

Monthly order activity fluctuates from January 2023 to June 2025. June 2024 recorded the highest monthly order count, at 53.

### 6. Monthly Total Sales Trend

![Monthly Total Sales Trend](images/06_monthly_total_sales_trend.png)

Monthly total sales fluctuate over the same period. June 2024 had the highest monthly total sales, at 68,068.54.

### 7. Quantity Boxplot

![Quantity Boxplot](images/07_boxplot_quantity.png)

The IQR method did not identify potential outliers in `Quantity`.

### 8. Unit Price Boxplot

![Unit Price Boxplot](images/08_boxplot_unit_price.png)

The IQR method did not identify potential outliers in `UnitPrice`.

### 9. Items in Cart Boxplot

![Items in Cart Boxplot](images/09_boxplot_items_in_cart.png)

The IQR method did not flag observations in `ItemsInCart`.

### 10. Total Price Boxplot

![Total Price Boxplot](images/10_boxplot_total_price.png)

The IQR method flagged eight unusually high `TotalPrice` records for further investigation.

## Relationships and Correlation — Chart Preview

Task 4 uses Pearson correlation to explore linear relationships between `Quantity`, `UnitPrice`, `ItemsInCart`, and `TotalPrice`.

### 11. Pearson Correlation Heatmap

![Pearson Correlation Heatmap](images/11_correlation_heatmap.png)

The heatmap compares the Pearson correlation values for the four numerical variables.

### 12. Unit Price vs Total Price

![UnitPrice vs TotalPrice](images/12_unitprice_vs_totalprice.png)

The correlation is approximately **0.717**, indicating a strong positive linear association. `TotalPrice` is calculated using `Quantity × UnitPrice`, so this relationship should be interpreted in the context of that formula.

### 13. Quantity vs Total Price

![Quantity vs TotalPrice](images/13_quantity_vs_totalprice.png)

The correlation is approximately **0.615**, indicating a positive linear association between quantity and total price.

### 14. Items in Cart vs Total Price

![ItemsInCart vs TotalPrice](images/14_itemsincart_vs_totalprice.png)

The correlation is approximately **0.393**, indicating a moderate positive linear association.

## Task 4 — Main Correlation Findings

Pearson correlation was calculated for all six unique pairs of numerical variables.

| Variable pair              | Pearson correlation | Interpretation                       |
| -------------------------- | ------------------: | ------------------------------------ |
| UnitPrice and TotalPrice   |               0.717 | Strong positive linear association   |
| Quantity and ItemsInCart   |               0.650 | Strong positive linear association   |
| Quantity and TotalPrice    |               0.615 | Strong positive linear association   |
| ItemsInCart and TotalPrice |               0.393 | Moderate positive linear association |
| Quantity and UnitPrice     |               0.015 | Little or no linear association      |
| UnitPrice and ItemsInCart  |               0.001 | Little or no linear association      |

The tests at the 5% significance level found statistically significant correlations for the four pairs with larger correlation values. The correlations between `Quantity` and `UnitPrice`, and between `UnitPrice` and `ItemsInCart`, were not statistically significant.

The eight high-value `TotalPrice` records identified in Task 3 were temporarily excluded for a sensitivity check. The correlation values changed only slightly, so the relationships were not heavily influenced by those records in this comparison.

The `TotalPrice` calculation was also checked against `Quantity × UnitPrice`. All 1,200 records matched after rounding to two decimal places.

**Correlation does not imply causation.** In particular, the relationship between `TotalPrice` and the variables used to calculate it is partly built into the dataset's formula. The results describe linear associations in this dataset and should not be treated as proof of cause and effect.

## Current Progress

**Task 1 — Project Purpose: Completed**

Loaded the cleaned dataset from Project 1 and confirmed that it contains 1,200 records and 14 columns.

**Task 2 — Descriptive Statistics: Completed**

Calculated count, mean, median, five-number summaries, skewness, and mean-versus-median differences. Created distribution charts for the four numerical variables.

**Task 3 — Trends and Outliers: Completed**

Analysed monthly order activity and total sales from January 2023 to June 2025. The IQR method flagged eight `TotalPrice` records (0.67% of the dataset). Their calculated totals matched `Quantity × UnitPrice`; the Z-score method found no records beyond the threshold of 3. The eight records are retained for the remaining analysis.

**Task 4 — Relationships and Correlation: Completed**

Calculated Pearson correlations for all six unique variable pairs, created a heatmap and three scatter plots, tested statistical significance, checked the `TotalPrice` calculation, and compared correlations with and without the eight high-value `TotalPrice` records. The analysis treats correlation as association, not causation.

## Internship

**Program:** Data Analytics Internship  
**Organization:** DecodeLabs  
**Project:** Project 2 — Exploratory Data Analysis (EDA)
