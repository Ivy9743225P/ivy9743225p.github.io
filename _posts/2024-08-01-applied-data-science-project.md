![image](https://github.com/user-attachments/assets/33b86980-6f82-47dd-8fca-ea5fb0316881)---
layout: post
author: Ivy Loi
title: "Applied Data Science Project"
categories: ITD214
---

<b><u>BUSINESS UNDERSTANDING</u></b> 💬


#### Background:
IJJ Pte Ltd is a medium-sized bank headquartered in Singapore, serving a diverse clientele ranging from individual customers to small and medium enterprises (SMEs). As a growing financial institution, the bank aims to strengthen its market position by leveraging technology and data-driven strategies/insights. 

#### Problem Statement
IJJ Pte Ltd struggles to attract high-value customers, optimize marketing efforts, and address customer complaints, impacting customer loyalty and business growth.

#### Business Goal
To enhance customer retention, improve marketing strategies, and effectively resolve customer complaints for better satisfaction and brand loyalty.

##### Objective 1 : Attract and Retain High-Value Customers (Jimmy)
Utilize customer data analytics to identify and target high-value clients.
##### Objective 2 : Enhance Marketing Performance (Joycelyn)
Implement proven marketing strategies to improve customer engagement (measured by whether a customer has signed up for term deposit in this case).
##### Objective 3 : Analyze customer feedback related to product and services. (Ivy)
Leverage bank review analysis to identify opportunities for enhancing IJJ's product and service offerings, ultimately improving customer experience and driving business growth.

#### Tools 🔨
The tools used to develop the project:
- Jupyter Notebook - Python

#### Work Accomplished 📔
<Objective 3>
Analyze customer feedback related to product and services: Leverage bank review analysis to identify opportunities for enhancing IJJ's product and service offerings, ultimately improving customer experience and driving business growth.


#### Data Review 
Data Collection Sources
Source link: https://www.kaggle.com/code/tanshihjen/sentimentanalysis-bankreviewsdataset/input [Total # of columns: 10 (after cleaning: 6 columns); Total # of rows: 1000]


Acquire/Select Data
Topic: bank reviews 
Selected based on its mixture of positive, neutral and negative reviews
Includes feedback on ratings, review title, rating title to provide more insights on the feedback from each individual 


Data Field Description 
Columns: ‘author’, ‘date’, ‘address’, ‘bank’, ‘rating’, ‘review_title_by_user’, ‘review’, ‘bank_image’,  ‘rating_title_by_user’, ‘useful_count’ 

Data Types: ‘author’ (string), ‘date’ (string), ‘address’(string), ‘bank’ (string), ‘rating’ (number) review_title_by_user’ (string), ‘review’ (string), ‘bank_image’ (string),  ‘rating_title_by_user’ (string), ‘useful_count’ (string)

![image](https://github.com/user-attachments/assets/6c6bcb6a-cad6-4faf-8c4f-57a44c41dec8)


Column Description

-author: The user who authored the review, providing valuable insights into the reviewer's identity and perspective.
-date: The date when the review was submitted, offering a temporal dimension to the dataset and enabling time-based analysis.
-address: The geographical location from which the review was written, contributing to understanding regional trends and variations in banking experiences.
-bank: The user's numerical assessment of the bank's service, indicating user satisfaction on a numerical scale.
-**rating**: The user who authored the review, providing valuable insights into the reviewer's identity and perspective.
-**review_title_by_user**: The user-assigned title to their review, summarizing the essence of their feedback in a concise manner.
-**review**: The detailed content of the user's review about the bank, providing the primary textual data for analysis and insights.
-bank_image: The URL pointing to the bank's logo or image relevant to the review, facilitating visual associations with the bank.
-**rating_title_by_user**: The user-assigned title to their rating, potentially offering additional context to the rating value.
-useful_count: The count of users who found the review helpful, reflecting the impact and usefulness of the review among other users.


**Base information on dataset**
Reviews were gathered from 620 users/individual over a period of 4-5 months.  
Missing values: 4 
There are total of 10 columns and 1000 rows with data points from Rating, Review Title, Review, and Rating Title. These are useful information that can be used in the sentiment analysis. There are some data points that can be meaningless and does not provide much insights for the analysis of feedback.

![image](https://github.com/user-attachments/assets/1051cc24-1f3b-47a1-a3c7-ae0b4acb6263)
![image](https://github.com/user-attachments/assets/db5c3245-0cf6-470d-90f8-a966f52787ab)
![image](https://github.com/user-attachments/assets/0fbdbfa8-a93a-41a7-b8f5-7ed97aa42d4d)

**Words existing in "Review" column (before preprocessing)**

Several prominent words that stand out: "account", "bank", "banking", "service", "good", "mobile", "net", "minimum", "balance", and "charge". Some of these words can be excluded as those words may not be very meaningful for sentiment analysis -> e.g. bank, banking
Based on this word cloud, it can be inferred that the reviews are predominantly positive and focus on core banking services like accounts, general service quality, and specific features like mobile apps.
![image](https://github.com/user-attachments/assets/6132c6ca-2cb0-41f1-b9fb-370fb2251b49)

**Create list of bank review document**
Map the rating titles into sentiments groupings of "positive", "neutral" and "negative" for more simplified analysis. The rationale behind mapping sentiments in the sentiment mapping dictionary is to simplify the process of categorizing and analyzing textual data, specifically reviews, into predefined sentiment categories (e.g., "Positive," "Neutral," "Negative"). 

Below is the sentiment mapping designed to cover clear and well-known expressions of sentiment:
Positive: "Great!", "Blown Away!", "Excellent!", "Pretty good"
Neutral: "Satisfactory", "Just OK", "Expected more“
Negative: "Unacceptable", "Bad", "Really Bad"
![image](https://github.com/user-attachments/assets/d9c402a3-0d14-4eb5-b533-182c4eb121b9)


**Sentiment Distribution**
The dataset is imbalanced, with majority of rows labeled as Positive, followed by Neutral and Negative sentiment which shows most of the customers have positive experiences. 
For Machine Learning model, to avoid biasness from the imbalanced data, some techniques can be used to overcome imbalance dataset. One of them would be Resampling techniques - Oversampling (increase Negative / Neutral samples) or  Undersampling  (reduce Positive samples).
![image](https://github.com/user-attachments/assets/e28975da-5586-43f2-bbd0-434bf263fc2b)


#### Data Cleaning/Transformation 🧼

**Kept relevant columns only** 

![image](https://github.com/user-attachments/assets/d318f157-0ffa-419f-9a39-77128c05525b)
![image](https://github.com/user-attachments/assets/3996a38c-3987-42b6-842e-128f53c4c7a5)


**Removed leading and trailing whitespace for more consistent data format**

![image](https://github.com/user-attachments/assets/87a978d2-5055-413b-b49d-e24540e822d5)
![image](https://github.com/user-attachments/assets/058fea48-ddda-41d1-879a-1d263d5ea2e0)

**Identify duplicates under review column - no duplicates found**

**TBC**

**Mapping for bank names - generalise to one bank**
Defining a mapping for various variations of bank names (in different cases) to the word/string "Bank". This is done to standardise the data for only one bank (IJJ bank) which helps eliminate potential noise, make the reviews less specific (the datapoint is not meaningful for sentiment analyis) to allow more focus on the underlying sentiment/feedback.

![image](https://github.com/user-attachments/assets/e272b318-f5c5-478c-90f8-eb33044714ef)


**Converting the review column to lowercase**

![image](https://github.com/user-attachments/assets/bb32acc1-219e-49a7-8337-d8dc315eeb00)

**Stop words removal**
-Removing stopwords (list of English stopwords from NLTK), kept negation words to help assist in identifying/interpreting sentiment
-Remove irrelevant words (context-specific words likely to appear in both positive & negative reviews) that do not inherently express positive/negative sentiments

![image](https://github.com/user-attachments/assets/138213eb-ab19-4077-adf5-ad819e3e8648)

**Remove punctuation marks from review column**

![image](https://github.com/user-attachments/assets/6640fa3a-588b-4ed5-836f-a2a1b5989f5e)

**Remove numbers from review column**

![image](https://github.com/user-attachments/assets/a9b5893b-664a-4bf9-b189-4af33296be8f)

**POS Tagger + Lemmatization
-Applied POS tagger and lemmatization on review column. It helps with word sense disambiguation and better feature represenation. Used POS tag+lemmatization instead of stemming as lemmatization preserves sentiment nuances and considers the context of words

![image](https://github.com/user-attachments/assets/71e2b7cd-7f40-4520-b751-d8221b900554)

![image](https://github.com/user-attachments/assets/9240875a-3778-4b8b-80cf-ca21c76975a0)

**Displaying the "cleansed" review (review_modified) column

![image](https://github.com/user-attachments/assets/0581d128-d677-4b7c-8379-a049cc0fd127)


#### Data Exploration 👣



### Modelling
XXX Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

### Evaluation
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Recommendation and Analysis
Explain the analysis and recommendations

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## AI Ethics
Discuss the potential data science ethics issues (privacy, fairness, accuracy, accountability, transparency) in your project. 

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Source Codes and Datasets
Upload your model files and dataset into a GitHub repo and add the link here. 
