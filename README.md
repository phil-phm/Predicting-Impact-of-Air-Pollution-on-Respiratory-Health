# Predicting Respiratory Hospital Visits via Air Quality Trends in Taiwan
 
This project explores the correlation between air pollution levels and hospital admissions for respiratory issues in Taiwan. Using a Deep Learning (LSTM) approach, the goal is to predict the number of hospital visits due to respiratory health issues by analyzing historical air quality time-series data in Taiwan.

## Project Overview
Air pollution is a significant environmental risk factor for respiratory diseases. This project utilizes **Long Short-Term Memory (LSTM)** networks to capture the temporal dependencies between pollutant concentrations and subsequent healthcare demands.

* **Objective:** Forecast hospital admission volumes based on multi-dimensional air quality features.
* **Key Approach:** Time-series forecasting with varying **look-back windows** to identify delayed health impacts (lag effects).
* **Target Variable:** Daily/Weekly respiratory-related hospital visits.

## Dataset & Features
The model is trained on a comprehensive set of air quality features:
* **Index:** Air Quality Index (AQI)
* **Gases:** Sulfur dioxide ($SO_2$), Carbon monoxide ($CO$ & $CO_{8hr}$), Ozone ($O_3$ & $O_3$ $8hr$), Nitrogen dioxide ($NO_2$)
* **Particulates:** Particulate matter < 10μm ($PM_{10}$) and < 2.5μm ($PM_{2.5}$)

> **Note on Data Access:** Due to the large file size (~800MB), the raw dataset is hosted on Google Drive. The provided Jupyter Notebook includes a `gdown` script to automatically fetch the data for seamless execution.

## Methodology
1.  **Data Preprocessing:** : Cleaning, merging pollution and hospital records, and normalizing features
2.  **LSTM Architecture:** Designed to handle sequential data, the model consists of LSTM layers followed by Dropout (to prevent overfitting) and Dense output layers for regression (predicting the count of visits).
3.  **Time-Window Experimentation:** We tested multiple time windows (e.g., 1 day, 4 days 7 days, 10 days, 25 days, 50 days) to determine how far back the model needs to "look" to make an accurate prediction.

## Getting Started
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/phil-phm/Predicting-Impact-of-Air-Pollution-on-Respiratory-Health.git](https://github.com/phil-phm/Predicting-Impact-of-Air-Pollution-on-Respiratory-Health.git)
    ```
2.  **Install requirements:**
    ```bash
    pip install pandas numpy matplotlib tensorflow gdown
    ```
3.  **Run the analysis:**
    Open `Air_Pollution_on_Respiratory_Health_Taiwan_LSTM.ipynb` in Jupyter Notebook or Google Colab.

