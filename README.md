# Calorie Burn Prediction

This project focuses on building and fine-tuning machine learning regression models to predict the number of calories burned based on features such as activity duration, heart rate, and other physiological factors. The dataset used for this project contains information about users and their physical activities.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset Description](#dataset-description)
3. [Methodology](#methodology)
4. [Results](#results)

---

## Project Overview
The goal of this project is to accurately predict the calories burned during physical activities using machine learning models. Various models, including Random Forest, Gradient Boosting, and Linear Regression, are trained and evaluated. The project also includes feature importance analysis to identify key factors influencing calorie burn.

## Dataset Description
The dataset (`calories.csv` and `exercise.csv`) contains the following columns:
- **User_id**: Identifier for the user (removed during preprocessing).
- **Gender**: Gender of the user (encoded as numeric values).
- **Age**: Age of the user (in years).
- **Height**: Height of the user (in centimeters).
- **Weight**: Weight of the user (in kilograms).
- **Duration**: Duration of the physical activity (in minutes).
- **Heart_rate**: Average heart rate during the activity (in beats per minute).
- **Body_temp**: Body temperature during the activity (in Celsius).
- **Calories**: Calories burned (target variable).

## Methodology
### 1. Exploratory Data Analysis (EDA):
- **Correlation Heatmap**: Examined relationships between features and the target variable.
- **Pairplot**: Explored relationships between pairs of features.

### 2. Data Preprocessing:
- Dropped unnecessary columns (`User_id`).
- Encoded categorical variables (`Gender`).
- Standardized numerical features to ensure uniform scaling.
- Split the dataset into three sets:
  - **Training Set (70%)**: Used to train the models.
  - **Validation Set (15%)**: Used to evaluate and compare model performance.
  - **Test Set (15%)**: Used for the final evaluation of the best model.

### 3. Model Training and Evaluation:
- Trained the following models:
  - Linear Regression
  - Ridge Regression
  - Lasso Regression
  - Random Forest Regressor
  - Gradient Boosting Regressor
- Chose **Random Forest Regressor** as the best-performing model based on validation performance.
- Performance metrics used:
  - Mean Absolute Error (MAE)
  - Mean Squared Error (MSE)
  - Root Mean Squared Error (RMSE)
  - R-squared (R²)

### 4. Hyperparameter Tuning:
- Used Grid Search to fine-tune Random Forest hyperparameters, optimizing the model for better accuracy.

### 5. Feature Importance Analysis:
- Visualized the contribution of each feature to the model’s predictions.

## Results
### Final Model Performance:
- **Test Set Results:**
  - **MAE**: 1.74
  - **MSE**: 8.06
  - **RMSE**: 2.84
  - **R²**: 1.00

### Insights from Feature Importance:
- **Duration** is the most influential factor in predicting calorie burn.
- Other features, such as `Heart_rate` and `Age`, contribute marginally to the model's performance.
- `Gender`, `Height`, `Weight` and `Body Temperature` appear to contribute negligibly, possibly because their impact is either too small to be significant in this dataset or because they are correlated with other features like `Age` or `Heart Rate`.