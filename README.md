# Data Preprocessing and Preparation for Predictive Modeling

This project involved preparing a dataset containing information on over 34,000 organizations that received funding from a fictional foundation. The goal was to preprocess the data to enable the development of a predictive model. Below is a detailed description of the preprocessing steps:

## Preprocessing Steps

1. **Dropping Non-Beneficial Columns**:
   - Removed columns that were not useful for predictive modeling, either due to high cardinality or irrelevant information.

2. **Analyzing Unique Values**:
   - For columns with more than 10 unique values, specifically `APPLICATION_TYPE` and `CLASSIFICATION`, the number of data points for each unique value was calculated.

3. **Binning Rare Categorical Values**:
   - A cutoff point was chosen to group rare categorical values together:
     - For `APPLICATION_TYPE`, a threshold of 600 was used.
     - For `CLASSIFICATION`, a threshold of 300 was used.
   - Values below these thresholds were combined into a new category called "Other".

4. **Converting Categorical Data to Numeric**:
   - Used `pd.get_dummies()` to one-hot encode categorical variables, converting them into numeric values suitable for modeling.

5. **Splitting Data into Features and Target**:
   - The dataset was divided into:
     - **Features Array (X)**: All predictor variables (44 features after preprocessing).
     - **Target Array (y)**: The target variable, `IS_SUCCESSFUL`, indicating whether an organization was successful in receiving funding.

6. **Train-Test Split**:
   - Used `train_test_split` to divide the data into training and testing sets for model evaluation.

7. **Scaling Data**:
   - Applied `StandardScaler` to scale both the training and testing sets to normalize the feature values, ensuring that all features are on the same scale, which helps many machine learning models perform better.

## Summary of Prepared Data

- **Features**: 44 preprocessed features used as inputs for the model.
- **Target Variable (y)**: `IS_SUCCESSFUL`, indicating whether an organization was successful in receiving funding.
- **Data Splitting**: Data was split into training and testing sets to evaluate model performance.

COMPILING, TRAINING, AND EVALUATING THE MODEL
 - I was able to get around 72% accurancy with my model 
