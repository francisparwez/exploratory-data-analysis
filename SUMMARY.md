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

## Current Status

**Task 1 — Completed**

**Task 2 — Completed**

The next task will be added only after the completed work so far has been documented and committed.
