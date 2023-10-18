# Housing Price Prediction using Regression Models

## Project Overview

This project is an exploration of regression techniques to predict house prices based on features provided by the Ames Housing Dataset, a Kaggle competition dataset. The goal is to accurately estimate the sale price of a house using various features. The project employs Python and machine learning libraries to accomplish this task.

### Project Files

The project consists of the following main components:

- [Jupyter Notebook](611_Project_v2.ipynb): This Jupyter Notebook contains the project's code and outputs.
- [Training Data](train.csv): This file serves as the training dataset used to train and validate the regression models.
- [Test Data](test.csv): This file functions as the testing dataset used in the Kaggle competition, and it lacks the target variable.

### Required Packages

The project utilizes the following Python packages:

- Python 3.8.16
- scikit-learn version 1.02
- xgboost version 1.7.3 (installed to use XGBoostedRegressor)

## Project Workflow

The project workflow involves several key steps:

### Data Preprocessing

1. Data is loaded, visualized, and analyzed to gain insights.
2. Missing values are handled based on a case-by-case approach, considering the number of null values, feature descriptions, and the appropriateness of using means or modes for replacement.
3. Categorical variables are processed using either ordinal encoding or one-hot encoding.
4. Numerical data is scaled to account for variations in numerical values.

### Model Selection

Four regression models are considered:
- Linear Regression
- Random Forest Regressor
- Gradient Boosting Regressor
- XGBoosted Regressor
These models are chosen due to their relevance to regression problems and their coverage in ENSF 611.

### Model Fitting

1. Models are instantiated, fitted to the training data, and evaluated using a validation set derived from the Kaggle training set.
2. The best-performing model is selected, and the linear regression model is discarded.

### Hyperparameter Tuning

1. Hyperparameters of the chosen model are tuned to improve the model's performance.
2. GridSearchCV is employed to identify the optimal hyperparameters.
3. A heatmap is used for visualization.

### Model Evaluation

1. The best-tuned model is fitted to the training data.
2. Model performance is evaluated on the Kaggle website using the provided test set.
3. The project achieves a score of 0.125, placing it in the top 20% of the competition.

## Results

The project successfully creates a regression model to predict housing prices. The final model is a Gradient Boosted Regressor with tuned hyperparameters, achieving an R² score of approximately 0.9 and a Root Mean Square Error (RMSE) of $27,258.

This project enables potential buyers and stakeholders to obtain more accurate estimates of house prices, reducing reliance on real estate agents and potentially promoting fair pricing.

## Acknowledgments

This project was undertaken by Sam Rainbow as part of a school assignment. The project remains open for further refinement and optimization, and future submissions are planned to improve its performance in the Kaggle competition.

For further information and to explore the project code, please refer to the `611_Project_v2.ipynb` Jupyter Notebook in this repository.
