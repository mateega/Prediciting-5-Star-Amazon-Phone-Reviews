# Prediciting 5-Star Amazon Phone Reviews

Spencer Mateega, Mehul Suri, Aditya Maddipatla

University of Pennsylvania 

## Usage

To view this project, download the repo as a ZIP, then open the "final_project.html" file in your browser. To run the .rmd file, the dataset, Amazon_Unlocked_Mobile.csv, will need to be downloaded from <a href="https://www.kaggle.com/code/rajatagg/star-rating-prediction-part-1/input" target="_blank">Kaggle</a>.

## Executive Summary

### Goal of the Study

Surfing Amazon products and reviews to find which products are of the highest quality can often be a stressful and tedious task. We wanted to do a project that analyzes amazon products and helps a user understand which products are more likely to suit their needs based on the reviews of that product. Reviews are often lengthy and can also be misconstrued. The dataset we are using has over 414K rows of Amazon reviews about Unlocked Mobile Phones which will provide a healthy training set. Essentially, our goal is to use the text that comprises these reviews to predict whether a product was given a 5 star review or a sub 5 star review on Amazon by the user. This will be done by using text processing and then analyzing the performance of a variety of models that we learned about in class. We know that reviews on Amazon typically skew towards the higher end and having even a 4.5 star average rating can result in a poor product when you get it. However, more often than not a product that is 5 stars will satisfy a customer’s expectations. Therefore, we thought predicting for 5 stars or not 5 stars makes the most sense. The overall flow of our product will be as following. First we will start by loading in and cleaning the dataset by removing nulls, filtering columns, etc. Next, we will perform EDA by analyzing important statistics about the dataset and displaying visuals that help us understand the dataset better. Next, we will move onto the actual prediction component of the project. We will split the data into train, test, and validation sets and then perform PCA analysis to reduce the dimensionality of the dataset. Next we will analyze the fit of several models to the data from what we learned in class. Our goal here is to find a model that best predicts on our data through the various model performance metrics that we use. In the end, we hope to have a tool that can be used by Amazon customers to save time and become more satisfied out of their shopping on Amazon.

### Data 

We chose to use the Star Rating Prediction dataset from Kaggle to obtain Amazon reviews for Unlocked Mobile Phones. Included in the dataset, is the product name, brand name, price of the phone, review rating, the review itself, and the number of votes that the review got. The review rating ranges from 1 to 5 but as mentioned above we formed a new column for if a review was 5 star or not and will use that as our predictor label. Moreover, the dataset contains over 414K of reviews but in order to ensure that our models are about to train within a reasonable amount of time we decided to take phones from the top 20 brands and then chose a random subset of those reviews. We decided to do this reduction because of how long our models were taking to run originally on the entire set. The top 20 brands comprised over 90% of the phone reviews so this made logical sense. Moreover, we dropped all null rows. Now, our data was ready to analyze and work with!

### Analysis

There were two types of models which were used: the random forest model and the LASSO regression model. In addition there were two variations of each model to check if dimensionality reduction increased accuracy: one which used the original dataframe and another which used the first 5 PCAs of the dataframe. The lasso model would be used as a basline model while the random forest would be used as the main model in order to form an accuracy comparision. We thought that the high dimensionality of the data combined with potential non-linear relationships would be better suited by a random forest model which better accounts for those features. Our findings confirmed this hypothesis as we saw that the random forests with and without PCA features outperformed their LASSO counterparts by around 10-15 percent. Additionlly, we found that the use of PCA did not improve accuracy, with the non-PCA models outperforming the PCA models. Overall, the best model was the random forest model using the standard, non-PCA dataframe as its input with an overall testing and validation error of around 6 percent.
