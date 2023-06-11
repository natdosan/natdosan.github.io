### Overview

Our exploratory data analysis on this dataset can be found [here](natdosan.github.io/recipes).

### Framing the Problem

We will build a classification model to predict the rating of a recipe as there appears to be correlation between 'rating' and other features such as 'cooking_time' and 'number_of_ingredients' based on our past bivariate analysis

We will build a classification model to predict the average rating of a recipe as there appears to be correlation between our response variable, **'rating'** and other features such as **'cooking_time'** and **'number_of_ingredients'** based on our past bivariate analysis. We chose **rating** as the response variable because it was quantitative discrete, meaning we can classify it easily. In addition, in the real world, the rating of a dish is very important, so trying to correctly classify a dish as a 5 star vs 1 star one can be important for restaurants and customers. 

Since our model is a classifier, we will evaluate metrics such as accuracy, F1, Precision, or recall. We chose precision and F1 to be the most important evaluation metrics because both quantify how well our model fits the dataset in the sense that the risk to reward ratio of  missing a good recipe outweighs the opposite of falsely labelling a bad recipe as good. For example, if we were recommending recipes to consumers, we wouldn't want to miss out on recommending a potentially good recipe versus recommending a bad recipe on accident because a bad review is subjective at the end of the day. 

At the time of prediction, we would know the **'cooking_time'** and **'number_of_ingredients'** because in order for there to have been a review, these recipes would have had to have been created, cooked, and served to a customer, implying and verifying that these features are all known at the time of prediction since every review and the steps before it would have taken place beforehand.

### Baseline Model

In our baseline model, there are 2 predictor features, **'cooking_time'** (quantitative continuous) and **'number_of_ingredients'** (quanitative discrete). For this model, we did not have any categorical features, so we did not one hot encovde them or apply any other categorical transformations. For number of ingredients, we decided not to split it into quartiles and just keep it as the raw integer value for simplicity. Our current model is decent because it does not do a terrible job at generalizing unseen data. 

### Final Model

In our final model, we encoded new categorical features such as **'has_good_or_bad_in_review'**, **'high_calories'**, and **'has_sugar'** in addition to to the original features in the first model. 

We chose these new encoded features because we hypothesize that if a review has the word 'good' in it, it is more likely to receive a higher review than if the review has the word 'bad' in it. In addition, we think that higher calories and a sugar content of some sort are common among satisfactory foods. We had to arbitraily set thresholds for these, so we did our best to estimate.

Since we are not dealing with Binary Classification, but rather multiclass, we cannot simply just use 'precision' or 'recall' for our evaluation. In addition we must also consider a weighted, macro, or micro option to specify how to handle the calculations:

- 'micro': Calculate metrics globally by counting the total true positives, false negatives and false positives.
- 'macro': Calculate metrics for each label, and find their unweighted mean. This does not take label imbalance into account.
- 'weighted': Calculate metrics for each label, and find their average weighted by support (the number of true instances for each label).

For our case, since there are label imbalances, we will not use macro. A better approach seems to be weighted, so we will try accuracy, weighted precision, and F1 scores.

Recall from DSC40A that we can only fit a model better when adding more features, thus this could only improve the generalization of our final model to unseen data. The added features likely improved our model because of a few reasons. First, adding information in the form of new features can include information that isn't present (or is less obvious) in the original features. For example, the binary feature indicating whether a recipe's calorie count is above 500 could be more predictive of a certain outcome than the raw calorie count itself. Similarly, knowing if a review includes words like "good" or "bad" might be useful information that's not directly available in the raw review text. In addition, new features can simplify relationships; they can be engineered thus making them easier for the model to learn. For example, a tree model would struggle to learn that there's a sharp cutoff at 500 calories (provided the depth is not deep enough to overfit), but introducing a feature for "calories > 500" allows the model to capture that relationship more easily.

# TODO : final algorithm and the hyperparameters

### Fairness Analysis
