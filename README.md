

# AI-Powered Sales Forecasting Dashboard (FUTURE\_ML\_01)

## Project Overview

This project focuses on developing an AI-powered dashboard to predict future sales trends using historical sales data. As part of the Future Interns Machine Learning program, this task demonstrates proficiency in time series forecasting, data analysis, and dashboard visualization. The primary goal is to build a robust model that can accurately forecast sales and present these predictions with clear insights.

## Data Source

The dataset used for this project is:

  * **Dataset Name:** Walmart Data Analysis and Forcasting.csv

The dataset contains historical sales information, including weekly sales, date, and other relevant features.

## Methodology

The project followed a standard machine learning pipeline for time series forecasting:

### 1\. Data Preprocessing & Exploratory Data Analysis (EDA)

  * **Loading Data:** The raw CSV file was loaded into a Pandas DataFrame.
  * **Date Handling:** The 'Date' column was converted to datetime objects and set as the DataFrame's index to facilitate time-series operations.
  * **Data Cleaning:** Checked for and handled any missing values to ensure data integrity.
  * **Time Series Decomposition:** The sales time series was decomposed into its trend, seasonal, and residual components to understand underlying patterns (e.g., weekly, yearly seasonality, and overall trend).
  * **Initial Visualization:** Visualized raw sales data over time to identify preliminary trends, seasonality, and any anomalies.

### 2\. Model Development (Sales Forecasting)

  * **Model Selection:** The **Facebook Prophet** library was chosen for forecasting due to its robust capabilities in handling business time series data with strong seasonal effects and holidays.
  * **Data Preparation for Prophet:** The DataFrame was formatted to Prophet's required `ds` (datestamp) and `y` (target value - sales) columns.
  * **Model Training:** The Prophet model was trained on a portion of the historical data (training set) to learn the patterns.
  * **Forecasting Future Sales:** The trained model was then used to predict sales for a future period, generating point forecasts and uncertainty intervals.

### 3\. Model Evaluation

  * **Time-Series Split:** The historical data was chronologically split into a training set and a test set (e.g., last X months/weeks reserved for testing).
  * **Prediction on Test Set:** The model predicted sales for the unseen test period.
  * **Metric Calculation:** Key regression metrics were calculated to assess model performance:
      * **Mean Absolute Error (MAE):** [Value you obtained] - Indicates the average absolute difference between actual and predicted sales.
      * **Root Mean Squared Error (RMSE):** [Value you obtained] - Penalizes larger errors more heavily.
      * **Mean Absolute Percentage Error (MAPE):** [Value you obtained]% - Provides error as a percentage, useful for business interpretation.
  * **Visual Comparison:** A plot was generated to visually compare actual sales versus predicted sales during the test period, along with the uncertainty intervals, to understand the model's fit and any areas of weakness.

### 4\. Dashboard & Visualization

  * A series of visualizations were created to present the forecasting results. These include:
      * Plots showing historical sales alongside the future sales forecast.
      * Visualizations of the trend component extracted by Prophet.
      * Visualizations of the weekly seasonality components.
    

## How to Run This Project

To run this project and reproduce the analysis and forecast:

  **Run the Script:**
    ```
    python task1.py
    ```
   
-----
