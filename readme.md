Data Analysis Exercise on the Global Food Prices (WFP) Dataset

Project objective:
clean and analyze a dataset in excel format related to the price trends of the main foodstuffs: oil, cereals, meat, dairy products.

Dataset used:

The data come from official surveys of the United Nations World Food Programme (WFP) and FAO. 

Main results:

• pre-processing:
       dataset cleaning, missing data detection, text and date formatting,
    • trend analysis: analysis of the price index trend over the period
       reference 1990-2026.
    • Volatility and Price Increases: Oil recorded the highest price increase and volatility overall, followed by dairy products. Sugar showed the trend which was most contained and disconnected from the other categories. 
    • Predictive Model Development and Forecasting

To predict future prices, two machine learning approaches were compared: Linear Regression and a decision tree-based model (Random Forest Regressor).
• Phase 1:
(Simple Models with Single Lag): Linear Regression initially beat Random Forest (MAE by 1.37 vs. 1.68). However, in generating long-term recursive projections for 2026/2027, the simple linear model tended to zero background noise, rapidly flattening to a constant value (share 131) that was unrealistic for a real market. 
• Phase 2:
(Feature Engineering and Evolved Model): To address flattening, the dataset was enriched by inserting monthly seasonality and deeper historical memory (Lags at 1, 2 and 12 months). With this new architecture, Advanced Linear Regression dramatically reduced its margin of error, achieving a Mean Absolute Error (MAE) of 1.04, confirming itself as the optimal model for generating dynamic and wavy future predictions.

Data Description

The dataset has 436 rows and 7 columns.
They are all numeric columns except the ‘Dates’ column which represents the reference month and year day.
There are no missing values.

Data cleaning

The ‘Date’ column has been converted to the standard Pandas 'datetime' format to be correctly recognized as a time index.
The components of 'Year' and 'Month' were extracted from the complete time record. This decomposition was crucial both in the exploratory analysis phase (to calculate annual averages and identify historical peaks) and in the Machine Learning phase (to pass the month number to the model as an indicator of seasonality).

Exploratory Data Analysis (EDA)

Dataset analysis reveals:

  • the average value of the highest price index overall is 144.51 reached in 2022
  • The most expensive category in 2022 was: Oils with an average value of 187.78
  • The index's absolute peak was 160.22 reached in April 2026
  • The index exceeded the value of 130 for 33 months in the years: 2008, 2011, 2021, 2022, 2023, 2025, 2026
  • the most expensive month of the year is April with an index worth 90.40
  • historical volatility sees oils top, then dairy and cereals
  • the percentage growth of oils from 1990 to 2026 was 295.81% followed by dairy with around 182%, last in the sugar ranking grew by only 15%
  • the relative price of oil vs. meat peaked in 2008 and 2022
  • the reactionary price cereals vs dairy products follows a reverse trend compared to oil vs meat with a minimum peak in 2008 and 2025
  • the relative price of cereals vs oils reached its highest peak in the early 2000s and now has a low peak in 2025

Conclusions

At the end of the analysis, a prediction of the price index was attempted.
• Phase1:
a simple linear regression machine learning model that has a mean absolute error of 1.37 demonstrating good predictive ability , better than the decision tree-based model that has a mean absolute error of 1.67.
However, when attempting to predict the price index for 2027 with this model, the result does not appear very credible.
• Phase 2:
a new model is developed by introducing seasonality and long-term trends.
I tried both models and the linear regression has a mean absolute error of 1.04 while the RandomForest Regressor has 1.77.

Linear regression predicts a range of values from 129 to 131 without flattening around a single value

Self-developed project for the EDA part and optimized with LLM support for the advanced feature engineering part”.
