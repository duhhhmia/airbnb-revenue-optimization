# Airbnb vs. Marketplace: Nightly Rate Prediction & Revenue Optimization

## 📋 Project Overview
This project leverages predictive machine learning models to analyze short-term rental dynamics and forecast optimal nightly pricing. By evaluating a dataset of over 116,000 monthly listing observations across distinct Southern California destination markets, the analysis establishes an automated revenue optimization framework to maximize property yields.

## ❓ The Business Problem
Hosts often struggle to price listings dynamically, leading to either unbooked nights (overpricing) or missed revenue (underpricing). This project builds an end-to-end regression and classification pipeline to accurately predict competitive nightly rates based on property features, platform mechanics, and localized geographic trends across two contrasting environments:
* **The Alpine Market:** Big Bear Lake & Big Bear City
* **The Desert Market:** Joshua Tree & Yucca Valley

## 🛠️ Tech Stack & Machine Learning Pipeline
* **Language:** Python
* **Libraries:** Scikit-Learn, Pandas, NumPy, Matplotlib, Seaborn
* **Workflow:**
    * **Data Wrangling & Integration:** Merged core market performance data with structured amenity features, resolved missing revenue indicators, and imputed median lead times.
    * **Feature Engineering:** Implemented categorical encoding (`get_dummies`) with dummy variable trap protection for cities and host types, mapped calendar months to specific meteorological seasons, and engineered a binary target variable (`is_high_price`) based on median price thresholds.
    * **Model Exploration:** Evaluated baseline models against regularized regression techniques and binary classifiers.

## 📊 Key Modeling Results & Insights
Rather than relying on basic characteristics, the modeling process demonstrated significant performance gains as spatial and temporal features were integrated:

* **Baseline Linear Regression:** Utilizing only baseline capacity constraints (bedrooms and bathrooms) yielded a weak test $R^2$ score of **13.90%** with a high Root Mean Squared Error (RMSE) of **$336.17** per prediction.
* **The Regularization Jump (The Winner):** Expanding the feature matrix to include localized geographic indicators and seasonal dummies—and optimization via **Ridge Regression** ($\alpha \approx 209.70$) and **Lasso Regression** ($\alpha \approx 0.71$)—boosted the $R^2$ score to an impressive **73.65%**.
* **Predicting Premium Listings:** A **Logistic Regression** model built to classify whether an accommodation would command an above-median nightly rate achieved a **67.82% testing accuracy** (True Negative: 10,491 | True Positive: 9,280).

## 💡 Strategic Business Impact
* **The "Snow Effect" Premium:** Feature importance extraction revealed that **Winter Season** was the single most powerful driver for high-price rental classification (Coefficient: **1.01**), a trend heavily localized to the alpine constraints of Big Bear Lake. 
* **Platform & Portfolio Arbitrage:** While the alpine market experiences a massive winter surge, the desert markets (Joshua Tree and Yucca Valley) exhibit a counter-seasonal trend. Property management groups can leverage these insights to hedge seasonal dips by cross-allocating marketing capital between desert and mountain asset portfolios based on predictive demand peaks.
