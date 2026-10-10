# Project 2 — Exploratory Data Analysis (EDA)

## Task 1 — Project Purpose

Task 1 establishes the purpose and starting point of Project 2.

Project 2 follows Project 1 and uses the cleaned and validated dataset to begin exploring what the data is telling us.

### Completed Work

The notebook `exploratory_data_analysis.ipynb`:

- Loads the cleaned dataset from `data/input/cleaned_dataset.xlsx`
- Displays the first records
- Confirms the dataset contains 1,200 records and 14 columns
- Records that the dataset has already been cleaned and validated in Project 1

### Current Result

The cleaned Project 1 dataset is established as the input for the EDA.

## Task 2 — Descriptive Statistics

Task 2 focuses on understanding the numerical variables using basic descriptive statistics and distribution analysis.

### Completed Work

The notebook:

- Calculates count, mean, and median for the numerical fields
- Produces a five-number summary using minimum, Q1, median, Q3, and maximum
- Creates distribution charts for `Quantity`, `UnitPrice`, `ItemsInCart`, and `TotalPrice`
- Calculates skewness to support the interpretation of distribution shape
- Compares mean and median and calculates the difference and percentage gap
- Records the main observations from the descriptive analysis

### Current Result

All four numerical variables contain 1,200 observations.

For `TotalPrice`, the mean is **1053.97**, the median is **823.62**, and skewness is **0.89**. This supports the observation that higher-value orders pull the average upward.

## Task 3 — Trends and Outliers

Task 3 focuses on identifying trends and investigating unusual observations using the IQR and Z-score methods.

### Completed Work

The notebook:

- Confirms the date range used for trend analysis
- Creates monthly summaries of order count and total sales
- Visualizes monthly order activity and monthly total sales
- Calculates highest and lowest order months and sales months
- Calculates month-to-month percentage changes and sales per order
- Uses the IQR method to identify potential outliers
- Reviews the records flagged by IQR
- Checks whether flagged `TotalPrice` values match `Quantity × UnitPrice`
- Compares flagged records with the full dataset
- Uses Z-scores to identify more extreme observations
- Compares the IQR and Z-score results
- Records how the unusual observations will be handled

### Current Result

Monthly order activity and total sales fluctuate from January 2023 to June 2025.

June 2024 had the highest order count (**53**) and highest monthly total sales (**68,068.54**). January 2025 had the lowest monthly order count (**27**), while April 2023 had the lowest monthly total sales (**27,751.71**).

The IQR method identified **8** potential outliers in `TotalPrice`, representing **0.67%** of the dataset. No IQR outliers were found for `Quantity`, `UnitPrice`, or `ItemsInCart`.

The eight flagged records matched the expected `Quantity × UnitPrice` calculation. The Z-score method identified no outliers using the threshold of 3; the IQR-flagged `TotalPrice` records had Z-scores between **2.78 and 2.93**.

The eight records are retained for the remaining analysis because the investigation did not find evidence of a calculation or pricing inconsistency.

## Task 4 — Relationships and Correlation

Task 4 examines the direction and strength of linear relationships between `Quantity`, `UnitPrice`, `ItemsInCart`, and `TotalPrice`.

### Completed Work

The notebook:

- Calculates the Pearson correlation matrix for the four numerical variables
- Lists the six unique variable pairs and sorts them by absolute correlation
- Adds plain-language labels for correlation strength and direction
- Creates a correlation heatmap
- Creates scatter plots for `UnitPrice` vs `TotalPrice`, `Quantity` vs `TotalPrice`, and `ItemsInCart` vs `TotalPrice`
- Runs Pearson correlation tests and labels results at a 5% significance level
- Checks recorded `TotalPrice` against `Quantity × UnitPrice`
- Compares the correlations using all records and a temporary dataset excluding the eight high-value `TotalPrice` records
- Documents the limitations of correlation and the difference between association and causation

### Current Result

The main Pearson correlations are:

| Variable pair              | Pearson correlation | Result at 5% level            |
| -------------------------- | ------------------: | ----------------------------- |
| UnitPrice and TotalPrice   |           **0.717** | Statistically significant     |
| Quantity and ItemsInCart   |           **0.650** | Statistically significant     |
| Quantity and TotalPrice    |           **0.615** | Statistically significant     |
| ItemsInCart and TotalPrice |           **0.393** | Statistically significant     |
| Quantity and UnitPrice     |           **0.015** | Not statistically significant |
| UnitPrice and ItemsInCart  |           **0.001** | Not statistically significant |

The strongest correlation is between `UnitPrice` and `TotalPrice` (**0.717**). However, `TotalPrice` is calculated from `Quantity × UnitPrice`, so this relationship is partly expected from the way the field is constructed.

The sensitivity check showed only small changes when the eight high-value `TotalPrice` records were temporarily excluded. For example, the `UnitPrice`–`TotalPrice` correlation changed from **0.717** to **0.712**, and the `Quantity`–`TotalPrice` correlation changed from **0.615** to **0.608**.

All 1,200 records matched `Quantity × UnitPrice` after rounding to two decimal places. The two near-zero correlations were not statistically significant at the 5% level.

