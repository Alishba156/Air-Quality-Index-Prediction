Air Quality Index (AQI) Prediction using Regression Models
Project Overview

This project predicts the Air Quality Index (AQI) in Pakistan using machine learning regression models. By analyzing historical pollutant concentrations and meteorological data from 2021–2024, the project aims to provide actionable insights for environmental policy-making and public health safety.

1. Introduction

Air pollution is a major environmental and public health issue in Pakistan, especially in urban areas. AQI serves as a key indicator for communicating pollution levels and potential health risks. This project applies regression models—including Linear Regression, Ridge, Lasso, Random Forest, Gradient Boosting, and Support Vector Regressor (SVR)—to predict AQI values accurately.

1.1 Problem Statement

High levels of particulate matter ($PM_{2.5}$ and $PM_{10}$) and gases such as $NO_2$ and $CO$ lead to respiratory issues and seasonal smog. Accurate AQI prediction is essential for public health management and informed governmental decision-making.

1.2 Objectives

Predictive Modeling: Build robust regression models to predict AQI based on pollutants and weather data.

Pollutant Impact Analysis: Identify key pollutants affecting AQI the most.

Weather-Pollution Relationships: Explore correlations between meteorological factors (temperature, humidity, wind speed) and pollution levels.

Model Evaluation: Assess model performance using metrics like R² and Mean Absolute Error (MAE).

Insights for Policy: Provide interpretable results to help understand pollution trends and support regulatory actions.

2. Dataset Description

The dataset includes historical air quality and weather data for Pakistan from August 2021 to July 2024.

Target Variable

main_aqi: Overall AQI value (Target).

Pollutant Features

components_pm2_5 – Fine particulate matter (< 2.5 µm)

components_pm10 – Coarse particulate matter (< 10 µm)

components_no2 – Nitrogen Dioxide

components_so2 – Sulfur Dioxide

components_co – Carbon Monoxide

components_o3 – Ozone

components_nh3 – Ammonia

Meteorological Features

temperature_2m – Air temperature at 2 meters

relative_humidity_2m – Air humidity

wind_speed_10m – Wind speed at 10 meters

shortwave_radiation – Sunlight intensity

3. Data Preprocessing

Missing values were imputed using column-wise means.

Key pollutant and meteorological features were selected; final models focused primarily on pollutant features.

StandardScaler was applied to normalize features, ensuring equal contribution during model training.

4. Exploratory Data Analysis (EDA)

Correlation heatmaps were used to visualize relationships between features and the main_aqi target.

5. Model Building & Evaluation

The dataset was split into training (80%) and testing (20%) sets with random_state=42.

Models Used

Linear Regression

Ridge Regression

Lasso Regression

Random Forest Regressor

Gradient Boosting Regressor

Support Vector Regressor (SVR)

Evaluation Metrics

R² Score: Explains the proportion of variance in AQI predicted by the model.

Mean Absolute Error (MAE): Measures the average magnitude of errors.

Model Performance (R² Score)
Model	R² Score
Random Forest	0.92
Gradient Boosting	0.90
SVR	0.85
Linear Regression	0.31
Ridge Regression	0.31
Lasso Regression	0.28
Key Findings from Linear Regression Coefficients
Feature	Impact
components_pm10	0.66
components_no2	0.26
components_so2	0.14
components_o3	0.08
temperature_2m	-0.02
relative_humidity_2m	-0.04
components_co	-0.14
components_pm2_5	-0.23

Residual analysis confirmed assumptions of linearity and homoscedasticity.

6. Conclusion

Random Forest Regressor achieved the highest performance (R² ≈ 0.92).

Gradient Boosting and SVR also performed well.

Linear, Ridge, and Lasso Regression models showed lower accuracy, highlighting non-linear relationships in AQI data.

This framework can be extended with advanced feature engineering, hyperparameter tuning, and deep learning techniques for improved AQI prediction.

7. How to Run the Notebook

Clone the repository:

git clone <repository_url>
cd <repository_name>

Download the dataset (archive (6).zip) to your project directory.

Open the .ipynb file in Google Colab.

Run all cells sequentially to reproduce preprocessing, training, and evaluation steps.
