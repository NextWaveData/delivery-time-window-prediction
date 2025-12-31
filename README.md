# delivery-time-window-prediction

This project explores whether it is possible to **predict the delivery time window of a parcel** (morning, afternoon, or evening) using operational, contextual, and package-level information.

The notebook follows an end-to-end data science workflow, starting from exploratory data analysis and data preparation, and moving through model training and interpretation. The main focus is not only on model performance, but also on understanding *which factors actually drive delivery timing*.

## Dataset

The dataset contains parcel-level delivery information with a mix of numerical and categorical features, including:
- distance between origin and destination
- traffic and weather conditions
- delivery sequence within the route
- parcel size and weight
- calendar information derived from the shipping date

The target variable is the **delivery time window** (morning / afternoon / evening).  
Evening deliveries are less frequent, resulting in a moderately imbalanced classification problem.

## Approach

The analysis is structured as follows:
- preliminary data checks and sanity validation
- exploratory data analysis (univariate, correlation, and multivariate)
- data cleaning and feature engineering
- leakage-safe preprocessing using pipelines
- model benchmarking with:
  - Logistic Regression  
  - Linear SVM  
  - Random Forest  
  - XGBoost  
  - CatBoost
- model interpretation using feature importance and SHAP values

## Results & Insights

All models achieved similar performance, with **accuracy between 87% and 89%** on the test set.  
The best-performing models were **Logistic Regression** and **Linear SVM**, with Logistic Regression selected as the final model due to its slightly higher macro F1 score (~0.86) and its interpretability.

The most relevant drivers of delivery timing are:
- **delivery sequence** (position in the route)
- **traffic conditions**
- **weekend vs weekday**

Distance has a moderate impact, while parcel size and weight play a minor role.  
Evening deliveries remain the hardest to predict, mainly due to their lower representation in the data.

## Conclusion

The results show that delivery time windows can be predicted with reasonable reliability using standard machine learning models. Simpler linear models performed on par with more complex approaches, while offering clearer explanations of the underlying patterns.

Overall, the analysis highlights that **operational and contextual factors** matter more than package characteristics when it comes to delivery timing. The notebook documents a structured and reproducible data science process applied to a realistic logistics use case.
