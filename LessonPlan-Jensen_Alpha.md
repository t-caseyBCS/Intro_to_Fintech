# **Lesson Plan: Finding Alpha**

---
## Prerequisite Python Libraries
1. [Pandas](https://pandas.pydata.org/)

2. [yFinance](https://pypi.org/project/yfinance/)

3. [getFamaFrenchFactors](https://pypi.org/project/getFamaFrenchFactors/)

4. [statsmodels](https://www.statsmodels.org/stable/index.html)

---
## Overview

This lesson will cover how financial analysts, and other finance professionals including portfolio managers, measure the risk-adjusted performance of their fund's ability to generate an abnormal return, or alpha.

---
## Objectives
By the end of this lesson, you will be able to:

1. Define the Jensen Measure and interpret its results

2. Explain how and why Jensen Alpha is used to measure fund performance

3. Pythonically compare a portfolio's performance to a benchmark

---
## **1. What Is the Jensen's Measure?**

<br>
The focus of this lesson is to meausure the performance of a single investment or portfolio against a benchmark. The financial calculations described in this lesson can also be used to measure a fund manager's performance against returns from a market-related investment (i.e. a mutal fund performance compared to the S&P 500).

<br>
Let's begin by setting up the scenario:

>You have worked very hard to create an `optimized portfolio` of securities by picking stocks that are `noncorrelated`, or `minimally-correlated`, and offer the highest `Sharpe ratios`.

<br><summary><b>Question:</b> How would you describe this in layman's terms?</summary><br>

<details>
    <summary><b>Answer:</b> (<i>click to expand</i>)</summary><br>
    In other words, You have created a portfolio of assets <i>(stocks)</i> consisting of groups of <code>diversified</code> assets. Within this portfolio, you select assets with price movements that are minimally related or non-related. Amongst this group, you then identify assets with the highest returns per unit of risk, which is called a <code>risk-adjusted return</code>. <b>This effectively minimizes the overall volatility of the portfolio, while maximizing the return-to-risk ratio, thus creating an <code>optimized portfolio</code></b>.
</details><br>

---
Continuing in our scenario:

>Let's say a year has pass and your optimized portfolio has accumulated profit. But so has the overall market… In fact you recall reading a market analysis report on MorningStar calling this year "One of the greatest bull-run years in history." **Now you begin to wonder: "Are my returns better than the market's?"** 

Naturally, you begin to compare your portfolio's return to that of the market using the simple return formula below to calculate the corresponding returns.

* **EXAMPLE:** Assume your portfolio realized a return of 13% last year, and the appropriate benchmark index for this fund (S&P 500 index) returned 12%. **Did you beat the benchmark?**

    ![return_formula](Images/return_formula.PNG "Simple Return Formula")

 * In short, it is hard to determine if you at this point.

 * **Why?** Well, consider the following:

    * What if your portfolio consists of relatively riskier securities than your benchmark?

    * How would you know the required return you need to satisfy the extra risk your portfolio took on?

* By using the simple return formula you cannot accurately determine your portfolio's performance, because it does not account for risk. Recall, how you worked very hard to create an optimized portfolio that maximizes the return-to-risk ratio.

<br>

**The Jensen's measure**, or **`Jensen's alpha`**, is a risk-adjusted performance measure that quantifies the excess returns obtained by a portfolio or investment, above or below the returns implied by the capital asset pricing model (CAPM), given the portfolio's or investment's systematic risk *(beta)* and the average market return.

* This metric is also commonly referred to as simply `alpha`.

* Jensen’s alpha focuses only on non-diversifiable, relevant risk by using beta and CAPM. It assumes that the portfolio has been adequately diversified.

* The Jensen's alpha can be calculated using the following formula:

    ![jensen_alpha_formula](Images/jensen_alpha_formula.PNG "Jensen's Alpha Formula")

    Jensen's Alpha equals the portfolio return minus the capital asset pricing model (CAPM) which is the product of the portfolio beta and the market risk premium, plus the risk free rate. 

    ![jensen_alpha_formula2](Images/jensen_alpha_formula2.PNG "Breaking down Jensen's Alpha Formula")

* The formula can be applied to any type of asset including securities, bonds, stocks and derivatives.

* It can also be used to measure a fund manager's performance against returns from a market-related investment. For example, a mutal fund's performance compared to the S&P 500.

---
<br><summary><b>Question:</b> Why is simply calculating the portfolio's return not sufficient in determining performance?</summary>

<details>
    <summary><b>Answer:</b> (<i>click to expand</i>)</summary><br>
In short, simple return does not account for risk. To accurately evaluate the performance of a portfolio or an investment manager, an investor must consider the <code>overall return</code> and <code>risk</code> of the portfolio. You must determine whether the portfolio is earning the proper return for the level of risk it takes. For example, if two funds both have a 20% return, a <code>rational investor</code> should prefer the less risky fund.

![jensen_alpha_formula3](Images/jensen_alpha_formula3.PNG "Incorporating Simple Return in Jensen's Alpha Formula")
</details><br>

<br><summary><b>Question:</b> Time to revisit your portfolio and benchmark returns from earlier. Now, try to solve for alpha given the following:</summary>

![quesiton1](Images/question1.PNG "Assumptions")

<details>
<summary><b>Answer:</b> (<i>click to expand</i>)</summary><br>

![question1_solution](Images/question1_solution.PNG "Solution")

</details><br>


---
## **2. Interpreting Jensen’s Alpha**

Now that you are able to calculate Jensen’s Alpha let's examine the results.

* Jensen's alphas are reported in percentage format

* The value of alpha can range from:

    * **Positive Alpha:** Outperformed the benchmark on a risk-adjusted basis

    * **Negative Alpha:** Underperformed the benchmark on a risk-adjusted basis

    * **Zero Alpha:** Netural Performance (i.e. Tracks benchmark)

* The size of the value indicates the percentage amount the portfolio has under/over performed compared to the market on a risk-adjusted basis.

---
**Let's examine the alpha value we calculated in the above example**

<br><summary><b>Question:</b> Did your portfolio Over or Under perform on a risk-adjusted basis?</summary>

<details>
    <summary><b>Answer:</b> (<i>click to expand</i>)</summary><br>

Given the assumptions in the example: the portfolio `Underperformed` because the Jensen Alpha formula returned a value of -0.8%
</details><br>

<br><summary><b>Question:</b> All things the same, What would your portfolio's realized return need to be in order to "track the benchmark"?</summary>

<details>
    <summary><b>Answer:</b> (<i>click to expand</i>)</summary><br><b>13.8%</b> 

By `"tracking the benchmark"` your portfolio's risk-adjusted return would need to equal the benchmark's return, which is calculated by using CAPM. This returns a `Zero Alpha` otherwise known as `"Netural Performance"`.
</details><br>

<br><summary><b>Question:</b> What does it mean if the value of alpha is positive?</summary>

<details>
    <summary><b>Answer:</b> (<i>click to expand</i>)</summary><br>
If the value is positive, then the investment/portfolio is earning excess returns. In other words, a positive value for Jensen's alpha means a fund manager has <code>"beat the market"</code> with their stock-picking skills.
</details><br>

---
## **3. Student Activity: Finding Alpha**

**Corresponding Activity:** [01-Stu_Finding_Alpha](Activities/01-Stu_Finding_Alpha)

In this activity, you will apply the concept of Jensen's Alpha to determine if your portfolio has over/under-performed against the market on a risk-adjusted basis. 

* To get started open the `starter_file` file in the **`unsolved`** `directory` in Jupyter Lab

* For the purpose of this activity, majority of the code has been provided

**File:** [starter_file.ipynb](Activities/01-Stu_Finding_Alpha/Unsolved/starter_file.ipynb)

**Instructions:** [README.md](Activities/01-Stu_Finding_Alpha/README.md)

---
<details>
    <summary><b>To understand more about the code provided in steps 1-6 of <code>starter_file.ipynb</code> :</b> (<i>click to expand</i>)</summary><br>

### 1. Start by importing the dependencies:

<details>
    <summary><b>How to check if packages are installed:</b> (<i>click to expand</i>)</summary><br>

>NOTE: You will need `yfinance` and `getFamaFrenchFactors` libraries to run this file.
>
> `statsmodels` library should come included wih anaconda. You can check your local machine for any of these packages by running the following commands in Terminal/ Git Bash

* Check Terminal/ Git Bash:

```shell
conda activate
conda list statsmodels
conda list yfinance
conda list getFamaFrenchFactors
```

* After checking packages, if `yfinance` and/or `getFamaFrenchFactors` are not installed on your machine you can `pip install` these packages in your Terminal/ Git Bash or upgrade the current version by using:

```bash
pip install yfinance --upgrade
pip install getFamaFrenchFactors --upgrade
```
</details><br>

```python
# Import packages 
import numpy as np
import pandas as pd
import yfinance as yf
import getFamaFrenchFactors as gff
import statsmodels.regression.linear_model as ln
import statsmodels.tools.tools as ot
```

### 2. Retrieve Stock data from yfinance

* Use *`yFinance download`* method to fetch daily stock price data from Yahoo Finance for multiple tickers over 1 year as defned by the *`start`* and *`end`* parameters

```python
# retrieve daily stock data and load into dataframe
portfolio_data = yf.download(tickers="FB AMZN AAPL NFLX GOOGL", 
                             start="2021-01-01", 
                             end="2022-01-01", 
                             interval = "1d")
portfolio_data
```

* With yFinance download method you can fetch multiple tickers by simply adding a space between each ticker within a string `tickers="FB AMZN AAPL NFLX GOOGL"`

* To fetch data by a specfic interval use the `interval` parameter, otherwise the default is `1d`

    * valid intervals: 1m,2m,5m,15m,30m,60m,90m,1h,1d,5d,1wk,1mo,3mo

* Check out the [yfinance Documentation](https://pypi.org/project/yfinance/) to learn more.


### 3. Retrieve Rf and benchmark data

* Use the *`famaFrench3Factor`* function to obtain the benchmark data on a monthly basis. 

<details>
    <summary><b>What is the Fama-French Model:</b> (<i>click to expand</i>)</summary><br>

* The Fama-French Model is a multi-factor model widely used in both academia and industry to estimate excess returns of an investment asset. 

* It is an extension to the Capital Asset Pricing Model (CAPM) by adding two addtional factors apart from market risk, which is incorporated in CAPM.

* The three factors considered in the model are:
    1. **Market factor (MKT)** - Excess market return
    2. **Size factor (SMB)** - Excess return with a small market cap over those with a large market cap
    3. **Value factor (HML)** - Excess return of value stocks over growth stocks

* Click [here](https://www.investopedia.com/terms/f/famaandfrenchthreefactormodel.asp) to learn more 
</details><br>

* For the purpose of this exercise, we are only using the *`famaFrench3Factor`* function to obtain the Market factor and Risk-Free rate. 

```python
ff3_monthly = gff.famaFrench3Factor(frequency='m')
ff3_monthly.rename(columns={'date_ff_factors': 'Date'}, inplace=True)
ff3_monthly.set_index('Date', inplace=True)
ff3_monthly
```

* Rename the 'Date' column and set it as the index

* Check out the [getFamaFrenchFactors documentation](https://pypi.org/project/getFamaFrenchFactors/) to learn more.

### 4. Calculate the portfolio's monthly returns

* Extract the `'Adj Close'` prices from the stock data and resample them into monthly prices by using the *`resample` function* and setting the parameter to *`"M"`*

* Use the *`pct_change` function* to find the monthly returns by calculating the percentage change of the last price of the monthly data compared to the previous month.

```python
#Calculate monthly returns by resampling the 'Adj Close' stock price data into monthly prices
portfolio_monthly_returns = portfolio_data['Adj Close'].resample('M').last().pct_change().dropna()
portfolio_monthly_returns.head()
```

### 5. Apply Stock weights to the portfolio

* Set the weights for corresponding stocks so that they are equally-weighted 

* Use the *`dot` function* to sum the product of each weight and the corresponding stock monthly return

```python
# Set an equally weighted portfolio
weights = [0.2, 0.2, 0.2, 0.2, 0.2]

#use the `dot` function to sum the product each weight and the corresponding stock montly return
equally_weighted_portfolio_monthly_returns = portfolio_monthly_returns.dot(weights)

# rename the column
equally_weighted_portfolio_monthly_returns.name = "Port_Returns_M"
equally_weighted_portfolio_monthly_returns
```

### 6. Merge the dataframes

* merge the calculated monthly stock returns data with the benchmark dataframe

```python
# Merge the dataframes on 'Date'
jensen_alpha = ff3_monthly.merge(equally_weighted_portfolio_monthly_returns, on='Date')
jensen_alpha
```
</details><br>

### 7. Calculating Alpha

To calculate alpha pythonically, you must first understand how it is represented in a linear equation. 

* Recall the alpha formula

    ![alpha_formula](Images/alpha_formula.PNG "Alpha Formula")

* Thanks to some simple mathematics the alpha formula can be represented as a simpler linear equation

    ![linear_equation](Images/linear_equation.PNG "Linear equation")

* Use the *`Python Stats OLS` function* to perform a linear regression to obtain the coefficient, which is alpha

* Assign 'X' to the market risk premium which is the independent or explanatory variable

* Assign 'y' to the portfolio risk premium which is the dependent or explained variable

```python
# Assign X to the market risk premium which is the independent or explanatory variable
X = jensen_alpha['Mkt-RF']

# Assign y to the portfolio risk premium which is the dependent or explained variable
y = jensen_alpha['Port_Returns_M']-jensen_alpha['RF']

# Use the 'add_constant' function to add a constant to X
X = ct.add_constant(X)

# Use Stats OLS function to build a linear model by using the 'X' and 'y' values
jalpha_model = lm.OLS(y, X).fit()

# Print results
print(jalpha_model.summary())
```

Let's examine the results from the OLS Regression Summary:

* From the results, we use the coefficient *(`"coef"`)* of the constant *(`"const"`)* as the value of Alpha

    * The Jensen's alpha is 0.0034, thus, portfolio generated an excess return of 0.34% 

* Similarly, we use the coefficient *(`"coef"`)* of the market risk *(`"MKT-RF"`)* as the value of Beta

![OLS_results1](Images/OLS_results1.PNG "OLS Regression Summary")


### 8. BONUS: 

* Change your portfolio weightings to see how it affects alpha

```python
weights = [0.2, 0.05, 0.15, 0.5, 0.1]

weighted_portfolio_monthly_returns = portfolio_monthly_returns.dot(weights)
weighted_portfolio_monthly_returns.name = "Port_Returns_M"

jensen_alpha = ff3_monthly.merge(weighted_portfolio_monthly_returns, on='Date')

X = jensen_alpha['Mkt-RF']
y = jensen_alpha['Port_Returns_M']-jensen_alpha['RF']
X = ct.add_constant(X)
jalpha_model = lm.OLS(y, X).fit()

print(jalpha_model.summary())
```

![OLS_results2](Images/OLS_results2.PNG "OLS Regression Summary")