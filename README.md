WRDS Stock Risk Analysis Tool
1. Problem & User
This project addresses the inefficiency of manually calculating stock risk metrics in Excel, which is prone to errors and difficult to scale. It is designed for accounting and finance students who need a quick, automated way to assess the risk profile (volatility, Beta) of specific stocks using historical data.
2. Data
Source: Wharton Research Data Services (WRDS) - CRSP (Center for Research in Security Prices) database.
Access Date: January 1, 2015 to January 1, 2025
Key Fields:
permno: Unique CRSP permanent security identifier.
date: Trading date.
prc: Closing price (or bid/ask average).
ret: Total daily return.
vwretd: Value-weighted market return (used as the S&P 500 benchmark).
3. Methods
The analysis follows a structured Python workflow:
Connection: Securely connects to the WRDS cloud using the wrds library.
Data Extraction: Executes SQL queries to retrieve daily stock data (crsp.dsf) and market index data (crsp.dsi) for the specified period (2015-2025).
Data Cleaning: Handles missing values, standardizes date formats, and adjusts for negative prices (a CRSP convention for bid-ask averages) by taking absolute values.
Metric Calculation: Computes annualized volatility, Beta (Covariance/Variance), Maximum Drawdown, and Sharpe Ratio using pandas and numpy.
Visualization: Generates normalized price trend charts and volatility comparison bar charts using matplotlib.
4. Key Findings
Volatility Analysis (Standard Deviation):
The annualized volatility, calculated using the standard deviation of daily returns, serves as a primary measure of market risk. The results indicate distinct risk profiles across the three selected stocks. Stocks with higher volatility experienced significant price fluctuations over the 2015-2025 period, suggesting a higher level of uncertainty and potential risk for investors compared to those with lower, more stable volatility metrics.
Systematic Risk (Beta):
The Beta coefficient measures the sensitivity of each stock to movements in the overall market (S&P 500). The analysis reveals varying levels of systematic risk. Stocks with a Beta greater than 1.0 are classified as aggressive, tending to amplify market movements, while those with a Beta less than 1.0 are considered defensive, offering more stability during market downturns. This metric is crucial for understanding how each asset would likely behave in different economic conditions.
Risk-Adjusted Performance (Sharpe Ratio):
By evaluating the Sharpe Ratio, we assess the excess return generated per unit of risk taken. The comparison highlights which of the three stocks provided the most efficient return on investment. A higher Sharpe Ratio indicates that the stock delivered better compensation for the risk borne, whereas a lower ratio suggests that the returns may not justify the volatility experienced by the investor.
Downside Risk (Maximum Drawdown):
The Maximum Drawdown metric identifies the largest peak-to-trough decline during the observed timeframe. This analysis underscores the severity of historical losses for each stock. Significant drawdowns highlight periods where the stock price suffered substantial retracement from its peak, serving as a vital indicator for risk management and for understanding the potential worst-case scenario an investor might have faced.
5. How to run
Prerequisites: Ensure Python is installed with the required libraries: pandas, numpy, matplotlib, wrds.
Launch: Open the Jupyter Notebook (stock_analysis.ipynb).
Execution: Run the cells sequentially.
Input:
Enter your WRDS username and password when prompted.
Input the Stock Name and corresponding PERMNO (e.g., Apple: 14593).
Type n to finish the input process and trigger the analysis.
Output: View the generated summary table and charts in the notebook.
6. Product link / Demo
Repository: [Link to your GitHub/GitLab repository]
Demo:
Table Output: [e.g., A summary table comparing risk metrics across 5 selected stocks.]
Visuals: [e.g., Line charts showing normalized price trends from 2015 to 2025.]
7. Limitations & next steps
Limitations:
The current script requires manual input of CRSP PERMNO codes; it does not automatically resolve stock tickers (e.g., "AAPL").
The analysis relies on historical closing prices and does not support real-time data streaming.
Next Steps:
Implement a Ticker-to-PERMNO lookup feature to improve user experience.
Incorporate additional technical indicators (e.g., Moving Averages, RSI) for deeper analysis.
Develop a web-based interface (e.g., using Streamlit) to make the tool accessible to non-programmers.
