# Delivery Time Window Prediction


This project explores whether we can predict **when a parcel will be delivered** (in the morning, afternoon, or evening) using information available before delivery.

The goal is to build a machine learning model that can help logistics teams better understand and anticipate delivery timing. The analysis walks through the full data science process, from exploring the data to building and comparing models, and finally interpreting the results in a way that makes sense for business users.



<p align="center">
  <img src="https://github.com/NextWaveData/delivery-time-window-prediction/blob/main/results/image.png?raw=true" 
</p>

## Dataset

The dataset includes information about individual parcel deliveries, such as:
- how far the parcel travels
- traffic and weather conditions
- the order of deliveries on a driver’s route
- parcel size and weight
- the day of the week

The main question we try to answer is: **Can we use this information to predict whether a delivery will happen in the morning, afternoon, or evening?**

Evening deliveries are less frequent than morning or afternoon ones, so the prediction task is somewhat unbalanced.

## Methodology

The notebook follows a clear workflow that includes:

- **Exploring the data** to understand patterns and check for issues
- **Cleaning and preparing the data** so that models can learn effectively
- **Training and comparing several machine learning models**, including:
  - Logistic Regression  
  - Support Vector Machine (SVM)  
  - Random Forest  
  - XGBoost  
  - CatBoost
- **Looking into the models** to understand which features influence the predictions the most

## Results & Insights

All models achieved similar performance, with **accuracy between 87% and 89%** on the test set.  
The best-performing models were **Logistic Regression** and **Linear SVM**, with Logistic Regression selected as the final model due to its slightly higher macro F1 score (~0.86) and its interpretability.

The most relevant drivers of delivery timing are:
- **delivery sequence** (position in the route)
- **traffic conditions**
- **weekend vs weekday**

Distance has a moderate impact, while parcel size and weight play a minor role.  
Evening deliveries remain the hardest to predict, mainly due to their lower representation in the data.


## Why This Matters

For operations and planning teams, having a model like this can support:
- route optimization
- delivery time estimation for customers
- better planning of workforce and resources

This notebook shows a **structured and repeatable approach** to data analysis and machine learning, and it provides actionable insight into what affects delivery timing the most.

---

