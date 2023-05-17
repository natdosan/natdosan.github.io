# Recipes and Reviews EDA

This project explores the Recipes and Interactions datasets from food.com. It was originally scraped and used by the authors of [this](https://cseweb.ucsd.edu/~jmcauley/pdfs/emnlp19c.pdf) recommender systems paper.

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