These results describe associations in this dataset. Correlation does not establish causation, and Pearson correlation measures linear relationships rather than every possible kind of relationship.

## Task 5 — Visual Evidence

Task 5 reviewed the existing charts and improved selected visuals so that the evidence is easier to read and interpret.

### Completed Work

The notebook:

- Reviewed the 14 original charts for purpose, readability, labels, and potential interpretation issues.
- Created a chart review table and prioritised presentation improvements.
- Improved the monthly total sales chart by reducing date-label crowding, formatting the sales axis, and highlighting the highest-sales month.
- Created a separately saved review version of the `UnitPrice` versus `TotalPrice` scatter plot while preserving the original chart.
- Created a separately saved review version of the `TotalPrice` boxplot with the upper IQR limit marked.
- Checked an inventory of 16 expected chart files, including the original charts and two separately saved review visuals.

### Current Result

The final chart inventory check recorded **16 expected chart files, 16 files found, and 0 files missing**.

The revised TotalPrice boxplot still identifies **8 IQR-flagged values** among 1,200 records. These records remain included because an IQR flag alone does not prove a data error.

The UnitPrice–TotalPrice scatter plot is interpreted carefully because `TotalPrice` is calculated from `Quantity × UnitPrice`. The visual describes the observed relationship and is not presented as evidence of causation.

The monthly sales chart highlights June 2024, which had the highest monthly total sales (**68,068.54**) in the earlier analysis. The chart uses dataset units rather than assuming a specific currency.

## Task 7 — Business Impact and Recommendations

Task 7 translates the earlier EDA findings into possible business uses and practical next steps.

### Completed Work

The notebook:

- Compares the highest and lowest monthly sales and order counts and compares these with monthly averages.
- Summarises mean and median transaction values.
- Reuses the Pearson correlation and outlier sensitivity results from Task 4.
- Creates business-implication, recommendation, measurement-plan, and evidence-to-action tables.
- Identifies additional information needed before implementing recommendations.
- Records limitations, including the lack of confirmed currency, profit/cost data, operational context, and causal evidence.

### Current Result

- June 2024 had the highest monthly sales (**68,068.54**) and order count (**53**).
- January 2025 had the lowest monthly order count (**27**); April 2023 had the lowest monthly sales (**27,751.71**).
- Mean `TotalPrice` was **1,053.97**, compared with a median of **823.62**.
- `ItemsInCart` and `TotalPrice` had a Pearson correlation of **0.393**. This is an association and does not show that increasing basket size will cause sales or profit to rise.
- Eight `TotalPrice` records (**0.67%**) were flagged by IQR. Their calculations matched `Quantity × UnitPrice` to two decimal places, so they remain included based on the checks performed.

### Recommendations Recorded

1. Review monthly sales and order counts together, and compare them with operational records where available.
2. Monitor mean and median transaction values over comparable periods.
3. Investigate basket-level data before testing actions intended to affect transaction value.
4. Verify unusual transactions against source records rather than removing them automatically.

The recommendations are evidence-informed suggestions, not guaranteed business outcomes. Additional operational data and measured results are needed to determine their effectiveness.

## Current Status

- **Task 1 — Project Purpose: Completed**
- **Task 2 — Descriptive Statistics: Completed**
- **Task 3 — Trends and Outliers: Completed**
- **Task 4 — Relationships and Correlation: Completed**
- **Task 5 — Visual Evidence: Completed**
- **Task 6 — Analytical Insights: Completed**
- **Task 7 — Business Impact and Recommendations: Completed**

The completed work should be reviewed and committed before beginning the next task.

## Task 8 — Final Presentation and Quality

Task 8 focuses on presenting the complete EDA as a clear problem → investigation → evidence → insight story and checking that the notebook and supporting files are ready to share.

### Completed Work

The notebook:

- Adds a final explanation of the analysis story and the scope of the review.
- Checks that the input file exists and the dataset contains 1,200 records and 14 columns.
- Checks the required analysis columns, missing values, and duplicate rows.
- Recalculates `TotalPrice` from `Quantity × UnitPrice` and checks for mismatches.
- Checks the monthly summary used in the trend analysis.
- Checks for the 16 expected chart files.
- Combines the results into a final quality-check table.

### Current Result

The latest saved notebook outputs show all 12 quality checks passing: the input dataset and expected structure are present, required columns are available, no missing values or duplicate rows were detected, all 1,200 total-price calculations match after rounding, monthly summary checks pass, and all 16 chart files are found.

This is a check of the saved notebook outputs. A fresh kernel restart and full run of every cell remains the final execution test before submission.

### Final Presentation Notes

- Keep the charts, labels, and explanations understandable for non-technical readers.
- Retain the eight IQR-flagged `TotalPrice` records unless source-level evidence shows an error.
- Describe correlation as association, not causation.
- Do not assume a currency or claim profit, savings, or revenue impact without supporting data.
- Keep `README.md`, `SUMMARY.md`, `CHANGE_LOG.md`, and `requirements.txt` alongside the notebook and input data.

## Final Status

Tasks 1–8 are documented. The final outstanding verification is a clean-kernel run of the notebook, followed by saving the successful run and committing the final project files.
