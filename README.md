# AI-Powered Sales Forecasting Dashboard (FUTURE_ML_01)

## Project Overview

This project implements an AI-powered dashboard to predict future sales trends using historical sales data. Developed as part of the Future Interns Machine Learning program, this task demonstrates practical skills in time series forecasting, data preprocessing, model evaluation, and data visualization. The primary objective is to build a robust forecasting model and present its predictions and insights in a clear, understandable manner.

## Data Source

The dataset utilized for this project is:
* **Dataset Name:** `Walmart Data Analysis and Forcasting.csv`
* **Source:** Kaggle

This dataset contains historical weekly sales data for Walmart stores, including dates and weekly sales figures, which are crucial for time series analysis.

## Methodology

The project follows a standard machine learning workflow tailored for time series forecasting:

### 1. Data Preprocessing & Exploratory Data Analysis (EDA)

* **Data Loading:** The `Walmart Data Analysis and Forcasting.csv` file was loaded into a Pandas DataFrame.
* **Date Conversion & Indexing:** The 'Date' column was converted from string format (`DD-MM-YYYY`) to datetime objects and then set as the DataFrame's index. The index was sorted chronologically to ensure proper time series analysis.
* **Initial Visualization:** A line plot of 'Weekly_Sales' over time was generated using `matplotlib` to visually inspect overall trends, potential seasonality, and any outliers.
* **Time Series Decomposition:** The `seasonal_decompose` function from `statsmodels` was used to break down the 'Weekly_Sales' time series into its additive trend, weekly seasonality, and residual components. This step provided deeper insights into the underlying patterns of the sales data.

### 2. Model Development (Sales Forecasting)

* **Model Selection:** **Facebook Prophet** was chosen as the forecasting model. Prophet is well-suited for business time series data, handling seasonality, holidays, and trends effectively, and providing interpretable forecasts.
* **Data Preparation:** The DataFrame was prepared for Prophet by renaming the date column to `ds` and the sales column (`Weekly_Sales`) to `y`, as required by the library.
* **Model Initialization:** The Prophet model was initialized with `weekly_seasonality=True` and `daily_seasonality=False`, `yearly_seasonality=False` based on the data's granularity and observed patterns.
* **Model Training:** The Prophet model was fitted using the prepared historical sales data.
* **Future Forecasting:** A future DataFrame was generated for 365 periods beyond the last available date in the dataset, and the model predicted sales for these future dates, including uncertainty intervals.
* **Forecast Visualization:** Prophet's built-in plotting functions were used to visualize the overall forecast (actuals + predictions) and its individual components (trend, seasonality).

### 3. Model Evaluation

* **Time-Series Split:** The historical data was split into a training set (data before '2012-09-01') and a test set (data from '2012-09-01' onwards) to evaluate the model's performance on unseen data while preserving the temporal order.
* **Model Retraining for Evaluation:** A new Prophet model was trained specifically on the training data.
* **Prediction on Test Set:** Predictions were generated for the dates within the test set.
* **Performance Metrics:** The following regression metrics were calculated using `scikit-learn` to quantify the model's accuracy on the test data:
    * **Mean Absolute Error (MAE):** 445319.27
    * **Root Mean Squared Error (RMSE):** 520017.45
    * **Mean Absolute Percentage Error (MAPE):** 66.26%
* **Actual vs. Predicted Visualization:** A plot was created to visually compare the actual sales from the test set against the model's predictions for the same period, including the uncertainty interval, providing a clear visual assessment of the forecast accuracy.


## How to Run This Project

To set up and run this project locally, follow these steps:

  **Clone the Repository:**
    ```bash
    git clone [https://github.com/snehal977/FUTURE_ML_01.git](https://github.com/YourGitHubUsername/FUTURE_ML_01.git)
    cd FUTURE_ML_01
    ```
   

    




    

