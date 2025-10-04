# Seoul Bike Sharing Demand Prediction

## 1. Business Problem

Efficient management of a public bike-sharing system is crucial for urban mobility. The primary challenge is ensuring bike availability aligns with public demand, which fluctuates based on various factors like time of day, weather, and seasonality.

* **Under-supply** leads to customer dissatisfaction when no bikes are available.
* **Over-supply** results in logistical inefficiencies and unnecessary operational costs for redistributing bikes.

This project aims to solve this problem by building a machine learning model to accurately forecast the demand for rented bikes on an hourly basis in Seoul. A reliable prediction model can empower the system's operators to make data-driven decisions for bike allocation and maintenance, ultimately improving service quality and operational efficiency.

## 2. Data Source

The dataset used for this project is the **Seoul Bike Sharing Demand Data Set**, originally published and hosted on the UCI Machine Learning Repository. For this project, the data was sourced from Kaggle, which provides a convenient platform for access and collaboration.

* **Original Academic Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Seoul+Bike+Sharing+Demand)
* **Data Accessed From:** [Kaggle Dataset Link](https://www.kaggle.com/datasets/saurabhshahane/seoul-bike-sharing-demand-dataset) *(You can update this with the exact link you used)*
* **Period:** 2017-2018
* **Features:** The dataset includes 14 features such as `Date`, `Hour`, `Temperature(°C)`, `Humidity(%)`, `Wind speed (m/s)`, `Rainfall(mm)`, `Snowfall (cm)`, `Seasons`, `Holiday`, and the target variable `Rented Bike Count`.

## 3. Project Objectives

The main goal is to predict the `Rented Bike Count` per hour. The project is broken down into the following objectives:

1.  **Exploratory Data Analysis (EDA):** Analyze the dataset to understand the relationships between the features and bike demand. Identify key patterns, trends, and correlations.
2.  **Feature Engineering:** Create new, meaningful features from the existing data to improve model performance (e.g., extracting 'day of the week' or 'month' from the date).
3.  **Model Building:** Train and evaluate several regression models (such as Linear Regression, Random Forest, and Gradient Boosting) to find the best predictor of bike demand.
4.  **Model Evaluation:** Assess the performance of the final model using relevant metrics like Root Mean Squared Error (RMSE) and R-squared (R²).

## 4. Exploratory Data Analysis - Key Findings

The EDA revealed several strong patterns that influence bike rental demand:

* **Hourly Trends:** Demand shows clear peaks during morning (7-9 AM) and evening (5-7 PM) commute hours, corresponding to typical work schedules. Demand is lowest overnight.
    
* **Seasonal Impact:** Bike rentals are highest during Summer and Autumn and significantly lower during the Winter season.
* **Weather Correlation:** Demand is positively correlated with temperature and negatively correlated with humidity, rainfall, and snowfall. Warmer, clearer days see much higher usage.
* **Working vs. Non-Working Days:** Weekdays show strong bimodal (two-peak) patterns, while weekends show a more spread-out, unimodal demand curve peaking in the afternoon.

## 5. Modeling and Evaluation

Several regression models were trained to predict the hourly count of rented bikes. The performance was evaluated based on the **Root Mean Squared Error (RMSE)**, which indicates the average error of the model's predictions in the number of bikes.

The **Gradient Boosting model (XGBoost/LightGBM)** proved to be the most effective, achieving the lowest RMSE on the test set. This indicates its strong ability to capture the complex, non-linear relationships within the data.

The final model achieved an RMSE of 180.41 and an R² of 0.92 on the test data.

## 6. Conclusion and Recommendations

This project successfully developed a machine learning model capable of predicting hourly bike demand with high accuracy. The key drivers of demand were identified as the hour of the day, season, and weather conditions, particularly temperature.

Based on the model's predictive power, the following recommendations can be made to the bike-sharing system operators:

* **Dynamic Rebalancing:** Use the hourly forecast to proactively redistribute bikes from low-demand to high-demand stations ahead of peak hours.
* **Informed Maintenance:** Schedule maintenance and repairs during predicted low-demand periods (e.g., late nights or days with poor weather) to minimize service disruption.
* **Promotional Campaigns:** Launch marketing campaigns or offer discounts during periods that are typically low in demand but have favorable weather, such as weekend mornings.

## 7. Technologies Used

* **Language:** Python
* **Libraries:**
    * Pandas (Data Manipulation)
    * NumPy (Numerical Operations)
    * Matplotlib & Seaborn (Data Visualization)
    * Scikit-learn (Machine Learning & Modeling)
