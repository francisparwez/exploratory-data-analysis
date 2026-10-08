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

The cleaned Project 1 dataset is now established as the input for the EDA.

No descriptive statistics, trend analysis, outlier analysis, correlation analysis, or business insight work was included in the Task 1 section.

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

`Quantity` and `UnitPrice` have mean and median values that are very close to each other. `ItemsInCart` shows a larger difference, while `TotalPrice` has the largest mean-versus-median gap.

For `TotalPrice`, the mean is **1053.97** and the median is **823.62**. The skewness value is **0.89**, supporting the observation that higher-value orders are influencing the average.

## Task 3 — Trends and Outliers

Task 3 focuses on identifying important trends and investigating unusual observations using the IQR and Z-score methods.

### Completed Work

The notebook:

- Confirms the date range used for the trend analysis
- Creates a monthly summary of order count and total sales
- Visualizes monthly order activity
- Visualizes monthly total sales
- Calculates the highest and lowest order months
- Calculates the highest and lowest sales months
- Calculates month-to-month percentage changes
- Calculates sales per order
- Uses the IQR method to identify potential outliers
- Reviews the actual records flagged by the IQR method
- Checks whether the flagged `TotalPrice` values match `Quantity × UnitPrice`
- Compares the flagged records with the full dataset
- Uses Z-scores to identify more extreme observations
- Compares the IQR and Z-score results
- Records the decision on how the unusual observations will be handled

### Current Result

Monthly order activity and total sales fluctuate across the period from January 2023 to June 2025.

June 2024 had the highest number of orders at **53** and the highest monthly total sales at **68,068.54**. January 2025 had the lowest order count at **27**, while April 2023 had the lowest monthly total sales at **27,751.71**.

The IQR method identified **8** potential outliers in `TotalPrice`, representing **0.67%** of the dataset. No IQR outliers were found for `Quantity`, `UnitPrice`, or `ItemsInCart`.

The eight `TotalPrice` records were investigated further. Their recorded total prices matched the expected `Quantity × UnitPrice` calculation, and no pricing inconsistency was found.

The Z-score method identified **0** outliers using the threshold of 3. The eight records flagged by IQR had TotalPrice Z-scores between **2.78 and 2.93**.

Based on these checks, the eight unusual records will be retained for the remaining analysis because they appear to be high-value transactions rather than obvious calculation errors.

## Current Status

**Task 1 — Completed**

**Task 2 — Completed**

**Task 3 — Completed**

The next task will be added only after the completed work so far has been documented and committed.
