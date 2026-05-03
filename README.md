# 🚦 Traffic Flow Prediction - Time Series Analysis

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)


## 📋 Overview
This project focuses on **Time Series Analysis** to predict traffic volume across different hours and days in four different city locations. Using a recurrent neural network approach, we aim to forecast the number of vehicles based on historical traffic data.

## 🛠️ Implementation Steps

### 1. Data Preprocessing
*   **Normalization**: All input data must be normalized to ensure consistent scaling.
*   **Encoding**: Convert various hours and days into a **one-hot encoding** format for the model to process categorical time data effectively.

### 2. Feature Engineering
*   **Lag Variables**: Utilize historical traffic data to estimate traffic at time $t$.
    *   *Lag-1*: Traffic data from the previous hour ($t-1$).
    *   *Lag-24*: Traffic data from the same hour on the previous day ($t-24$).
*   **Moving Average**: Implement moving averages to reduce noise in the dataset. For example, a window size of 3 would use the average traffic from hours $t-1$, $t-2$, and $t-3$.

### 3. Custom GRU Architecture
*   **Manual Construction**: Build a Gated Recurrent Unit (GRU) cell from scratch using basic library functions in **TensorFlow** or **PyTorch** (do not use pre-built cells).
*   **Structure**: Refer to the architecture diagram in explaination document.

### 4. Model Training & Optimization
*   **Stacking**: Combine the custom GRU cells to build the full model.
*   **Hyperparameter Tuning**: 
    *   **Layers**: Experiment with 1-3 layers.
    *   **Hidden Units**: Experiment with 32-256 hidden units per layer.
*   **Regularization**: Implement techniques to prevent overfitting.

## 📈 Evaluation & Results

The project requires several experimental setups for comparative analysis:

*   **Single-Step Prediction (Hourly)**: Predict the traffic for the next hour.
    *   Evaluate using different **Lag** values (previous hour, previous day, previous week) without moving averages.
    *   Evaluate using different **Moving Average** windows.
*   **Multi-Step Prediction (Daily)**: Predict traffic for the next 24 hours.
*   **Metrics**: Model accuracy is assessed using **RMSE** (Root Mean Squared Error).
*   **Visualization**: Generate plots comparing Predicted vs. Actual traffic for hourly, daily, and weekly intervals.

---
