```markdown
# Air Quality Index (AQI) Prediction using Regression Models

## Project Overview
This project focuses on predicting the Air Quality Index (AQI) in Pakistan using various machine learning regression models. We analyze historical pollutant concentrations and meteorological data from 2021 to 2024 to build and evaluate predictive models, aiming to provide insights for environmental policy-making and public health safety.

## 1. Introduction
Air pollution is a significant environmental and public health concern in Pakistan, especially in major urban centers. The AQI is a crucial indicator for communicating pollution levels and health risks. This project utilizes a range of regression models, including Linear Regression, Ridge, Lasso, Random Forest, Gradient Boosting, and Support Vector Regressor, to predict AQI values.

### 1.1 Problem Statement
High levels of particulate matter ($PM_{2.5}$ and $PM_{10}$) and toxic gases like $NO_2$ and $CO$ contribute to severe respiratory issues and seasonal smog. Accurate AQI prediction is vital for governmental policy-making and public health initiatives.

### 1.2 Objectives
- **Develop Predictive Models**: Build robust regression models capable of predicting AQI based on environmental pollutants and weather features.
- **Analyze Pollutant Impact**: Identify which specific pollutants ($PM_{2.5}$, $SO_2$, $NO_2$, etc.) have the most significant impact on the overall AQI.
- **Study Weather Relationships**: Investigate how meteorological factors (temperature, humidity, wind speed) correlate with pollution levels.
- **Evaluate Model Reliability**: Use statistical metrics (MAE, R-squared) to validate the models' accuracy.
- **Provide Data-Driven Insights**: Offer interpretable results to aid in understanding pollution trends for regulatory analysis.

## 2. Dataset Description
The dataset comprises historical air quality and meteorological data for Pakistan from August 2021 to July 2024.

### Target Variable
- **`main_aqi`**: The overall numerical indicator of air quality (Target variable).

### Pollutant Components (Input Features)
- **`components_pm2_5`**: Fine Particulate Matter (< 2.5 µm).
- **`components_pm10`**: Coarse Particulate Matter (< 10 µm).
- **`components_no2`**: Nitrogen Dioxide.
- **`components_so2`**: Sulfur Dioxide.
- **`components_co`**: Carbon Monoxide.
- **`components_o3`**: Ozone.
- **`components_nh3`**: Ammonia.

### Meteorological Features
- **`temperature_2m`**: Air temperature measured 2 meters above ground.
- **`relative_humidity_2m`**: Moisture level in the air.
- **`wind_speed_10m`**: Wind speed at 10 meters height.
- **`shortwave_radiation`**: Intensity of sunlight.

## 3. Data Preprocessing
- **Missing Values**: Handled by filling `NaN` values with the mean of their respective columns.
- **Feature Selection**: Initially, a subset of key pollutant and meteorological features were selected for modeling. For the final model comparison, only pollutant features were used.
- **Feature Scaling**: Applied `StandardScaler` to normalize the features, ensuring equal contribution from all features during model training.

## 4. Exploratory Data Analysis (EDA)
A correlation heatmap was generated to visualize the relationships between the selected features and the `main_aqi` target variable, providing initial insights into pollutant impact.

![Correlation Heatmap](https://raw.githubusercontent.com/user/repo/main/images/correlation_heatmap.png) <!-- Replace with actual image URL if you upload it -->

## 5. Model Building and Evaluation
Several regression models were trained and evaluated to predict AQI. The dataset was split into training and testing sets (80/20 split) with `random_state=42` for reproducibility.

### Models Used:
- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regressor
- Gradient Boosting Regressor
- Support Vector Regressor (SVR)

### Evaluation Metrics
- **R² Score**: Measures the proportion of variance in the dependent variable that can be predicted from the independent variables.
- **Mean Absolute Error (MAE)**: The average of the absolute errors.

### Model Performance (R² Score)
| Model                 | R² Score |
| :-------------------- | :------- |
| Random Forest         | 0.92     |
| Gradient Boosting     | 0.90     |
| SVR                   | 0.85     |
| Linear Regression     | 0.31     |
| Ridge Regression      | 0.31     |
| Lasso Regression      | 0.28     |

### Key Findings from Linear Regression Coefficients:
For the initial Linear Regression model, the impact of features was analyzed based on their coefficients after scaling. 

| Feature              | Impact   |
| :------------------- | :------- |
| `components_pm10`    | 0.66     |
| `components_no2`     | 0.26     |
| `components_so2`     | 0.14     |
| `components_o3`      | 0.08     |
| `temperature_2m`     | -0.02    |
| `relative_humidity_2m`| -0.04    |
| `components_co`      | -0.14    |
| `components_pm2_5`   | -0.23    |

### Residual Analysis
Residual plots were used to check the assumptions of linearity and homoscedasticity. The distribution of errors and residuals vs. predictions were visualized.

![Residual Plots](https://raw.githubusercontent.com/user/repo/main/images/residual_plots.png) <!-- Replace with actual image URL if you upload it -->

## 6. Conclusion
The **Random Forest Regressor** demonstrated the highest performance with an R² score of approximately 0.92, indicating its strong capability in predicting AQI values based on the provided pollutant data. Gradient Boosting and SVR also performed well. Simple linear models like Linear, Ridge, and Lasso Regression showed lower predictive power for this dataset, suggesting the non-linear relationships present in air quality data.

This project provides a foundational predictive framework that can be further enhanced with more advanced feature engineering, hyperparameter tuning, and potentially deep learning models for even greater accuracy.

## How to Run the Notebook
1.  **Clone the repository**:
    ```bash
    git clone <repository_url>
    cd <repository_name>
    ```
2.  **Download the dataset**:
    Ensure you have the `archive (6).zip` file in your Colab environment or project directory. The notebook expects it at `/content/archive (6).zip`.
3.  **Open in Google Colab**:
    Upload the `.ipynb` file to Google Colab.
4.  **Run all cells**:
    Execute the cells sequentially to reproduce the data extraction, preprocessing, model training, and evaluation steps.# Air-Quality-Index-Prediction
