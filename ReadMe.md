### How does stock price movement in particular sectors relate to company fundamentals, economic factors, and other market indicators

**Sanjay Kumar Hooda**

#### Executive summary
This project make investment intelligence accessible to everyone by giving everyday investors access to analytical tools traditionally reserved for professionals and research teams only. Using open-source, data-driven models, it provides risk-return profiles for 300+ stocks across major sectors including technology, healtcare, industrial, finacials, and customer discretionary. It uncovers sector-level patterns that help individuals make smarter portfolio decisions. The integrated economic analysis quantifies how factors such as interest rates, money supply, and market volatility influence sector performance—for example, how rate hikes affect financial stocks—empowering users to anticipate market movements rather than react to them. Sector-specific insights deepen this understanding by showing how industries like technology, financials, and consumer discretionary respond to different macroeconomic conditions. Predictive, time-lagged models enable proactive planning by estimating stock performance 1, 3, and 6 months ahead, while volatility and clustering analysis strengthen risk management by clarifying diversification needs, drawdown potential, and risk-tolerance alignment. By making all research transparent and open source, the project not only levels the playing field for retail investors but also educates them, allowing users to verify methods, reproduce results, and customize analyses to fit their individual financial goals.
#### Rationale
Why should anyone care about this question?
People should care about this question because  everyday investors are expected to take important financial decisions without the tools or knowledge that professional investors use. Most people managing their financial accounts don’t understand how to analyze stocks and how economic changes—like interest rates or market volatility—affect their investments. This project gives them easy-to-use, transparent analysis that helps them understand what’s happening in the market, make smarter choices, and avoid unnecessary losses. In a fast-moving financial world, giving regular people better information isn’t just helpful—it can make a real difference in their long-term financial security.
#### Research Question
What are you trying to answer?
 I am trying to answer a very simple but important question that is how does stock price movement in particular sectors relate to sales growth, company fundamentals, and macroeconomic factors
#### Data Sources
What data will you use to answer you question?
For stock data yahoo finance has been my source of the data
For economic indicators came from two source yahoo finance and fred .
#### Methodology
What methods are you using to answer the question?
The following steps have been used 
**1. Data Collection & Processing**
Historical Price Data: Yahoo Finance API (yfinance) for 2-year daily stock prices across 303 stocks
Economic Indicators: FRED API (Federal Reserve Economic Data) for macroeconomic time series (M2, Fed Funds Rate, GDP, CPI, Unemployment, Treasury Yields)
Market Volatility: VIX index from Yahoo Finance
Data Cleaning: Forward-fill for missing values, outlier detection, handling of delisted/acquired stocks
**2. Feature Engineering** - Following  indicators have been used including
**Technical**
Momentum indicators (RSI, MACD)
Moving averages (20-day, 50-day, 200-day)
Volatility measures ( standard deviation)
Volume-based metrics
**Economic**
From FRED:
Monetary Policy: M2 Money Supply, Federal Funds Rate, Treasury Yields (2Y, 5Y, 10Y)
Economic Growth: GDP, Industrial Production, Capacity Utilization
Inflation: CPI, PPI, PCE, Core CPI
Labor Market: Unemployment Rate, Non-farm Payrolls, Labor Force Participation, Initial Claims
Consumer: Retail Sales, Consumer Sentiment (UMich), Personal Income
Housing: Housing Starts, New Home Sales, Existing Home Sales
Credit Markets: Corporate Bond Spread (BAA), High Yield Credit Spread
From Yahoo:
VIX (^VIX) - Volatility Index
Oil Prices (CL=F) - WTI Crude Oil futures
US Dollar Index (DX-Y.NYB) - Dollar strength
Gold Prices (GC=F) - Gold futures
All economic data is cached to 'economic_data_cache.pkl' to avoid re-downloading on subsequent runs, similar to the stock price cache.
**Fundamental**
Returns calculations (daily, monthly, cumulative)
Risk metrics (annualized volatility, Sharpe Ratio)
Sector aggregations
**3. Exploratory Data Analysis (EDA)**
Visualization: Correlation heatmaps, time series plots, risk-return scatter plots
Descriptive Statistics: Mean, median, standard deviation, skewness by sector
Distribution Analysis: Identifying patterns in returns across sectors and time periods
**4. Machine Learning Models**
Linear Regression: Baseline model for return prediction
Ridge Regression: Regularized linear model to handle multicollinearity (alpha=1.0)
Random Forest Regressor: Ensemble method for capturing non-linear relationships 
Train-Test Split: 80/20 time-series split (respects temporal ordering)
**5. Model Evaluation**
Performance Metrics:
R² Score (coefficient of determination)
RMSE (Root Mean Squared Error)
MAE (Mean Absolute Error)
Cross-Validation: Time-series aware validation to prevent data leakage
Visualization: Actual vs. Predicted plots, residual analysis
**6 Economic Indicators Evaluation**

