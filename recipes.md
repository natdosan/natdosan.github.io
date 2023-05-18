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
9. [Results and Conclusion](#results-and-conclusion)


## Introduction and Question Identification
- Our research question was what is the relationship between cooking time and the number of ingredients? 
- Furthermore, do more ingredients lead to higher ratings (or more positive reviews)
- There are 234429 rows from the dataset after merging the two input csv files. 

This question is important because cooking time is often a deciding factor for whether or not someone decides to eat at home or order food instead. Because of this factor of time being important in our lives, we wanted to see
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

### Univariate Analysis

### Bivariate Analysis

## NMAR Analysis	

### Missingness Dependency	

## Hypothesis Testing	

## Results and Conclusion

### Requirements
- Python 3.8+
- NumPy
- pandas
- plotly

### Contributors

- [Nate del Rosario](https://natdosan.github.io)
- Steven Luong


