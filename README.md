# Project 2 — Exploratory Data Analysis (EDA)

This is Project 2 of my Data Analytics Internship at DecodeLabs.

In Project 1, I cleaned and validated the dataset. This project uses that cleaned dataset to explore the data and understand its patterns, trends, distributions, unusual values, and relationships.

The main goal is not just to calculate numbers or create charts, but to use the analysis to find useful observations and understand what they mean.

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

I will first understand the data, then investigate the important variables and relationships, look for patterns and unusual observations, and finally explain the main findings in a way that is easy to understand.

Outliers will be investigated rather than automatically removed, since an unusual value can sometimes be a useful signal rather than a data error.

Correlation results will also be interpreted carefully because correlation does not mean causation.

## Tools Used

- Python
- Pandas
- Jupyter Notebook
- Matplotlib
- Seaborn

## Project Structure

```text
exploratory-data-analysis__eda/
│
├── data/
│   └── input/
│       └── cleaned_dataset.xlsx
│
├── notebooks/
│   └── 01_exploratory_data_analysis.ipynb
│
├── README.md
├── SUMMARY.md
├── CHANGE_LOG.md
├── requirements.txt
└── .gitignore
```

## Final Output

The final notebook will contain the completed exploratory analysis, visual evidence, key observations, and conclusions from the dataset.

The README will be updated after the analysis is completed with the main findings and final project results.

## Internship

**Program:** Data Analytics Internship  
**Organization:** DecodeLabs  
**Project:** Project 2 — Exploratory Data Analysis (EDA)
