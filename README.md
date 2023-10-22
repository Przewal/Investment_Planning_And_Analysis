# Investment Planning and Analysis

In this project, we leverage insights gathered over several weeks to create a foundational algorithm. This algorithm is designed to perform a quantitative assessment on predefined investment portfolios. We further employ Monte Carlo simulation to project the expected returns for each portfolio, establishing a confidence interval range for a specified initial investment amount of __$20,000__.

Our study encompasses five distinct portfolios, each of which is compared to the broader market represented by the S&P 500 Index. To acquire the necessary data for our analysis, we extract stock information from Yahoo Financials for all individual stocks within these portfolios. The analysis is centered on data spanning from the current date, going back five years in time. It's important to note that the results of our simulations will exhibit variability based on the timeframe chosen for analysis.

These five portfolios have been meticulously defined based on a thorough literature review and market research conducted by our team. They are categorized as follows:


### Low Risk Portfolio
Lowest Beta stocks arranged from highest market cap from [Marketbeat](https://www.marketbeat.com/market-data/low-beta-stocks/ )

* LLY - Eli Lilly and Company
* NVO - Novo Nordisk A/S
* WMT - Walmart Inc.
* JNJ - Johnson & Johnson
* PG - Procter & Gamble Company
* MRK - Merck & Co., Inc.
* ABBV - AbbVie Inc.
* KO - The Coca-Cola Company
* PEP - PepsiCo, Inc.
* AZN - AstraZeneca PLC


### Growth Portfolio
Largest 5 stocks from SP 500 and NASDAQ.

- AAPL - Apple Inc.
- MSFT - Microsoft Corporation
- AMZN - Amazon.com, Inc.
- NVDA - NVIDIA Corporation
- GOOGL - Alphabet Inc. (formerly Google Inc.)
- META - Meta Platforms, Inc. (formerly Facebook, Inc.)
- TSLA - Tesla, Inc.
- AVGO - Broadcom Inc.
- COST - Costco Wholesale Corporation
- ADBE - Adobe Inc.

### Moderate Risk Portfolio
5 stocks each from SP Mid Cap Index and Vanguard Mid Cap Index.

- HUBB - Hubbell Incorporated
- JBL - Jabil Inc.
- BLDR - Builders FirstSource, Inc.
- RS - Reliance Steel & Aluminum Co.
- DECK - Deckers Outdoor Corporation
- APH - Amphenol Corporation
- AJG - Arthur J. Gallagher & Co.
- GGG - Graco Inc.
- MSI - Motorola Solutions, Inc.
- PCAR - PACCAR Inc.


### High Risk Portfolio
5 stocks each from SP Small Cap Index and Vanguard Small Cap Index. 


- AIT - Applied Industrial Technologies, Inc.
- SPSC - SPS Commerce, Inc.
- FIX - Comfort Systems USA, Inc.
- RMBS - Rambus Inc.
- FN - Fabrinet
- TRGP - Targa Resources Corp.
- PTC - PTC Inc.
- AXON - Axon Enterprise, Inc.
- ENTG - Entegris, Inc.
- DECK - Deckers Outdoor Corporation


### Traditional Companies Portfolio
Largest 10 stocks from Dow Jones Industrial Average.

- UNH - UnitedHealth Group Incorporated
- GS - The Goldman Sachs Group, Inc.
- HD - The Home Depot, Inc.
- CAT - Caterpillar Inc.
- AMGN - Amgen Inc.
- DELL - Dell Technologies Inc.
- PTC - PTC Inc.
- HUBB - Hubbell Incorporated
- STLD - Steel Dynamics, Inc.
- FDS - FactSet Research Systems Inc.

<br>

__Note__: Each stock within the portfolios has an equal weight, set at 0.1 by default.

The daily returns for these portfolios over the last five years is calculated and all the portfolios are concatenated with the S&P 500 daily returns to conduct a quantitative analysis. The goal is to determine which portfolio is performing the best across multiple areas: Volatility, Returns, Risk, and Sharpe ratios. 

* Performance Analysis
* Risk Analysis
* Rolling Statistics
* Sharpe Ratios

## Quantitative Analysis 
Updated on 22 Oct 2023

### Daily Returns
While daily returns offer insights into short-term trends, they might not be the most suitable method for understanding returns. Therefore, we utilize cumulative returns as a better baseline.

![Daily Returns](./Analysis%20Images/Daily%20Returns.png)


### Cumulative Returns
From the cumulative returns, we can infer that the High-Risk and Growth Portfolios have the highest cumulative returns. The Moderate-Risk portfolio also suggests high returns. Surprisingly, all the defined portfolios indicate a high cumulative returns compared to the S&P 500 Index. 

![Cumulative Returns](./Analysis%20Images/Cumulative%20Returns.png)


### Annualized Standard Deviation
We gauge volatility using standard deviation. The higher the standard deviation, the more volatile the stock. To account for the annual trading days (252), we multiply the standard deviation by the square root of 252. For brevity, only the annualized standard deviation values are shown below.

<img src="./Analysis%20Images/Standard%20Deviation.png" alt="Standard Deviation" style="width:250px;">
<br>
<br>

The Low-Beta (Low-Risk) portfolio exhibits the lowest standard deviation, indicating lower volatility. The High-Risk and Growth portfolios show similar standard deviation values, but the Moderate-Risk portfolio, despite similar cumulative returns, is less volatile.


### Rolling Statistics (Exponentially Weighted)

Exponentially weighted rolling statistics (EMAs) are more sensitive to recent data and are useful for capturing short-term trends and reacting quickly to changes in the time series. On the other hand, regular rolling statistics (SMAs) provide a smoother, less sensitive representation of data and are useful for reducing noise and identifying longer-term trends.

![Rolling Statistics](./Analysis%20Images/Rolling%20Statistics.png)

Using the rolling statistics it can be inferred that the Growth portfolio has slightly higher risk as compared to the High-Risk portfolio since 2022.

### Correlation
The correlation plot across different porfolios is derived and it can be seen that S&P 500 does have a high correlation with most of our portfolios as we derived values from the index. The portfolios among themselves do not indicate high correlation as such.

![Correlation](./Analysis%20Images/Correlation.png)


### Beta
For brevity, the traditional companies portfolio is omitted. Each of the portfolio is analyzed with the S&P 500 to determine the beta. The Growth Portfolio has the higest beta among all the portfolios. 

![Beta](./Analysis%20Images/Beta.png)

### Sharpe Ratios
While returns alone can provide a good understanding of where to invest, a return-to-risk analysis can help determine which portfolio to invest in when they offer almost identical returns but lower risk. Sharpe ratios help evaluate returns in the context of risk. A higher Sharpe ratio indicates a better return for the same level of risk.

![Sharpe Ratio](./Analysis%20Images/Sharpe%20Ratio.png)

The moderate risk portfolio stands out in the top as it offers better returns with lower risk compared to the rest.


## Monte Carlo Simulation
Updated on 22 Oct 2023


### Low-Risk Portfolio
There is a 95% chance that an initial investment of __$20,000__ in the Low-Beta portfolio over the next 5 years will end within in the range of __$32,584.44__ and __$87,695.01__

![Returns](./Analysis%20Images/low_beta_returns.png)

![Returns](./Analysis%20Images/low_beta_dist.png)


### Moderate-Risk Portfolio
There is a 95% chance that an initial investment of __$20,000__ in the Moderate Risk portfolio over the next 5 years will end within in the range of __$50,260.76__ and __$267,874.6__

![Returns](./Analysis%20Images/moderate_returns.png)

![Returns](./Analysis%20Images/moderate_dist.png)


### High-Risk Portfolio
There is a 95% chance that an initial investment of __$20,000__ in the Low-Beta portfolio over the next 5 years will end within in the range of __$52,601.12__ and __$239,269.63__

![Returns](./Analysis%20Images/high_risk_returns.png)

![Returns](./Analysis%20Images/high_risk_dist.png)


### Growth Portfolio
There is a 95% chance that an initial investment of __$20,000__ in the Growth portfolio over the next 5 years will end within in the range of __$51,547.33__ and __$524,025.9__

![Returns](./Analysis%20Images/growth_returns.png)

![Returns](./Analysis%20Images/growth_dist.png)


### Traditional Companies Portfolio
There is a 95% chance that an initial investment of __$20,000__ in the Traditional Companies portfolio over the next 5 years will end within in the range of __$31,024.06__ and __$97,972.13__

![Returns](./Analysis%20Images/traditional_returns.png)

![Returns](./Analysis%20Images/traditional_dist.png)


### S&P 500
There is a 95% chance that an initial investment of __$20,000__  in the S&P 500 over the next 5 years will end within in the range of __$12,381.59__ and __$81,655.76__

![Returns](./Analysis%20Images/sp500_returns.png)

![Returns](./Analysis%20Images/sp500_dist.png)

### Diversified Portfolio
As a final twist, all the five defined portfolio are combined with equal weight allocation.

There is a 95% chance that an initial investment of __$20,000__  in the Diversified Portfolio over the next 5 years will end within in the range of __$41,787.31__ and __$143,166.21__

![Returns](./Analysis%20Images/mix_returns.png)

![Returns](./Analysis%20Images/mix_dist.png)