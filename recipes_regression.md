### Overview

Our exploratory data analysis on this dataset can be found [here](natdosan.github.io/recipes).

### Framing the Problem

We will build a regression model to predict the average rating of a recipe as there appears to be correlation between our response variable, **'average_rating'** and other features such as **'cooking_time'** and **'number_of_ingredients'** based on our past bivariate analysis. We will then use RMSE and R^2 to evaluate our model; since it is not a classification model, we cannot use metrics such as accuracy, F1, Precision, or recall. We chose RMSE and R^2 because both quantify how well our model fits the dataset. However they are better than other metrics such as Mean Absolute error since RMSE tells how well the model can predict the value of a response variable in absolute terms and squared making it more robust to outliers, and R^2 tells how well the predictor features explain the variance in the response. It is good to have both to measure the variance and error.

### Baseline Model

In our baseline model, there are two predictor features, **'cooking_time'** (quantitative continuous) and **'number_of_ingredients'** (quanitative discrete). For this model, we did not have any categorical features, so we did not one hot encovde them or apply any other categorical transformations. For number of ingredients, we decided not to split it into quartiles and just keep it as the raw integer value for simplicity.

### Final Model
### Fairness Analysis
