# Recipes and Reviews EDA

This project explores the Recipes and Interactions datasets from food.com. It was originally scraped and used by the authors of [this](https://cseweb.ucsd.edu/~jmcauley/pdfs/emnlp19c.pdf) recommender systems paper.

Instructions and Guidelines can be found [here:](https://dsc80.com/project3/recipes-and-ratings/)

## Table of Contents

1. [Introduction and Question Identification](#introduction-and-question-identification)
2. [Data Cleaning	](#data-cleaning)
3. [Univariate Analysis](#univariate-analysis)
4. [Bivariate Analysis](#bivariate-analysis)
5. [Interesting Aggregates](#interesting-aggregates)
6. [NMAR Analysis](#nmar-analysis)
7. [Missingness Dependency](#missingness-dependency)
8. [Hypothesis Testing](#hypothesis-testing)


## Introduction and Question Identification
- Our research question was what is the relationship between cooking time and the number of ingredients and ratings? 
- There are 234429 rows from the dataset after merging the two input csv files. 

This question is important because cooking time is often a deciding factor for whether or not someone decides to eat at home or order food instead. Because of this factor of time being important in our lives, we wanted to see how cooking time relates to the number of ingredients, as ideally lower cooking time and less ingredients is easier to cook with the dish being more simple. Furthermore, a simpler dish may be more enjoyable to cook and eat, leading to a higher rating.

The features we will be focusing on “name”, “minutes”, “n_steps”, and ”nutrition” . 

| Column Name  | Description |
|--------------|-------------|
| name         | This column contains the name of the recipe. |
| minutes      | This column indicates the amount of time, in minutes, it takes to prepare the recipe. |
| n_ingredients| This column tells the number of ingredients involved in preparing the recipe. |
| rating       | This column indicates the rating the user gave the recipe |
| carbohydrates| This column indicates the carbohydrates content of the recipe (PDV). Derived from the nutrition column. |
| nutrition    | This column originally contained nutritional information as a list in string format, which was subsequently split into individual columns. It includes: calories (#), total fat (PDV), sugar (PDV), sodium (PDV), protein (PDV), saturated fat (PDV), and carbohydrates (PDV). |
| calories     | This column denotes the amount of calories in the recipe. Derived from the nutrition column. |
| total fat    | This column represents the total fat content of the recipe (PDV). Derived from the nutrition column. |
| sugar        | This column details the sugar content of the recipe (PDV). Derived from the nutrition column. |
| sodium       | This column informs about the sodium content of the recipe (PDV). Derived from the nutrition column. |
| protein      | This column tells about the protein content of the recipe (PDV). Derived from the nutrition column. |
| saturated fat| This column reveals the amount of saturated fat in the recipe (PDV). Derived from the nutrition column. |
| carbohydrates| This column indicates the carbohydrates content of the recipe (PDV). Derived from the nutrition column. |

The "nutrition" column contains values that look like lists, but are actually strings that look like lists. We converted the strings into actual lists, and then created columns for every unique value in the respective list. 
For instance, per the data dictionary, each value in the 'nutrition' column contains information in the form "[calories (#), total fat (PDV), sugar (PDV), sodium (PDV), protein (PDV), saturated fat (PDV), and carbohydrates (PDV)]"; Thus, we created individual columns in the new merged dataset titled 'calories', 'total fat', etc.

## Data Cleaning	

1. Since the datasets for the recipes came in both reviews and interactions, we had to merge these to combine the columns into one uniform DataFrame. We did this by first grouping by the id's to get rid of duplicate entries and aggregating by the mean rating per each recipe (not by user), and then merging both the recipes dataset and interactions dataset on the common recipe_ids's.
2. The next step we took was making sure all "missing" values were correctly labelled as NaN and not anything else in the ratings column. This was a reasonable choice because these can shift the mean rating down when in reality they are just missing entries.
3. Next we renamed some columns to be more descriptive and accurate of the data they held. This was important for making our EDA easier for us to understand the data within each column, as some of the column names were very ambiguous in nature.
4. The next step was to address the 'nutrition' column which contained information in the form of a list of each macronutrient. We then assigned columns for each of the new macronutrients and then split the list accordingly, converting the dtypes of each column to a float instead of a string since our values were numeric.
5. The last major step we took to clean the data was to convert the date column dtype from a string to a pandas datatime object, as handling dates as this type would be much easier to work with than handling strings of different length.

Here is the head of the merged DataFrame, with columns of free response removed for readability. 
                                                                                                                                                   
                                                                                                                                                   
| name                                 |   recipe_id |   cooking_time_minutes |   contributor_id | date_of_recipe_submission   |   number_of_steps |   number_of_ingredients |          user_id | date_of_review      |   rating |   average_rating |   calories |   total fat |   sugar |   sodium |   protein |   saturated fat |   carbohydrates |
|:-------------------------------------|------------:|-----------------------:|-----------------:|:----------------------------|------------------:|------------------------:|-----------------:|:--------------------|---------:|-----------------:|-----------:|------------:|--------:|---------:|----------:|----------------:|----------------:|
| 1 brownies in the world    best ever |      333281 |                     40 |           985201 | 2008-10-27 00:00:00         |                10 |                       9 | 386585           | 2008-11-19 00:00:00 |        4 |                4 |      138.4 |          10 |      50 |        3 |         3 |              19 |               6 |
| 1 in canada chocolate chip cookies   |      453467 |                     45 |          1848091 | 2011-04-11 00:00:00         |                12 |                      11 | 424680           | 2012-01-26 00:00:00 |        5 |                5 |      595.1 |          46 |     211 |       22 |        13 |              51 |              26 |
| 412 broccoli casserole               |      306168 |                     40 |            50969 | 2008-05-30 00:00:00         |                 6 |                       9 |  29782           | 2008-12-31 00:00:00 |        5 |                5 |      194.8 |          20 |       6 |       32 |        22 |              36 |               3 |
| 412 broccoli casserole               |      306168 |                     40 |            50969 | 2008-05-30 00:00:00         |                 6 |                       9 |      1.19628e+06 | 2009-04-13 00:00:00 |        5 |                5 |      194.8 |          20 |       6 |       32 |        22 |              36 |               3 |
| 412 broccoli casserole               |      306168 |                     40 |            50969 | 2008-05-30 00:00:00         |                 6 |                       9 | 768828           | 2013-08-02 00:00:00 |        5 |                5 |      194.8 |          20 |       6 |       32 |        22 |              36 |               3 |

### Univariate Analysis

<iframe src="assets/fig_cookingtime.html" width=800 height=600 frameBorder=0></iframe>
- This graph is representative of the cooking times without the extreme, extreme outliers. Emphasis on the double of extreme as there
are still many outliers. Even when we removed anything past 50,000 minutes, the ditribution along the x axis still shows how extreme the outliers were. These were due to people making joke reviews such as "How to preserve your husband" which was not a real recipe.

<iframe src="assets/fig_cookingtime2.html" width=800 height=600 frameBorder=0></iframe>
- This graph is representative of the cooking times almost all outliers. We made the range of the x axis to be within 500 minutes because that is where >98% of the data fell in.
- As we can see, the mean cooking time was around 30-50 minutes.

<iframe src="assets/fig_num_ingredients.html" width=800 height=600 frameBorder=0></iframe>
- This graph is representative of the distribution of number of ingredients per recipe. The mean appears to be around 9-11 ingredients per recipe. This distribution appears to be less 
skewed in comparison to the cooking time distribution.

### Bivariate Analysis

<iframe src="assets/avg_rating_min.html" width=800 height=600 frameBorder=0></iframe>
- This scatter plot comparing the relationship between average rating and cooking time shows that a majority of our data falls in the area of 0 to 100 minutes of cooking time, aligning with the distribution plots. In addition though, we see that even when the cooking time is low, we find that the data points of average rating are above 3.5 stars. This suggest that average rating and cooking time are not necessarily positively or negatively correlated.

<iframe src="assets/avg_num_ingredients.html" width=800 height=600 frameBorder=0></iframe>
- This scatter plot comparing the relationship between average rating and number of ingredients shows that as the number of ingredients increases, the average rating increases. We can see this where there are a lot less reviews below 3 stars as the number of ingredients increases. This does not necessarily imply causation, but from a visual standpoint these variables do appear to be correlated.

### Interesting Aggregates


|   cooking_quart |   average_rating |
|----------------:|-----------------:|
|               0 |          4.71486 |
|               1 |          4.67837 |
|               2 |          4.66697 |
|               3 |          4.66738 |
|               4 |          4.64907 |

|   ingredient_quart |   average_rating |
|-------------------:|-----------------:|
|                  0 |          4.69636 |
|                  1 |          4.6605  |
|                  2 |          4.66143 |
|                  3 |          4.67685 |
|                  4 |          4.68415 |

Both tables were grouped by cooking time quartile and number of ingredients quartiles respectively. We used 5 quartiles and then aggregated using the mean, calling this column 'average rating'. As we can see, the mean across the different quartiles is very significantly close, suggesting that not one single quartile of number of ingredients and cooking time has a mean way higher or lower than another quartile.

## NMAR Analysis	

Recall that observations in a column are not missing at random (NMAR) if the chance that a value is missing depends on the actual missing value or other columns. We think that the missingness in the number of steps, 'number_of_steps' may depend on the 'steps' column because if people do not include any description for the steps, they may also not include the number of steps. To further look into this, some data to collect would be in the description column, as the respondent could have included some information about the steps in the description of a recipe instead.

### Missingness Dependency	

## Hypothesis Testing	

### Recall our question at the start, what is the relationship between the number of ingredients and recipe rating? 

To answer this question we will run a permutation test to discover this relationship. 
Since we want to test whether both groups of recipes have the same distribution, will perform a permutation test and shuffle the columns to make whether the number of ingredients is high or low random. We accomplish this by creating a new column, 'ingredient_class' based off of the number of ingredients for each recipe.
Because the data we have are categorical (low / high ingredient amount) and numerical (rating), we will use the difference between the two group means as our test statistic.

- Null Hypothesis: In the population, recipes that involve a higher number of ingredients and recipes of a lower number of ingredients have the same distribution of rating, and any differences are due to random chance. 

- Alternative Hypothesis: In the population, recipes that involve a higher number of ingredients and recipes of a lower number of ingredients do not have the same distribution of rating, and any differences are not due to random chance alone.

- Our test statistic will be **the difference in group means (mean rating of higher number of ingredients - mean rating of lower number ingredients)** We do not use the absolute value so that positive values point to the Null and Alternative values point to the Alternative

- Significance Level: We choose a = .05 because that means that our test statistic would need to be in the extreme direction with less than a 5% chance of occuring to reject the null.

- Resulting p-value: .257

- Conclusion: We fail to reject the null. This suggests that recipes with a higher number of ingredients have a different distribution than recipes of lower number of ingredients, which makes sense when we refer back to the scatter plot visualization between number of ingredients and rating, where as number of ingredients increased, the number of lower ratings appeared to decreased as there were fewer and fewer points.

### Requirements
- Python 3.8+
- NumPy
- pandas
- plotly

### Contributors

- [Nate del Rosario](https://natdosan.github.io)
- Steven Luong


