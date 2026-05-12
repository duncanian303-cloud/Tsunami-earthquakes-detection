# Earthquake-Induced Tsunami Prediction Project

## Overview
This project aims to predict whether an earthquake will trigger a tsunami based on seismic features such as magnitude, depth, and station data. This is a critical classification task for early warning systems and disaster mitigation.

## Dataset
- **Source**: `earthquake_data_tsunami.csv`
- **Features**: Magnitude, depth, CDI (Community Decimal Intensity), MMI (Modified Mercalli Intensity), significance, number of stations (nst), and geographical coordinates.
- **Target**: `tsunami` (Binary: 0 for No, 1 for Yes)

## Workflow
1.  **Exploratory Data Analysis (EDA)**: Analyzed feature correlations and identified that depth and magnitude are key differentiators for tsunami events.
2.  **Preprocessing**: Cleaned the dataset, handled time-based columns, and addressed class imbalance using `scale_pos_weight` and stratified splitting.
3.  **Baseline Modeling**: Evaluated Random Forest and XGBoost classifiers.
4.  **Optimization**: Performed `GridSearchCV` to find the best hyperparameters for the XGBoost model.
5.  **Feature Engineering**: Added an `is_deep` feature (depth >= 70km) based on error analysis to help the model distinguish between shallow and deep-focus events.
6.  **Validation**: Conducted 5-fold cross-validation and detailed misclassification analysis.

## Final Model Performance
- **Model**: Optimized XGBoost Classifier
- **Accuracy**: 90%
- **F1-Score (Tsunami)**: 0.87
- **Recall (Tsunami)**: 89% (Correctly identified most tsunami events)

## Conclusion
The model demonstrates high predictive power. Future improvements could involve integrating real-time oceanic data or distance-from-coastline features to further reduce false negatives in deep-sea seismic events.
