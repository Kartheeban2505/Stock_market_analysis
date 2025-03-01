# Stock Analysis Dashboard

# Problem Overview
This project is a Stock Analysis Dashboard built using Power BI, designed to analyze stock market data and provide actionable insights. The dashboard helps track stock performance, volume trends, and price changes over time. The dataset used includes historical stock prices, trading volumes, and key financial indicators.

# Problem Statement
Financial analysts and investors often struggle with handling large datasets while analyzing stock performance. Manually tracking stock trends, price movements, and trading volumes can be time-consuming and inefficient. This project aims to simplify the process by creating an interactive Power BI dashboard that visualizes stock trends, compares performance across different stocks, and provides valuable insights through DAX calculations, ultimately helping users make data-driven investment decisions.

# Task List
1.**Data Cleaning & Preparation:** Loaded stock data from a CSV file into Power BI.Checked for missing values and handled date formatting.
2.**Data Modeling:** Created relationships between different data tables. Added calculated columns and measures using DAX.
3.**Dashboard Design & Visuals:** Created 7-8 interactive visuals in a one-page layout. Used slicers for Ticker Selection & Date Filtering. Applied conditional formatting for better readability.
4.**DAX Calculations Used:**
**% Change in Close Price**
Chan%ge in Close = 
VAR LatestDate = MAX('stocks'[Date])
VAR PreviousDate = CALCULATE(MAX('stocks'[Date]), 'stocks'[Date] < LatestDate)
VAR LatestClose = CALCULATE(MAX('stocks'[Close]), 'stocks'[Date] = LatestDate)
VAR PreviousClose = CALCULATE(MAX('stocks'[Close]), 'stocks'[Date] = PreviousDate)
RETURN DIVIDE((LatestClose - PreviousClose), PreviousClose, 0) * 100
**Average Trading Volume**
Avg Volume = AVERAGE('stocks'[Volume])
**Latest Close**
Latest Close = 
CALCULATE(MAX('stocks'[Close]),'stocks'[Date] = MAX('stocks'[Date]))

# Dashboard
![Screenshot 2025-02-28 175630](https://github.com/user-attachments/assets/2dcad2e2-869c-4106-9c73-fe9629a1d7d3)

# Things Learned
1. Data Transformation & Cleaning using Power Query.
2. Creating Relationships & Data Modeling in Power BI.
3. Advanced DAX Measures for custom calculations.
4. Dashboard Design Principles for better readability.
5. Interactivity with Filters & Slicers.
6. Optimizing Performance by reducing data load and improving calculations.
7. Using Conditional Formatting for better visualization.

# Key Insights from Dashboard
1. **Stock Prices Trend:** Price trends show fluctuations in major stocks, with peaks in March-April.
2. **Daily Trading Volume:** March had the highest trading activity (3.2B volume).
3. **Stock Performance Comparison:** MSFT and AAPL had higher trading volumes than others.
4. **Sector Contribution:** AAPL contributed the largest share in total volume.
5. **Drop in Volume in May:** A sharp decline in stock trading volume was observed in May, indicating a potential shift in market activity.
6. **Volatility in Adjusted Closing Price:** Stocks exhibited significant fluctuations, suggesting market instability in certain periods.
7. **Consistent Growth in Some Stocks:** Certain stocks showed a steady upward trend, making them strong investment options.
