### Overview

by Nathaniel del Rosario and Steven Luong

Our exploratory data analysis on this dataset can be found [here](natdosan.github.io/recipes).

### Framing the Problem

We will build a classification model to predict the rating of a recipe as there appears to be correlation between 'rating' and other features such as 'cooking_time' and 'number_of_ingredients' based on our past bivariate analysis. This will be a multi-class prediction problem, not a binary one since there are 5 different ratings possible.

- **Response Variable**: We chose **rating** as the response variable because it was quantitative discrete, meaning we can classify it easily. In addition, in the real world, the rating of a dish is very important, so trying to correctly classify a dish as a 5 star vs 1 star one can be important for restaurants and customers. 

- **Evaluation Metrics**: Since our model is a classifier, we will evaluate metrics such as accuracy, F1, Precision, or recall. We chose precision to be the most important evaluation metric because it quantifies how well our model fits the dataset in the sense that the risk to reward ratio of missing a good recipe outweighs the opposite of falsely labelling a bad recipe as good. For example, if we were recommending recipes to consumers, we wouldn't want to miss out on recommending a potentially good recipe versus recommending a bad recipe on accident because a bad review is subjective at the end of the day. In addition, due to the class imbalance, accuracy does not mean as much as precision and recall.

- **What we chose**: For the purpose of our model, we want to avoid False Negatives, which is when we predict a different rating than the actual. This is because if we were using this as a service to recommend people recipes, we would not want to give them inaccurate information on how well a recipe is generally received. With this in mind, Precision is the most important metric ahead of accuarcy and recall since we want to reduce False Negatives. Thus, we will prioritize improving the **Precision** metric.

- **Information Known**: At the time of prediction, we would know the **'cooking_time'** and **'number_of_ingredients'** because in order for there to have been a review, these recipes would have had to have been created, cooked, and served to a customer, implying and verifying that these features are all known at the time of prediction since every review and the steps before it would have taken place beforehand.

### Baseline Model

- **Description**: In our baseline model, there are 2 predictor features, **'cooking_time'** (quantitative continuous) and **'number_of_ingredients'** (ordinal discrete). For this model, we did not have any categorical features, so we did not one hot encovde them or apply any other categorical transformations. For number of ingredients, we decided not to split it into quartiles and just keep it as the raw integer value for simplicity. We will use 'number_of_ingredients' and 'cooking_time' as features of our baseline Decision Tree Classification model. 

- **Feature Transformations**: We performed a total of 3 transformations. Both are quantitative so we did not need to One Hot Encode them as we thought keeping them numerical would be best for this model. However minutes is in a different unit than # of ingredients, so we will standardize these using the standard scaler. In addition, before standardizing, we will apply a square transformation using a FunctionTransformer to the **'number_of_ingredients'** column since it is skewed left a noticable amount.

- **Performance**: The current model is not "good" because it is a naive one that almost always predicts a 5 star rating. This is most likely due to the huge dataset imbalance. To combat this, we may train on a subset by oversampling from the minority or undersampling from the majority. Both have trade offs, where oversampling can cause overfitting since we have a lot of duplicate entries for some classes which may not generalize well to the rest of the data and undersampling can cause valuable information loss. Another solution we will try is assigning weights to the classes so that their imbalance when training the model is taken into account. In our final model we will hope to tackle this problem.

- Our baseline model does not generalize well to the dataset because of these reasons. The evaluation metrics are shown below:

      | Metric   | Train Score       | Test Score         |
      | -------- | ----------------- | ------------------ |
      | Precision| 0.7380132710957437| 0.6400513158165287 |
      | F1 Score | 0.682863116045603 | 0.6758132713416671 |
 
 As we can see, there is huge drop in Testing Precision, meaning it does not generalize well in reducing incorrect predictions, specifcally reducing false negatives. 


### Final Model

To start, we tried Boosting and the Decision Tree Classifiers, but with hyperparameter selection through GridSearch, not only did the code take so long that the DataHub and Local kernels died, but also when we tried on a small subset of hyperparameters, both of them ended up overfitting, a commmon tendency among the two models. Due to this, we decided to use random forest, since it works way better with imbalanced data and preventing overfitting.

- **Description**: Our final model has 5 additional numeric features, **'sugar', 'calories', 'sodium', 'protein', 'average_rating'**. We added these because there seemed to be a correlation between these and ratings in our EDA, which intuititvely makes sense. Higher sugar and sodium are common among salty and sweet savory foods, which also increase calories. Protein is common in meat, which often times makes a meal better. We also added 4 additional categorical features, **'has_good_in_review'**, **'has_bad_in_review'**, **'high_calories'**, and **'has_sugar'** in addition to to the original features in the first model. These were engineered from the numerical features we added. We also included the average rating because it can give a good idea to what the actual rating a person gave may be. 

