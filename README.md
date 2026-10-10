# Project 2 — Exploratory Data Analysis (EDA)

This is Project 2 of my Data Analytics Internship at DecodeLabs.

Project 1 was about cleaning and validating the dataset. In this project, I use that cleaned dataset to explore patterns, trends, distributions, unusual observations, and relationships between variables.

The project is organised into tasks, with each stage reviewed before moving to the next one. Tasks 1–8 are documented in the notebook and project files. Task 8 adds final quality checks and presentation guidance.

## What I Will Explore

- Basic descriptive statistics such as count, mean, median, and the five-number summary
- The shape and distribution of numerical variables
- Differences between mean and median
- Monthly trends in order activity and total sales
- Potential outliers using IQR and Z-score methods
- Relationships between numerical variables using Pearson correlation
- Visualizations that help explain the findings
- Key observations and their meaning in context
- Evidence-based business recommendations and ways to measure them

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
│   ├── 14_itemsincart_vs_totalprice.png
│   ├── 15_unitprice_vs_totalprice_review.png
│   └── 16_totalprice_boxplot_review.png
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

## Visual Evidence — Task 5

Task 5 reviewed the existing visuals and made targeted improvements rather than adding charts without a clear purpose.

### Improvements made

- Updated `06_monthly_total_sales_trend.png` with less crowded date labels, clearer sales-axis formatting, and an annotation for the highest-sales month.
- Added `15_unitprice_vs_totalprice_review.png` as a clearer review version of the scatter plot. The original chart is preserved.
- Added `16_totalprice_boxplot_review.png` with the upper IQR limit marked. The eight flagged `TotalPrice` observations remain in the analysis.
- Checked the inventory of 16 expected chart files. The notebook's recorded check found all 16 files and no missing files.

### How the visuals support the analysis

- Distribution charts show how the numerical values are spread.
- Monthly trend charts show changes in order activity and sales over time.
- Boxplots help identify unusual observations for further investigation.
- The heatmap and scatter plots show linear associations between numerical variables.

The relationship between `UnitPrice` and `TotalPrice` needs particular care because `TotalPrice` is calculated as `Quantity × UnitPrice`. Correlation describes association and does not establish causation. The currency is not labelled as a specific currency because it has not been confirmed by the available dataset documentation.

## Task 7 — Business Impact and Recommendations

Task 7 connects the exploratory findings to practical business questions and possible actions. The recommendations are suggestions for follow-up, not claims that a particular action will guarantee better results.

### Main findings and possible business uses

- **Monthly performance varies.** June 2024 recorded the highest monthly sales (68,068.54) and highest order count (53). January 2025 had the lowest order count (27), while April 2023 had the lowest monthly sales (27,751.71). Reviewing monthly sales and order counts together may help with operational planning, but the dataset does not explain the causes of the changes.
- **The mean transaction value is higher than the median.** Mean `TotalPrice` was 1,053.97 and median `TotalPrice` was 823.62. Tracking both measures can give a more complete view of transaction values.
- **Basket size may warrant further investigation.** `ItemsInCart` and `TotalPrice` had a Pearson correlation of 0.393. This is an association, not proof that increasing basket size will increase sales or profit.
- **Unusual transactions were investigated.** Eight `TotalPrice` records (0.67% of the dataset) were flagged by the IQR method. Their totals matched `Quantity × UnitPrice` to two decimal places, so they remain included unless additional evidence identifies an error.

### Recommendations

1. Review monthly sales and order counts together, and compare them with operational information such as staffing and stock records where available.
2. Monitor mean and median transaction values across comparable periods.
3. Investigate basket-level data before testing any changes intended to affect transaction value.
4. Verify unusual transactions against source records when available rather than removing them solely because they are statistical outliers.

The dataset does not confirm a currency or provide enough information to calculate profit impact, cost savings, or additional revenue. Recommendations should therefore be evaluated with further operational data and measured results.

## Current Progress

**Task 1 — Project Purpose: Completed**

Loaded the cleaned dataset from Project 1 and confirmed that it contains 1,200 records and 14 columns.

**Task 2 — Descriptive Statistics: Completed**

Calculated count, mean, median, five-number summaries, skewness, and mean-versus-median differences. Created distribution charts for the four numerical variables.

**Task 3 — Trends and Outliers: Completed**

Analysed monthly order activity and total sales from January 2023 to June 2025. The IQR method flagged eight `TotalPrice` records (0.67% of the dataset). Their calculated totals matched `Quantity × UnitPrice`; the Z-score method found no records beyond the threshold of 3. The eight records are retained for the remaining analysis.

**Task 4 — Relationships and Correlation: Completed**

Calculated Pearson correlations for all six unique variable pairs, created a heatmap and three scatter plots, tested statistical significance, checked the `TotalPrice` calculation, and compared correlations with and without the eight high-value `TotalPrice` records. The analysis treats correlation as association, not causation.

**Task 5 — Visual Evidence: Completed**

Reviewed the original charts and improved the monthly sales trend, `UnitPrice` versus `TotalPrice` scatter plot, and `TotalPrice` boxplot. The recorded inventory check found all 16 expected chart files. The eight IQR-flagged `TotalPrice` records remain included.

**Task 6 — Analytical Insights: Completed**

Consolidated the findings on monthly activity, transaction-value distribution, numerical relationships, and high-value transactions. The conclusions describe observed patterns and acknowledge that correlation does not establish causation.

**Task 7 — Business Impact and Recommendations: Completed**

Connected the findings to possible business uses and created evidence-to-action and measurement tables. Recommendations focus on reviewing monthly performance, monitoring mean and median transaction values, investigating basket-size patterns, and verifying unusual transactions. The proposed actions are not presented as guaranteed improvements; further operational data and measured results are needed to evaluate their impact.

## Task 8 — Final Presentation and Quality

The final stage brings the analysis together as a clear story: problem, investigation, evidence, insight, and possible next steps.

The notebook now includes quality checks for:

- The expected input dataset and its shape (1,200 records and 14 columns)
- Required analysis columns
- Missing values and duplicate rows
- The `TotalPrice = Quantity × UnitPrice` calculation
- The monthly summary used in the trend analysis
- The 16 expected chart files

The saved results from these checks show all checks passing. This confirms the recorded checks, but a fresh **Restart Kernel and Run All Cells** execution should also be completed before submission.

The final review keeps the findings in context: the eight IQR-flagged high `TotalPrice` records are not removed automatically, correlation is not treated as causation, and no currency or financial impact is assumed without supporting information.

## Final Project Status

Tasks 1–8 have been documented in the notebook and project files. The remaining submission check is to restart the notebook kernel, run every cell from the beginning, confirm there are no errors, and save the notebook.

## Internship

**Program:** Data Analytics Internship  
**Organization:** DecodeLabs  
**Project:** Project 2 — Exploratory Data Analysis (EDA)
