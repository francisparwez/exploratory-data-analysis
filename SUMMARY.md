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

## Current Status

- **Task 1 — Completed**
- **Task 2 — Completed**
- **Task 3 — Completed**
- **Task 4 — Completed**

The next task will be added only after the completed work so far has been documented and committed.