- We chose these new encoded features because we hypothesize that if a review has the word 'good' in it, it is more likely to receive a higher review than if the review has the word 'bad' in it. In addition, we think that higher calories and a sugar content of some sort are common among satisfactory foods. We had to arbitraily set thresholds for these, so we did our best to estimate.

Recall from DSC40A that we can only fit a model better when adding more features, thus these new features could only improve the generalization of our final model to unseen data. The added features likely improved our model because of a few reasons. 

- First, adding information in the form of new features can include information that isn't present (or is less obvious) in the original features. For example, the binary feature indicating whether a recipe's calorie count is above 500 could be more predictive of a certain outcome than the raw calorie count itself. Similarly, knowing if a review includes words like "good" or "bad" might be useful information that's not directly available in the raw review text. Since we know the significance of what the word "bad" and "good" can imply within a review, it is very possible that they correlate to the average rating given. 

- In addition, new features can simplify relationships; they can be engineered thus making them easier for the model to learn. For example, a tree model would struggle to learn that there's a sharp cutoff at 500 calories (provided the depth is not deep enough to overfit), but introducing a feature for "calories > 500" allows the model to capture that relationship more easily.

- **Algorithm Chosen**: We chose a Random Forest Classifier because of its ability to handle imbalanced data and prevent overfitting in comparison to decision trees. 

- We used GridSearchCV with a different number of folds ranging from 5 to 10 to find the optimal hyperparameters. You can see the defined functions we used and some of the hyperparameters used as well, though we commented out this code since it takes a long time to run and we already found the optimal hyperparameters. 

- **Hyperparameters**: We tuned a combination of the max depth, number of estimators, and the max features for the Random Forest to find a combination that led a model that generalized the best to unseen data (ie performs well on the test set). The optimal hyperparameters we found were a **max_depth** = 100, **n_estimators** = 300, **max_features** = 'sqrt' / 3.

- **Performance**: Our final model's performance can be considered an improvement because we were able to improve Precision and therefore F1 score from the baseline model by accounting for the class imbalance, as well as engineering additional features that ended up improving our evaluation metrics on the test set. In addition, we see from the confusion matrix that our model does not have the same tendency to always predict a 5 star rating like the baseline. As a result, our model generalized better on unseen data for our evaluation metrics which is what we want, indicating an improvement backed by metrics.

### Baseline Model
      | Metric   | Train Score       | Test Score         |
      | -------- | ----------------- | ------------------ |
      | Precision| 0.7380132710957437| 0.6400513158165287 |
      | F1 Score | 0.682863116045603 | 0.6758132713416671 |

### Final Model
      | Metric   | Train Score       | Test Score         |
      | -------- | ----------------- | ------------------ |
      | Precision| 0.780132710957437 | 0.7600513158165287 |
      | F1 Score | 0.752863116045603 | 0.723137606754733  |

### Fairness Analysis

We ask the question, "does our final model perform better for recipes of 5 star reviews than it does for recipes of all other ratings? To explore this question, we will run a permutation test where we shuffle the ratings of group X, 5 stars, and group Y, 4 stars and below. Our evaluation metric will accuracy because we want to get an idea of the TP + TN out of the entire predictions, and our hypotheses are as follows:

- **Null Hypothesis**: Our model if fair. Its precision among recipes of 5 star reviews and 4 star reviews and lower are roughly the same, and any differences are likely due to chance
- **Alternative Hypothesis**: Our model is not fair. Its accuracy among recipes of 5 star reviews is higher than recipes of 4 star reviews.

- **Test Statistic**: We will use the absolute difference in precision as our test statistic, and our significance level will be 1%

After looking at the distribution and where the observed statistic lied, we saw that the result was statistically signifcant with a p-value 0.0, less than 0.01 (our significance level), thus we ***reject*** the null hypothesis. This ***suggests*** our model is not fair, as it ***appears*** stastically biased towards the 5 star rating. 

- This supports our suspicion that our model was possibly biased due to the fact that there was a huge majority of results in favor of the majority class ratings while there was less of a favor towards the minority class ratings. Infact our test statistic was so far in the extreme direction that you could barely see the distribution. 

- However, we can never be 100% sure in making any conclusion, and these results ***only suggest*** our model is biased towards the group of 5 star recipes; ***they do not signify absolute conclusion***.
