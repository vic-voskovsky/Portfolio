# Project 2: Predicting Ames, Iowa Housing Prices w/ Kaggle Submission :house: 

---
## Project Author:

Vic Voskovsy  - [LinkedIn](https://www.linkedin.com/in/victorvoskovsky)

---
## Executive Summary

- [Mission Statement](#Mission-Statement "Intro")

- [Problem Statement](#Problem-Statement "PS")

- [Data Information](#Data-Information "Data")

- [Data Cleaning](#Data-Cleaning "EDA")

- [Feature Engineering](#Feature-Engineering "EDA")

- [Modeling Results](#Modeling-Results "Models")

- [Key Findings](#Key-Findings "Go to Key-Findings")

- [Whats Next?](#Whats-Next "EDA")

### Mission Statement

Build a prediction model that will utilize historic home sales in Ames Indiana to predict future home sales given similar data criteria.

### Problem Statement

We are in the market to buy a home in Ames, Iowa. We want to build a quick model to predict prices for similar homes to the best of our ability. 

---
### Data Information

Training Set:
- 2051 observations, 80 features

Testing Set:
- 878 observations, 80 features

---

### Data Cleaning

- Rename all columns to more descriptive format.
- Find NULL values. 
- Find data errors. 
- Validate and prepare dataset for binarizing. 

### Feature Engineering 

- Impute NULL values using two techniques. 
1. Impute values based on data dictionary structure. 
1. Impute values based on average sale price given a category. 

---
### Modeling Results

Model 1: Baseline
- Calculated taining/test scores using all available features.

Model 2: Best Correlators
- Calculated scores only using the features with the best correlations. 

---
### Key Findings

- sale_type column had a data collection error.
- The 5 best features were:
  1. total quality.
  1. ames neighborhood.
  1. eterior quality.
  1. ground living square feet.
  1. kitchen quality. 
- Some features predicted only for soem ranges of house values. 
- Using all features scored worse than just using the best. 
- Using the best features was the best with the data and tools i used up to now. 

---
### Whats Next?

- Create a loop function that will binarize all columns automatically based on value_counts. 
- Tools I would like to use in my next version: 
1. Regularization. 
1. Standard Scaling. 
1. Logistic Regression.
1. Lasso method.
1. Logging.
