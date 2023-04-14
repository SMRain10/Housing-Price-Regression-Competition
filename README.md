# 611_Final_Project
# Sam Rainbow
# UCID 30084292


Predict housing prices using regression models

There are 3 files of interest:
1) 611_Project_v2.ipynb which contains the code and output from when I ran it
2) train.csv the training set from Kaggle that the model is trained and validated on
3) test.csv the testing set from Kaggle used for the competition (is missing the target variable)

In terms of packages I have been using the the same packages that I installed following the ENSF 611 notes at the beginning of the semester
  - scikit - learn version 1.02
  - Python version 3.8.16

Additionally I had to install XGB to use XGBoostedRegressor
  - xgboost version 1.7.3


Interpretation

The aim of this project was to develop a regression model that accurately predicted house prices based on various features provided by the Ames Housing Dataset. The dataset is a Kaggle competition and requires regression techniques to predict the sale price of a house based on various features. The training dataset contains 79 features and 1460 observations. To answer the question in the proposal I completed the following steps:

1. Load and analyze the data
    In this step I loaded the data and got a sense of the data through visualization. I then analyzed the data to determine the best way to deal with missing values. Missing values were decided on a case by case basis depending on how many null values there were, the description of the feature, and if it made sense to replace it with a mean or mode. Furthermore I processed categorical variables (either ordinal encoder, or onehotencoder) and scaled the numerical data due to the large differences found in the numerical values. It was also important to scale since the values in numerical columns were much larger than the encoded columns since OneHotencoder encodes 0 or 1's and OrdinalEncoder encoded numbers 0 through 5. 
2. Choose a model
    I chose to use a linear regression model, random forest regressor, gradient boosting regressor, and XGBRegressor. I chose these models because they are all regression models and are commonly used for regression problems that I learned in ENSF 611.
3. Instantiate model
    In this part I instantiated the models and fit them to the training data. and evaluated the models using a validation set(a portion of the Kaggle training set provided). I then chose the best model and dropped linearregression since it was the poorest model of all four types and tuned the hyperparameters to improve the score.
4. Find the best model
    In this step I tuned the hyperparameters of the best model to improve the score. I looked at each model individually and completed used GridSearchCV to find the best parameters. In order to visualize when I had found the best parameters I utilized a heatmap.
5. Fit the best model to data
    In this step I fit the best model to the training data and evaluated the model on the kaggle website to see how it performed on the test set. I received a score of 0.125 which was in the top 20% of the competition.

Overall I was able to come up with a model that accurately predicted housing prices with the final model being a GradientBoostedRegressor with hyper paramaters tuned and a r2 score of ~0.9 and a RMSE of $27,258.
    
    
Reflection

i. I selected this problem because I wanted to learn more about regression and how to use it to predict values. I also wanted to learn more about the data science process and how to use the tools I learned in ENSF 611 to solve a real world problem. Housing pricing is a large problem, and something we have seen explode since the pandemic started. A large portion of Canadian familes will or hope to own a home. Tools that could predict home values may help potential buyers figure out a fair price for a house, rather than relying on a real estate agent who might be biased. Additonally after researching Kaggle competitions I wanted to learn more about them and test what I had learned in ENSF 611.

ii. I did not deviate from the original proposal other than not having the time to explore a second Kaggle competition which I mentioned I might do if time permitted. While not in my proposal I did not have the time to submit my predictions with my hyper parameters tuned to the Kaggle competition for feedback (but I do plan to submit and refine it more after the semester is over as I enjoyed the exercise and I was able to submit a prediction earlier in the week and achieved a score of 0.14 putting me in the top 25%). I did try to use XGBoosted which I had originally included as a possibility if time allowed and I was able to include this model although it was not my best performer.

iii. The data preprocessing was very challenging - deciding how to treat missing values, encode categorical features with two different encoders and then scaling only the numerical features was difficult. Tuning the models and trying more models is easy and not that time consuming (if you keep the number of parameters low) after the preprocessing has been completed. One thing I learned was that I originally had combined the training set (had a target variable) and testing set (did not have the target variable) and begun preprocessing the two sets together. I realized that this was not a good idea and could introduce bias into the model since in some cases I was applying the mean from all other rows to fill in values in the testing set. While preprocessing both sets may have given me a better score on the training set it could have biased my results.
