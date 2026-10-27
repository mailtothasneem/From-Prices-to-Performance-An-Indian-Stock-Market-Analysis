# Stock Market Analysis

Exploratory analysis of historical stock market data using Python, statistical tests, and visualizations. The project examines price movements and daily returns across multiple ticker symbols, then summarizes patterns in charts and statistical results.

> **Scope:** This is a historical data analysis project for learning and demonstration. It is not investment advice, a trading strategy, or a forecast of future prices.

## Project Overview

Stock prices change over time and can behave differently across companies. This project explores a cleaned, combined stock dataset to understand price trends, daily return distributions, and whether observed return categories differ by ticker.

The analysis focuses on six ticker symbols. The project discussion and charts include examples such as **ADANIPORTS**, **MUNDRAPORT**, and **RELIANCE**. Confirm the complete ticker list against the notebook or dataset before publishing a final project version.

## Objectives

- Explore the structure, quality, and key fields in the cleaned stock dataset.
- Compare closing-price trends over time across ticker symbols.
- Calculate and inspect daily returns.
- Compare return distributions and positive-return proportions by ticker.
- Use statistical tests to assess whether ticker and return category are associated.
- Present results with clear, interpretable visualizations.

## Dataset

The analysis uses a cleaned combined CSV file discussed in the project as `stock_market_combined (1).csv`.

The dataset represents historical market observations for multiple listed companies. The analyses discussed use date, ticker symbol, and closing-price information; depending on the source file, additional daily price and trading fields may also be available.

| Item | Description |
|---|---|
| File used in project discussion | `stock_market_combined (1).csv` |
| Data type | Historical stock market observations |
| Main analysis fields | Date, ticker symbol, closing price |
| Derived measure | Daily return |
| Number of tickers analyzed | 6 |

**Dataset source:** Add the original download/source URL and any license or attribution requirements here. The source link was not available in the project files provided for this README.

### Data preparation

The analysis uses a cleaned dataset. Before sharing the project, document the exact cleaning steps from the notebook, such as how missing values, duplicates, date types, ticker names, and invalid prices were handled. Do not claim a cleaning step unless it appears in the notebook.

## Analysis and Methodology

1. **Load and inspect the data**  
   Read the CSV and review its dimensions, columns, data types, summary statistics, missing values, and duplicate rows.

2. **Prepare time-series fields**  
   Convert the date field to a date/time type, sort observations by ticker and date, and verify that prices are valid before calculating returns.

3. **Calculate daily returns**  
   Daily simple return is calculated as:

 - Daily Return (%) = ((Today’s Closing Price − Previous Day’s Closing Price) ÷ Previous Day’s Closing Price) × 100

**Example:** If yesterday’s closing price was ₹100 and today’s is ₹105:

- Daily Return = ((₹105 − ₹100) ÷ ₹100) × 100 = 5%

   Returns should be calculated separately for each ticker after sorting by date. The first observation for each ticker has no previous close and therefore has no daily return.

4. **Explore and visualize**  
   Compare historical closing prices, return distributions, and the share of positive versus zero-or-negative daily returns.

5. **Perform statistical checks**  
   Use a chi-square test of independence to check whether ticker and return category are associated. Interpret the p-value alongside the test statistic and degrees of freedom.

## Visualizations

The project work discussed these visualizations:

- **Closing price over time:** compares historical closing prices for each ticker. Price charts show nominal price levels, not percentage investment performance. Sudden movements should be checked for corporate actions, changes in data coverage, or data issues.
- **Daily return distribution:** compares the spread of daily percentage returns by ticker. Values concentrated near 0% indicate that most observed daily changes were relatively small; extreme values should be investigated.
- **Return categories by ticker:** a 100% stacked bar chart compares the percentage of positive and zero-or-negative daily returns for each ticker. Each bar totals 100%, so it compares proportions rather than counts.
- **Optional interactive chart:** if the notebook contains Plotly charts, describe the available hover, zoom, and filtering controls here.

## Key Findings

- The closing-price charts show that prices fluctuate over time and that trends vary between tickers. A sharp drop visible for MUNDRAPORT around 2010 should be validated against the source data and any relevant corporate actions before drawing conclusions.
- The stacked return-category chart showed broadly similar positive and zero-or-negative proportions across the tickers discussed, generally around 48–52% positive days in the displayed analysis.
- The chi-square test returned **χ² = 6.707**, **5 degrees of freedom**, and **p = 0.243**. At a 0.05 significance level, this result does not provide statistically significant evidence of an association between ticker and return category in this dataset.
- These findings describe the observed sample only. They do not establish causation, predict future returns, or show that any ticker is a better investment.

## Tools and Technologies

- **Python** for analysis
- **Pandas** and **NumPy** for data preparation and calculations
- **Matplotlib** and **Seaborn** for charts
- **Plotly** for interactive visualizations, if used in the notebook
- **SciPy** for statistical testing, if used in the notebook
- ** Google Colab** as the analysis environment, depending on where the notebook is stored
- **Power BI** for a dashboard.


## Repository Contents


```text
stock-market-analysis/
├── README.md
├── stock_market_combined.csv       # cleaned dataset, if redistribution is permitted
├── notebooks/
│   └── stock_market_analysis.ipynb # analysis notebook
├── images/
│   └── ...                         # exported charts or dashboard screenshots
└── requirements.txt                # optional dependency list
```

## Getting Started

### Requirements

Python 3.9 or later is recommended. The exact minimum Python version and package versions should match the environment used by the notebook.

### Setup

1. Clone or download the repository.
2. Place the dataset in the location expected by the notebook, or update the notebook's file path.
3. Install the packages used by the project:

```bash
python -m pip install pandas numpy matplotlib seaborn scipy plotly jupyter
```

4. Open and run the notebook:

```bash
jupyter notebook
```

If using Google Colab, upload the dataset or mount the appropriate Drive folder, then update the notebook's data path.


## Limitations

- Historical price and return patterns do not guarantee future performance.
- The chi-square result depends on the selected return categories, observations, and assumptions of the test.
- Grouping all returns at or below zero into one category discards information about the size of gains and losses.
- The discussed analysis does not account for transaction costs, dividends, risk-adjusted performance, or a complete investment benchmark comparison.
- Extreme price movements may reflect data errors, corporate actions, or genuine market events; they require verification.
- Statistical association does not imply causation.

## Future Improvements

- Add adjusted-close prices and validate corporate actions.
- Compare cumulative returns and volatility, using a consistent date range.
- Add benchmark comparisons and risk measures where appropriate.
- Include confidence intervals or additional robustness checks for statistical comparisons.
- Add automated validation for missing values, duplicate dates, and price anomalies.
- Export polished figures and include them in the repository.

## Author

**Author:** L.Thasneem 
**Course / Program:** AI Driven Data Analytics
**Contact:** mailtothasneem16@gmail.com



---


