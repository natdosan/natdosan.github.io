### Overview

Our exploratory data analysis on this dataset can be found [here](natdosan.github.io/recipes).

### Framing the Problem

We will build a classification model to predict the rating of a recipe as there appears to be correlation between 'rating' and other features such as 'cooking_time' and 'number_of_ingredients' based on our past bivariate analysis

We will build a classification model to predict the average rating of a recipe as there appears to be correlation between our response variable, **'rating'** and other features such as **'cooking_time'** and **'number_of_ingredients'** based on our past bivariate analysis. We chose **rating** as the response variable because it was quantitative discrete, meaning we can classify it easily. In addition, in the real world, the rating of a dish is very important, so trying to correctly classify a dish as a 5 star vs 1 star one can be important for restaurants and customers. 

Since our model is a classifier, we will evaluate metrics such as accuracy, F1, Precision, or recall. We chose precision and F1 to be the most important evaluation metrics because both quantify how well our model fits the dataset in the sense that the risk to reward ratio of  missing a good recipe outweighs the opposite of falsely labelling a bad recipe as good. For example, if we were recommending recipes to consumers, we wouldn't want to miss out on recommending a potentially good recipe versus recommending a bad recipe on accident because a bad review is subjective at the end of the day. 

### Baseline Model

In our baseline model, there are 2 predictor features, **'cooking_time'** (quantitative continuous) and **'number_of_ingredients'** (quanitative discrete). For this model, we did not have any categorical features, so we did not one hot encovde them or apply any other categorical transformations. For number of ingredients, we decided not to split it into quartiles and just keep it as the raw integer value for simplicity. Our current model is decent because it does not do a terrible job at generalizing unseen data. 

### Final Model

In our final model, we encoded new categorical features such as **'has_good_or_bad_in_review'** 
### Fairness Analysis
