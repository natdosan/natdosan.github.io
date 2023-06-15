### Overview

Our exploratory data analysis on this dataset can be found [here](natdosan.github.io/recipes).

### Framing the Problem

We will build a classification model to predict the rating of a recipe as there appears to be correlation between 'rating' and other features such as 'cooking_time' and 'number_of_ingredients' based on our past bivariate analysis. This will be a multi-class prediction problem, not a binary one since there are 5 different ratings possible.

- **Response Variable**: We chose **rating** as the response variable because it was quantitative discrete, meaning we can classify it easily. In addition, in the real world, the rating of a dish is very important, so trying to correctly classify a dish as a 5 star vs 1 star one can be important for restaurants and customers. 

- **Evaluation Metrics**: Since our model is a classifier, we will evaluate metrics such as accuracy, F1, Precision, or recall. We chose precision to be the most important evaluation metric because it quantifies how well our model fits the dataset in the sense that the risk to reward ratio of missing a good recipe outweighs the opposite of falsely labelling a bad recipe as good. For example, if we were recommending recipes to consumers, we wouldn't want to miss out on recommending a potentially good recipe versus recommending a bad recipe on accident because a bad review is subjective at the end of the day. 

- For the purpose of our model, we want to avoid False Negatives, which is when we predict a different rating than the actual. This is because if we were using this as a service to recommend people recipes, we would not want to give them inaccurate information on how well a recipe is generally received. With this in mind, Precision is the most important metric ahead of accuarcy and recall since we want to reduce False Negatives. Thus, we will prioritize improving the Precision metric.

- **Information Known**: At the time of prediction, we would know the **'cooking_time'** and **'number_of_ingredients'** because in order for there to have been a review, these recipes would have had to have been created, cooked, and served to a customer, implying and verifying that these features are all known at the time of prediction since every review and the steps before it would have taken place beforehand.

### Baseline Model

- **Description**: In our baseline model, there are 2 predictor features, **'cooking_time'** (quantitative continuous) and **'number_of_ingredients'** (quanitative discrete). For this model, we did not have any categorical features, so we did not one hot encovde them or apply any other categorical transformations. For number of ingredients, we decided not to split it into quartiles and just keep it as the raw integer value for simplicity. We will use 'number_of_ingredients' and 'cooking_time' as features of our baseline Decision Tree Classification model. 

- Both are quantitative so we did not need to One Hot Encode them as we thought keeping them numerical would be best for this model. However minutes is in a different unit than # of ingredients, so we will standardize these using the standard scaler. In addition, before standardizing, we will apply a square transformation using a FunctionTransformer to the **'number_of_ingredients'** column since it is skewed left a noticable amount.

- **Performance**: The current model is not "good" because it is a naive one that almost always predicts a 5 star rating. This is most likely due to the huge dataset imbalance. To combat this, we may train on a subset by oversampling from the minority or undersampling from the majority. Both have trade offs, where oversampling can cause overfitting since we have a lot of duplicate entries for some classes which may not generalize well to the rest of the data and undersampling can cause valuable information loss. In our final model we will hope to tackle this problem.

- Our baseline model does not generalize well to the dataset because of these reasons. The evaluation metrics are shown below:

      | Metric   | Train Score       | Test Score         |
      | -------- | ----------------- | ------------------ |
      | Accuracy | 0.7749922608055168| 0.770068317677199  |
      | Precision| 0.7380132710957437| 0.6400513158165287 |
      | Recall   | 0.7749922608055168| 0.770068317677199  |
      | F1 Score | 0.682863116045603 | 0.6758132713416671 |
 
 As we can see, there is huge drop in Testing Precision, meaning it does not generalize well in reducing incorrect predictions, specifcally reducing false negatives. 


### Final Model

In our final model, we encoded new categorical features such as **'has_good_or_bad_in_review'**, **'high_calories'**, and **'has_sugar'** in addition to to the original features in the first model. 

We chose these new encoded features because we hypothesize that if a review has the word 'good' in it, it is more likely to receive a higher review than if the review has the word 'bad' in it. In addition, we think that higher calories and a sugar content of some sort are common among satisfactory foods. We had to arbitraily set thresholds for these, so we did our best to estimate.

Recall from DSC40A that we can only fit a model better when adding more features, thus these new features could only improve the generalization of our final model to unseen data. The added features likely improved our model because of a few reasons. First, adding information in the form of new features can include information that isn't present (or is less obvious) in the original features. For example, the binary feature indicating whether a recipe's calorie count is above 500 could be more predictive of a certain outcome than the raw calorie count itself. Similarly, knowing if a review includes words like "good" or "bad" might be useful information that's not directly available in the raw review text. Since we know the significance of what the word "bad" and "good" can imply within a review, it is very possible that they correlate to the average rating given. In addition, new features can simplify relationships; they can be engineered thus making them easier for the model to learn. For example, a tree model would struggle to learn that there's a sharp cutoff at 500 calories (provided the depth is not deep enough to overfit), but introducing a feature for "calories > 500" allows the model to capture that relationship more easily.

# TODO : final algorithm and the hyperparameters

### Fairness Analysis
