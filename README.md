# Predicting 5-Star Amazon Phone Reviews

## Usage

View this project live <a href="https://mateega.com/review-prediction" target="_blank">here</a>. To run the .rmd file, the dataset, Amazon_Unlocked_Mobile.csv, will need to be downloaded from <a href="https://www.kaggle.com/code/rajatagg/star-rating-prediction-part-1/input" target="_blank">Kaggle</a>.

## Executive Summary

### Summary

This project is completed in R using the following methods: **NLP/text mining, logistic regression, LASSO, PCA, and random forest**.

This project is aimed to predict star ratings of unlocked mobile phones on Amazon.com using machine learning techniques. The Star Rating Prediction dataset from Kaggle is utilized which contains features like product name, product brand, product price, review rating, review text, and the number of votes received a view received. 

The exploratory data analysis revealed insights such as phone price range, review votes distribution, average ratings by brand, and the distribution of phone ratings. A two-category response variable was created to classify reviews as 5-star or non-5-star. A document term matrix (dtm) was generated for review text after preprocessing steps.

A LASSO model was trained on all features, achieving an error rate of approximately 20%. Relevant words associated with 5-star reviews were identified using LASSO and logistic regression. Principal Component Analysis (PCA) was applied but did not improve model performance significantly.

A Random Forest Classification model was implemented on both original and PCA-transformed data, with the non-PCA model outperforming. The Random Forest without PCA achieved the lowest validation error of 5.92%.

In conclusion, the Random Forest model without PCA achieved the highest accuracy of 94.08% on the validation set. This model can effectively predict 5-star phone products on Amazon, assisting users in making informed decisions.

### Goal of the Study 

Surfing Amazon products and reviews to find which products are of the highest quality can often be a stressful and tedious task. This product is aimed to analyze Amazon products and help users understand which products are most likely to suit their needs based on the reviews of products. The intention of this product is to use the text that comprises mobile phone reviews to predict whether a product was given a 5-star review or a sub-5-star review. This will be achieved through text processing and regression methods. Reviews on Amazon tend to skew high so even a 4.5-star average rating can result in a poor product. However, often a product that has 5 stars will satisfy a customer’s expectations. Therefore, we predict for 5-star vs sub-5-star review. 

First, we will clean the dataset and perform EDA to better understand the dataset. We will split the data into train, test, and validation sets and perform PCA analysis to reduce dimensionality. We will fit several prediction models to the data and analyze each model’s accuracy to select the most useful model. By the end, we hope to provide a tool that can be used by Amazon customers to save time and become more satisfied out of their shopping on Amazon.

### Dataset

Data was sourced from the [Kaggle Star Rating Prediction dataset](https://www.kaggle.com/code/rajatagg/star-rating-prediction-part-1/input) to obtain reviews for unlocked mobile phones sold on Amazon.com. Each review contains the following features (possibly null): product name, brand name, phone price, review rating, the review text itself, and number of votes that the review received. Review rating range from 1 to 5. The dataset contains over 414K reviews. 
