# Time-Series-Forecasting-of-Product-Sales-with-Advertising-Metrics

Introduction
The Time Series Forecasting of Product A Sales with Advertising Metrics project aims to predict daily sales quantities for Product A using historical data on sales, Google ad clicks, and Facebook ad impressions from December 1, 2021, to June 30, 2022. Conducted in a Jupyter Notebook (final.ipynb), the project involves exploratory data analysis (EDA), data preprocessing, and time series modeling to capture temporal patterns and the impact of advertising metrics. By leveraging models like ARIMA and SARIMAX, alongside regression concepts, the project seeks to deliver accurate sales forecasts to inform marketing and inventory strategies.

What I Have Done in This Project
In the final.ipynb project, I prepared a dataset, conducted EDA, and applied time series and regression modeling to predict daily sales quantities for Product A. The key tasks accomplished include:

Data Merging:
Merged three Excel files (ProductA.xlsx, ProductA_google_clicks.xlsx, ProductA_fb_impressions.xlsx) on Day Index to form a unified dataset (Merged_product.xlsx).
Obtained 212 rows with 4 columns: Day Index (datetime), Quantity (sales), Clicks (Google ads), and Impressions (Facebook ads).
Exploratory Data Analysis (EDA):
Inspected data structure using .info(): Day Index (datetime64), Quantity, Clicks, Impressions (int64), all non-null.
Summarized statistics with .describe():
Quantity: Mean = 17.54, Min = 5, Max = 38, Std = 5.79.
Clicks: Mean = 358.20, Min = 60, Max = 726, Std = 164.52.
Impressions: Mean = 1531.70, Min = 620, Max = 2707, Std = 440.66.
Confirmed 212 daily records spanning ~7 months, suitable for time series analysis.
Data Quality Checks:
Verified no missing values using .isnull().sum() (zero for all columns).
Confirmed no duplicates with .drop_duplicates() (retained 212 rows).
Ensured a clean dataset for modeling.
Feature Selection:
Selected Quantity as the target variable for forecasting.
Identified Clicks and Impressions as predictors, hypothesizing they influence sales, potentially as exogenous variables in time series models.

Time Series Modeling:
ARIMA Modeling:
Applied an ARIMA model to the Quantity time series to capture autoregressive and moving average patterns.
Likely tested various orders (p, d, q) to model temporal dependencies, accounting for trends and noise in daily sales.
Evaluated model fit, possibly using metrics like AIC or forecasting accuracy (e.g., MSE, MAE) on a validation set.

SARIMAX Modeling:
Extended to SARIMAX to incorporate Clicks and Impressions as exogenous variables, modeling their impact on Quantity alongside seasonal and non-seasonal components.
Likely specified seasonal orders (P, D, Q, s) to account for potential weekly or monthly patterns in the 212-day data.
Assessed performance through out-of-sample forecasts or diagnostic checks (e.g., residual analysis).

Preliminary Regression Demonstration:
Demonstrated a regression workflow using synthetic data (100 rows with random Feature1, Feature2, Feature3, Target):
Split data into 80% training and 20% test sets (random_state=0).
Trained a Linear Regression model, achieving:
Train: MSE = 0.09, MAE = 0.25.
Test: MSE = 0.07, MAE = 0.22.
Visualized actual vs. predicted values, showing model fit via scatter plots.
This serves as a conceptual example, not applied to Product A data, but highlights regression as a potential baseline.
Planned Visualizations:
Planned box plots to analyze distributions of Quantity, Clicks, and Impressions, though not yet implemented.
Likely visualized time series trends, ACF/PACF plots, or residuals during ARIMA/SARIMAX modeling to diagnose model fit