**7. Sector-Specific Analysis**
Comparative Analysis: How each sector responds to economic changes
Sensitivity Testing: Correlation of sector returns with specific economic indicators
Scatter Plot Analysis: Risk-return profiles by sector
**8. Data Persistence**
Caching Strategy: Pickle files for large datasets (price_data, economic_data, fundamentals)
Version Control: Structured notebooks (EDA → Advanced → Economic)
Output Artifacts: CSV exports 
**9. Results and Findings**
The comprehensive analysis of 28+ economic indicators across 5 major sectors (Technology, Healthcare, Financials, Industrials, and Consumer Discretionary) reveals that 
economic fundamentals significantly drive stock prices, with machine learning models achieving high R² scores demonstrating strong predictive power. Market volatility (VIX) emerged as the
most powerful and consistent predictor across all sectors, with commodities (oil, gold) and foreign exchange (USD strength) also showing substantial impact. Critically, different sectors exhibit
distinct sensitivities to economic conditions: Technology is highly vulnerable to interest rate changes and monetary policy due to long-duration growth characteristics; Financials thrive on 
steep yield curves and healthy credit markets but suffer when spreads widen; Healthcare demonstrates defensive properties with minimal economic sensitivity; Industrials correlate strongly with 
GDP growth, industrial production, and housing activity; while Consumer Discretionary is most responsive to employment, consumer sentiment, and disposable income metrics. This sector-specific 
response pattern enables sophisticated investment strategies including pro-cyclical rotation (favoring Industrials/Financials in early recovery, Technology/Consumer Discretionary in mid-cycle, 
and defensive Healthcare in late-cycle), tactical positioning based on interest rate environments (overweighting Financials when rates rise, Technology when rates fall), and risk management adjustments 
during volatility spikes or credit spread widening. The analysis conclusively demonstrates that fundamentals matter significantly for stock price determination, and understanding these sector-specific 
economic sensitivities provides actionable insights for portfolio construction, sector allocation, and timing decisions across different economic regimes.

The analysis shows that economic factors account part  of the variance in stock returns but is sector specific as well, suggesting that while they play a major role, predictability has a  ceiling,
this shows that the  markets remain partly efficient. The time horizon also matters: three-month predictions provide the best balance between accuracy and practical usefulness. In addition to broad 
economic influences, sector-specific dynamics contribute a part of the variance in returns, highlighting the importance of understanding both macro conditions and industry-level effects when evaluating stock performance.

#### Next steps
I would be using the outcome from this project for my own stock investing journey
#### Outline of project

- [Basic Data Analysis](https://github.com/sanjayhooda19/CapStoneFinal/blob/main/StockAnalysis_EDA.ipynb)
- [Advanced Data Analysis](https://github.com/sanjayhooda19/CapStoneFinal/blob/main/StockAnalysis_Advanced.ipynb)
- [Update Sector stocks](https://github.com/sanjayhooda19/CapStoneFinal/blob/main/update_sector_stocks.ipynb)
- [Economic Factors](https://github.com/sanjayhooda19/CapStoneFinal/blob/main/EconomicFactors_Analysis.ipynb)
- [StockPricePrediction](https://github.com/sanjayhooda19/CapStoneFinal/blob/main/StockPricePrediction.ipynb#:~:text=StockPricePrediction.ipynb)


##### Final Thoughts
Really thankful to the whole team for the proper guidance during the programm, I feel really confident to do any AI-ML project on my own now. The whole journey was really fruitful. 
