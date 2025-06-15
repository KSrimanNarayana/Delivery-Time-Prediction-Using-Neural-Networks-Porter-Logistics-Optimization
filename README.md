# Delivery Time Prediction Using Neural Networks – Porter Logistics Optimization

## 🚚 Project Overview

This project is a machine learning-based solution for **Porter**, India's leading intra-city logistics platform, to predict **estimated delivery times** for food orders. Using historical order and logistics data, we train a regression model that can accurately estimate the delivery duration based on several factors such as order details, restaurant location, time of order, and delivery partner availability.

The goal is to improve customer experience and operational efficiency by providing more reliable delivery time estimates.

---

## 📦 Dataset Description

**Dataset Source**: Proprietary Porter data  
Each row in the dataset corresponds to a unique delivery order. Key features include:

- `market_id`: Market identifier
- `created_at`: Order placement timestamp
- `actual_delivery_time`: Delivery completion timestamp
- `store_primary_category`: Restaurant type/category
- `order_protocol`: How the order was placed (platform, phone, etc.)
- `total_items`: Total price of items
- `num_distinct_items`: Number of distinct items
- `min_item_price`, `max_item_price`: Range of item prices
- `total_onshift_partners`, `total_busy_partners`: Real-time delivery partner data
- `total_outstanding_orders`: Orders in queue
- `estimated_store_to_consumer_driving_duration`: Travel time estimate

---

## 🧠 Problem Statement

> Predict the **delivery time** (in minutes) using a **regression model**, primarily a neural network, using order and logistic metadata.  
> Target = `actual_delivery_time - created_at`

---

## 🧪 Project Workflow

### 1. 📊 Data Understanding & Preprocessing
- Loaded dataset and explored data structure
- Converted timestamps to datetime format
- Feature engineered:
  - `delivery_time_minutes` = difference between `actual_delivery_time` and `created_at`
  - Extracted `hour_of_day` and `day_of_week`
- Handled missing values
- Encoded categorical variables

### 2. 📈 Data Visualization
- Countplots and scatterplots for categorical and numerical insights
- Identified and removed outliers
- Re-visualized cleaned data

### 3. ⚙️ Model Preparation
- Train-test split
- Feature scaling using StandardScaler
- Built a baseline regression model using Random Forest for comparison

### 4. 🧠 Neural Network Implementation
- Built a custom neural network using Keras
- Tuned hyperparameters (layers, activations, optimizers, epochs)
- Tracked training/validation losses

---

## 📊 Evaluation Metrics

- **MSE** (Mean Squared Error)
- **RMSE** (Root Mean Squared Error)
- **MAE** (Mean Absolute Error)
- Visualized predictions vs actuals

---

## 🛠️ Tech Stack

- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Scikit-learn (preprocessing, metrics)
- TensorFlow / Keras (neural network)
- Jupyter Notebook

---

## 🏁 Key Takeaways

- Columnar time-series features can enhance regression accuracy
- Feature engineering from timestamps (hour/day) adds contextual relevance
- Simple neural networks can outperform traditional models with proper tuning
- Delivery partner availability and traffic estimates are strong predictors

---

## 📌 Next Steps

- Try advanced models like XGBoost or LSTM for time-aware learning
- Integrate real-time traffic and weather APIs
- Deploy as a REST API for live predictions

---

