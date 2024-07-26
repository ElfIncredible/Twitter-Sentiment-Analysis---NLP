# Twitter Sentiment Analysis - NLP
This initiative aims to analyze and interpret the sentiments expressed in tweets, enabling us to gain valuable insights into public opinion and sentiment trends. By leveraging natural language processing (NLP) techniques, we can categorize tweets into positive, negative, or neutral sentiments. This analysis will help us understand customer emotions, monitor brand reputation, and make informed decisions to enhance engagement and customer satisfaction.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Natural Language Processing](#natural-language-processing)
  - [Install Dependencies](#install-dependencies)
  - [Data collection and Processing](#data-collection-and-processing)
  - [Stemming](#stemming)

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
