# Twitter Sentiment Analysis - NLP
This initiative aims to analyze and interpret the sentiments expressed in tweets, enabling us to gain valuable insights into public opinion and sentiment trends. By leveraging natural language processing (NLP) techniques, we can categorize tweets into positive, negative, or neutral sentiments. This analysis will help us understand customer emotions, monitor brand reputation, and make informed decisions to enhance engagement and customer satisfaction.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Natural Language Processing](#natural-language-processing)
  - [Install Dependencies](#install-dependencies)
  - [Data collection and Processing](#data-collection-and-processing)
  - [Stemming](#stemming)
  - [Separating feature and target](#separating-feature-and-target)
  - [Split the data Train and Test data](#split-the-data-train-and-test-data)
  - [Convert textual data to numerical](#convert-textual-data-to-numerical)
  - [Model training - Logistic Regression](#model-training---logistic-regression)
  - [Model evaluation - Accuracy score](model-evaluation---accuracy-score)
  - [Saving the trained model](#saving-the-trained-model)
  - [Using the saved model for predictions](#using-the-saved-model-for-predictions)

## Project Overview
**Goals:**

- Leverage NLP techniques to understand and interpret human sentiments on Twitter (X).
- Gain insights into public opinion and sentiment trends to enhance engagement and customer satisfaction.

**Objectives:**

- Collect and preprocess tweets to prepare them for sentiment analysis.
- Develop and apply models to classify tweets into positive, negative, or neutral sentiments.
- Evaluate and visualize the model's performance to extract actionable insights.

**Scope:**

- Data collection from Twitter (X) using APIs or other methods.
- Text preprocessing, including cleaning, tokenization, and normalization.
- Model training, evaluation, and continuous improvement.
- Visualization and reporting of sentiment analysis results.

**Expected Outcomes:**

- Accurate classification of tweets into sentiment categories.
- Valuable insights into public opinion and sentiment trends.
- Improved brand reputation monitoring and customer engagement strategies.
- Data-driven decision-making to enhance customer satisfaction and retention.

## Dataset

This is the [sentiment140 dataset](https://www.kaggle.com/datasets/kazanova/sentiment140). It contains 1,600,000 tweets extracted using the twitter api . The tweets have been annotated (0 = negative, 4 = positive) and they can be used to detect sentiment.

It contains the following 6 fields:

- *target:* the polarity of the tweet (0 = negative, 2 = neutral, 4 = positive)

- *ids:* The id of the tweet

- *date:* the date of the tweet

- *flag:* The query. If there is no query, then this value is NO_QUERY.

- *user:* the user that tweeted

- *text:* the text of the tweet

## Natural Language Processing
### Install Dependencies
Provide a pipeline for performing sentiment analysis on text data using machine learning. It involves preprocessing the text data, extracting features, training a Logistic Regression model, and evaluating its performance.
### Data collection and Processing
Perform the following tasks:

- Download and print common English stopwords.
- Load a dataset from a CSV file and assign column names.
- Check the shape and missing values of the dataset.
- Analyze and update the distribution of the target sentiment labels.

### Stemming
- Define a stemming function to preprocess text by removing non-alphabetic characters, converting to lowercase, splitting into words, removing stopwords, stemming the words, and joining them back into a single string.
- Apply this function to the 'text' column of the DataFrame, creating a new column 'stemmed content' with the processed text.

### Separating feature and target
Prepare the data for machine learning by separating the features (input variables) from the target variable (output variable). The characteristics X include all of the necessary information required to make predictions, whereas y holds the values that the model intends to forecast. This division is a typical strategy in machine learning to help with model training and evaluation.

### Split the data Train and Test data
Split the stemmed text data and sentiment labels into training and testing sets, with 70% of the data used for training and 30% for testing, while maintaining the original distribution of sentiment labels in both sets for balanced and effective model training and evaluation.

### Convert textual data to numerical
This process ensures that both training and testing data are converted into a compatible numerical format for use in machine learning models.
- *TfidfVectorizer* is used to convert text data into numerical features.
- *fit_transform(X_train):* Learns the vocabulary and IDF values from the training data and transforms it into TF-IDF features.
- *transform(X_test):* Transforms the testing data into TF-IDF features using the same vocabulary and IDF values learned from the training data.

### Model training - Logistic Regression
- *LogisticRegression(max_iter=1000):* Initializes the logistic regression model with a maximum of 1000 iterations for optimization.
- *lr.fit(X_train, y_train):* Trains the model on the training data, adjusting the model parameters to best fit the training features and labels.

### Model evaluation - Accuracy score
**Training Data Accuracy:**

- Measures how well the model fits the training data.
- High accuracy here might suggest that the model has learned well from the training data. However, it could also indicate overfitting if the accuracy is significantly higher than on the testing data.

**Testing Data Accuracy:**

- Measures how well the model performs on unseen data.
- This is a more reliable indicator of the model's ability to generalize to new data. A high testing accuracy implies that the model is likely to perform well on real-world data, not just the data it was trained on.

Training accuracy evaluates the model's fit to the training data, while testing accuracy assesses the model's performance on new data.
Comparing these two metrics helps identify issues like overfitting or underfitting and provides insights into the model's robustness and generalization capabilities.

### Saving the trained model
Save the trained logistic regression model to a file using pickle. This is useful for preserving the model so it can be loaded and used later without needing to retrain it. The saved model can be deployed or shared for future use.

### Using the saved model for predictions
**Loading the Model:** 

The model is loaded using pickle.

**Prediction and Evaluation:**

- Predictions are made using the loaded model (loaded).
- For each test instance, the code prints the actual label, makes a prediction, and prints whether the prediction indicates a "Negative Tweet" or "Positive Tweet."
