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

The first two tasks established the purpose of the EDA and examined the numerical fields using descriptive statistics, distribution analysis, and mean-versus-median comparisons.

## Tools Used

- Python
- Pandas
- Jupyter Notebook
- Matplotlib
- Seaborn

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
│   └── 04_total_price_distribution.png
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

This histogram shows how many items were purchased per order. The values are concentrated within the small range of 1 to 5, with the distribution staying fairly balanced around the typical quantity.

### 2. Unit Price Distribution

![Unit Price Distribution](images/02_unit_price_distribution.png)

This chart shows the spread of unit prices across the orders. The values cover a wide price range, while the mean and median remain quite close to each other.

### 3. Items in Cart Distribution

![Items in Cart Distribution](images/03_items_in_cart_distribution.png)

This histogram shows the number of items in a customer's cart for each order. Most observations are centred around the middle of the 1 to 10 range, with a little more variation than Quantity.

### 4. Total Price Distribution

![Total Price Distribution](images/04_total_price_distribution.png)

This chart shows the distribution of total order values. The mean is higher than the median, which indicates that some higher-value orders are pulling the average upward.

## Final Output

The final notebook will contain the completed exploratory analysis, visual evidence, key observations, and conclusions from the dataset.

### Current Progress

**Task 1 — Project Purpose: Completed**

The cleaned dataset from Project 1 has been loaded successfully and confirmed as the starting point for the EDA. The dataset contains 1,200 records and 14 columns.

**Task 2 — Descriptive Statistics: Completed**

The numerical fields were analyzed using count, mean, median, and the five-number summary. Distribution charts were created for Quantity, UnitPrice, ItemsInCart, and TotalPrice, and skewness was used to support the distribution analysis.

The comparison between mean and median showed that `TotalPrice` has the largest gap. Its mean is 1053.97 compared with a median of 823.62, while the other variables have much smaller differences.

The remaining parts of Project 2 will be added separately as each task is completed and verified.

## Internship

**Program:** Data Analytics Internship  
**Organization:** DecodeLabs  
**Project:** Project 2 — Exploratory Data Analysis (EDA)
