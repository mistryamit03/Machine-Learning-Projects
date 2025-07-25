# 🧠 Demand and Pricing Optimization for E-commerce Products

A full-stack data science project designed to optimize pricing strategies across multiple product categories using predictive modeling and neural networks.

---

## 📚 Contents

- [Project Summary](#project-summary)
- [How to Use](#how-to-use)
- [Data Overview](#data-overview)
- [Forecasting Product Demand](#forecasting-product-demand)
- [Optimizing Prices](#optimizing-prices)
- [Projecting Revenue](#projecting-revenue)
- [Evaluating Model Performance](#evaluating-model-performance)
- [Technical Stack](#technical-stack)
- [Contribution Guidelines](#contribution-guidelines)
---

## 📌 Project Summary

This project tackles the challenge of forecasting demand and optimizing product prices in a retail e-commerce environment. Using a combination of time-series forecasting (ARIMA), gradient boosting (XGBoost), and feedforward neural networks (MLP), the solution identifies pricing strategies that maximize profit and revenue across different product categories.

---

## 🧑‍💻 How to Use

1. Load the dataset into a DataFrame.
2. Run the EDA notebook to explore trends.
3. Apply feature engineering to generate demand, profit, and price-related fields.
4. Forecast demand using ARIMA and XGBoost.
5. Optimize prices using a custom MLP model.
6. Simulate revenue using adjusted prices.

---

## 📦 Data Overview

Your data should include the following features:

```plaintext
product_id, product_category_name, month_year, qty, total_price, freight_price, unit_price,
product_name_lenght, product_description_lenght, product_photos_qty, product_weight_g,
product_score, customers, weekday, weekend, holiday, month, year, volume,
comp_1, ps1, fp1, comp_2, ps2, fp2, comp_3, ps3, fp3, lag_price,
demand, revenue_comp1, profit_comp1, margin_comp1,
revenue_comp2, profit_comp2, margin_comp2,
revenue_comp3, profit_comp3, margin_comp3,
revenue_our_product, profit_our_product, margin_our_product,
fp1_diff, fp2_diff, fp3_diff, price_ratio_1, price_ratio_2, price_ratio_3,
price_diff_1, price_diff_2, price_diff_3, price_change


These features are used for modeling elasticity, computing profits, and benchmarking competitors.

🔮 Forecasting Product Demand
We apply both classical and ML-based forecasting techniques:

ARIMA: Applied per category after stationarity checks to model seasonality and trends.

XGBoost: Handles non-linear demand patterns.

Evaluation metrics: RMSE, MAE, and R².

💸 Optimizing Prices
A custom-built Multi-Layer Perceptron (MLP) is used to optimize product pricing (unit and total price).

📐 Architecture Summary
Layer	Details
Input Layer	All selected numerical features
Hidden Layer 1	64 neurons + ReLU + Dropout(0.2)
Hidden Layer 2	32 neurons + ReLU + Dropout(0.2)
Hidden Layer 3	16 neurons + ReLU
Output Layer	1 neuron (predicts price)
Loss Function	MSE (regression task)
Optimizer	Adam

The model captures key drivers of pricing such as:

Freight cost

Product score

Competition prices

Demand fluctuations

📊 Projecting Revenue
Once optimized prices are obtained, revenue can be simulated using expected quantities.

Example Simulation
Category	Optimized Price	Expected Quantity	Simulated Revenue
perfumery	412.29	159	65,553.61
watches_gifts	1689.66	753	1,272,317.31

✅ Evaluating Model Performance
Models are evaluated using:

R² Score – Goodness of fit

RMSE – Error magnitude

MAE – Absolute error

Separate metrics are generated per category and model (ARIMA/XGBoost/MLP).

⚙️ Technical Stack
Tool/Library	Purpose
Python 3.x	Core programming language
Pandas, NumPy	Data manipulation
Seaborn, Matplotlib, Plotly	Visualization
Scikit-learn	Preprocessing & metrics
Statsmodels	ARIMA forecasting
XGBoost	Demand regression
TensorFlow/Keras	Neural network modeling
SHAP	Model explainability (optional)

🤝 Contribution Guidelines
Pull requests are welcome for:

Enhancing model logic

Adding new optimization scenarios

Improving visualizations or interactivity

