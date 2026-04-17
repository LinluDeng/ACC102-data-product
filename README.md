Stock Risk Analysis & Valuation Tool
1. Problem & User
College students and beginner investors often lack the technical tools to quantitatively evaluate stock risk. This project provides a Python-based solution to automate the calculation of key financial metrics (Beta, Volatility, Sharpe Ratio) and visualize performance against the S&P 500 market benchmark.
2. Data
Source: Wharton Research Data Services (WRDS) - CRSP (Center for Research in Security Prices) Database.
Access Date: April 2026.
Key Fields: permno (Stock Identifier), date, prc (Price), ret (Daily Returns), vwretd (Market Value Weighted Return).
3. Methods
Data Extraction: Used pandas and wrds libraries to execute SQL queries, fetching daily price and return data for user-specified stocks and the market index.
Data Preprocessing: Cleaned data by handling missing values (dropna), converting dates, and calculating absolute prices.
Financial Modeling: Implemented custom functions to calculate Annualized Volatility, Beta (using aligned covariance/variance), Maximum Drawdown, and Sharpe Ratio.
Visualization: Utilized matplotlib to generate normalized price trend charts and comparative volatility bar charts.
4. Key Findings
The tool successfully calculates Beta Coefficients, allowing users to identify if a stock is more (Beta > 1) or less volatile than the market.
Maximum Drawdown analysis highlights the potential worst-case scenario for an investment during the selected period.
The Sharpe Ratio provides a clear metric for risk-adjusted returns, helping users compare efficiency across different stocks.
Visual comparison of individual stocks against the S&P 500 index offers immediate context on relative performance.
5. How to run
Install dependencies: pip install wrds pandas numpy matplotlib
Ensure you have a valid WRDS username and password.
Run the script in a Jupyter Notebook or terminal.
Follow the on-screen prompts to enter stock PERMNOs (e.g., 14593 for Apple) and the desired date range.
6. Product link / Demo
(Note: Since this is a local script, you can link to your GitHub repository here)
GitHub Repository: [Insert your GitHub Link Here]
Demo Video: [Insert a link to a screen recording of the code running, if available]
7. Limitations & next steps
Limitations: Currently relies on manual input of PERMNOs (stock IDs), which may be unfamiliar to non-expert users. The analysis is purely historical and does not predict future prices.
Next Steps: Integrate an automatic ticker-to-PERMNO lookup feature. Incorporate fundamental data (e.g., P/E ratios) from the Compustat database to enhance valuation analysis.
