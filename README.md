# Predictive Maintenance
Machine learning pipeline for predictive maintenance - forecasting equipment failures from sensor and operational data to enable proactive servicing.

## Project Overview
This project focuses on predicting machine failures using machine learning techniques.

The dataset contains information about different machine operating conditions, including air temperature, process temperature, rotational speed, torque, and tool wear.

The goal of the project is to analyze the relationships between machine parameters and failures, preprocess the data, select relevant features, and develop a machine learning model capable of predicting machine failures.

## Dataset
| Feature | Description |
|---|---|
| UDI | Unique identifier |
| Product ID | Product identifier |
| Type | Type of product |
| Air temperature [K] | Air temperature |
| Process temperature [K] | Process temperature |
| Rotational speed [rpm] | Rotational speed |
| Torque [Nm] | Torque |
| Tool wear [min] | Tool wear |
| Target | Machine failure indicator |

## Exploratory Data Analysis

Exploratory Data Analysis (EDA) was performed to better understand the structure and distribution of the dataset.

The analysis included:

- Checking for missing values
- Inspecting data types
- Analyzing numerical feature distributions
- Detecting potential outliers using boxplots
- Comparing numerical features between machine failure and non-failure cases
- Investigating relationships between features and the target variable
### Feature distributions
![Feature distributions](Images/Air_temperature_dist.png)
![Feature distributions](Images/Process_temperature_dist.png)
![Feature distributions](Images/Rotational_speed_dist.png)
![Feature distributions](Images/Torque.png)

The distributions show that most numerical features have different scales and ranges, which was taken into consideration during preprocessing.

## Data Preprocessing

The following preprocessing steps were performed:

- Removed identifier columns that do not provide useful predictive information.
- Checked for missing values.
- Separated features from the target variable.
- Split the dataset into training and testing sets.
- Standardized numerical features where required.

## Correlation Analysis

- A correlation analysis was performed to better understand the relationships between numerical features and the target variable.

- A correlation heatmap was used to identify highly correlated features and to examine how strongly each feature was associated with the target variable.

- Although some features exhibited moderate correlations, no features were removed from the dataset. Since the dataset contains a relatively small number of predictors, all features were retained for model training to preserve potentially useful information.

- The correlation matrix also helped verify that no pair of features exhibited excessive multicollinearity that would justify removing variables before model training.

![Correlation Analysis](Images/Correlation.png)

## Model Development

Several machine learning models were evaluated for the classification task:

- Logistic Regression
- K-Nearest Neighbors
- Decision Tree
- Random Forest

## Model Evaluation

The models were evaluated using several classification metrics:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.97 | 0.64 | 0.10 | 0.18 |
| KNN | 0.97 | 0.72 | 0.31 | 0.43 |
| Decision Tree | 0.97 | 0.81 | 0.19 | 0.31 |
| Random Forest | 0.89 | 0.22 | 0.93 | 0.36 |

## Results

The Random Forest model achieved the best overall performance among the evaluated models.

The results indicate that machine operating conditions such as torque, rotational speed, and tool wear contain useful information for predicting machine failures.

The final model was selected based on its performance across multiple evaluation metrics rather than accuracy alone.

### Confusion matrix of Random Forest

| | Predicted No | Predicted Yes | 
|---|---|---|
| **Actual No** | 1711 | 221 |
| **Actual Yes** | 5 | 63 |



## Technologies

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Conclusion

This project demonstrates a complete machine learning workflow for predicting machine failures, from exploratory data analysis and preprocessing to feature selection, model training, hyperparameter optimization, and evaluation.

The analysis shows how machine operating conditions can be used to identify patterns associated with machine failures.
