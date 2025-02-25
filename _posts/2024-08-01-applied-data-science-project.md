---
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
-Reviews were gathered from 620 users/individual over a period of 4-5 months.  
-Missing values: 4 
-There are total of 10 columns and 1000 rows with data points from Rating, Review Title, Review, and Rating Title. These are useful information that can be used in the sentiment analysis. There are some data points that can be meaningless and does not provide much insights for the analysis of feedback.

![image](https://github.com/user-attachments/assets/1051cc24-1f3b-47a1-a3c7-ae0b4acb6263)
![image](https://github.com/user-attachments/assets/db5c3245-0cf6-470d-90f8-a966f52787ab)
![image](https://github.com/user-attachments/assets/0fbdbfa8-a93a-41a7-b8f5-7ed97aa42d4d)

**Words existing in "Review" column (before preprocessing)**

-Several prominent words that stand out: "account", "bank", "banking", "service", "good", "mobile", "net", "minimum", "balance", and "charge". Some of these words can be excluded as those words may not be very meaningful for sentiment analysis -> e.g. bank, banking
-Based on this word cloud, it can be inferred that the reviews are predominantly positive and focus on core banking services like accounts, general service quality, and specific features like mobile apps.
![image](https://github.com/user-attachments/assets/6132c6ca-2cb0-41f1-b9fb-370fb2251b49)

**Create list of bank review document**
-Map the rating titles into sentiments groupings of "positive", "neutral" and "negative" for more simplified analysis. The rationale behind mapping sentiments in the sentiment mapping dictionary is to simplify the process of categorizing and analyzing textual data, specifically reviews, into predefined sentiment categories (e.g., "Positive," "Neutral," "Negative"). 

-Below is the sentiment mapping designed to cover clear and well-known expressions of sentiment:
  -Positive: "Great!", "Blown Away!", "Excellent!", "Pretty good"
  -Neutral: "Satisfactory", "Just OK", "Expected more“
  -Negative: "Unacceptable", "Bad", "Really Bad"
![image](https://github.com/user-attachments/assets/d9c402a3-0d14-4eb5-b533-182c4eb121b9)


**Sentiment Distribution**
-The dataset is imbalanced, with majority of rows labeled as Positive, followed by Neutral and Negative sentiment which shows most of the customers have positive experiences. 
-For Machine Learning model, to avoid biasness from the imbalanced data, some techniques can be used to overcome imbalance dataset. One of them would be Resampling techniques - Oversampling (increase Negative / Neutral samples) or  Undersampling  (reduce Positive samples).
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
-Defining a mapping for various variations of bank names (in different cases) to the word/string "Bank". This is done to standardise the data for only one bank (IJJ bank) which helps eliminate potential noise, make the reviews less specific (the datapoint is not meaningful for sentiment analyis) to allow more focus on the underlying sentiment/feedback.

![image](https://github.com/user-attachments/assets/e272b318-f5c5-478c-90f8-eb33044714ef)


**Converting the review column to lowercase**

![image](https://github.com/user-attachments/assets/a3c49664-c013-49f7-96e4-387fe1cb2732)
![image](https://github.com/user-attachments/assets/ccfba07b-82d4-4f07-8489-edb914e06a2b)


**Stop words removal**
-Removing stopwords (list of English stopwords from NLTK), kept negation words to help assist in identifying/interpreting sentiment
-Remove irrelevant words (context-specific words likely to appear in both positive & negative reviews) that do not inherently express positive/negative sentiments

![image](https://github.com/user-attachments/assets/f2028869-0426-49a7-a23f-f3597aca9034)
![image](https://github.com/user-attachments/assets/f8510447-052e-42a2-9c3e-bdb22733c51d)


**Remove punctuation marks from review column**

![image](https://github.com/user-attachments/assets/1784bb60-4eee-4a3d-825e-708b5bd9ebff)
![image](https://github.com/user-attachments/assets/6a5d39f6-6f23-4b58-9eb7-9368ad4678e1)


**Remove numbers from review column**

![image](https://github.com/user-attachments/assets/80ad4889-3dea-40cc-91ed-3d1fa2a8d51b)
![image](https://github.com/user-attachments/assets/0b15f33d-616f-43fa-ae90-e985a9cd2e97)


**POS Tagger + Lemmatization
-Applied POS tagger and lemmatization on review column. It helps with word sense disambiguation and better feature represenation. Used POS tag+lemmatization instead of stemming as lemmatization preserves sentiment nuances and considers the context of words

![image](https://github.com/user-attachments/assets/71e2b7cd-7f40-4520-b751-d8221b900554)

![image](https://github.com/user-attachments/assets/9240875a-3778-4b8b-80cf-ca21c76975a0)

**Displaying the "cleansed" review (review_modified) column

![image](https://github.com/user-attachments/assets/0581d128-d677-4b7c-8379-a049cc0fd127)


#### Data Exploration 👣

**Words existing in "Review_modified" column**
-Several prominent words that stand out: "account", "bank", "banking", "service", "HDFC", "good", "mobile", "net", "minimum", "balance", and "charge". Some of these words can be excluded as those words are not very meaningful for sentiment analysis -> bank, banking,

-Based on this word cloud, it can be inferred that the reviews are predominantly positive and focus on core banking services like accounts, general service quality, and specific features like mobile apps.

![image](https://github.com/user-attachments/assets/deb7e31d-2409-4409-89c1-ff417cdcbefd)
![image](https://github.com/user-attachments/assets/8250b30f-ddae-4551-8094-3a089de75ec2)


**Overall distribution of rating (by rating score) in 1000 reviews**
-Based on the below chartsm it is observed that the most common rating is 5.0, representing 55% of all reviews. The next most frequent is 4.0, at 25.7%. The distribution is heavily skewed towards positive reviews, with relatively few reviews below 3.0.

![image](https://github.com/user-attachments/assets/e819f898-dbf7-4ab0-a478-ceab47835de2)

**User Review Title**
-Below is a word cloud displaying the common vocabulary used by the user in their review title. The more prominent words are "Good", Service, "Best", etc.
-Apart from "Good" and "Best", other words like "Excellent", "improve", "friendly", "reliable", "safe", and "happy" suggest a positive overall experience or desired aspects of the bank's services.
-While the overall sentiment seems positive, words like "decrease", "worst", and "unhappy" suggest that there might be areas where the bank could improve.**

![image](https://github.com/user-attachments/assets/341f0ffa-ce27-4030-8bc1-3345ced95937)

**User Review Title (with rating < 2.5)**
-Below is a word cloud displaying the common vocabulary used by the user in their review title with rating lower than 2.5. The more prominent negative terms are "improve", "service", "account" with words such as "pathetic", "average", "worst", "headache" which express strong negative emotions and experiences.
-"Customer" is quite prominent, and associated words like "respect", "support", "communication", and "respond" may suggest customer experience problems related to shortcomings in customer service and interactions. The issues appear to be centered around poor service quality, inadequate customer support, and potential problems with account management or specific banking practices.
-The huge size of the word "Need" could suggest a fundamental gap between customer expectations and the bank's current offering hence understanding what specific needs are not being met is crucial for the bank.
-Some actionable insights for IJJ: relook and prioritise on their service improvement and invest in customer service training to improve overall customer experience and satisfaction.

![image](https://github.com/user-attachments/assets/110c3e92-9395-4648-b2c6-34d23c0c6778)

**User Review Title (with rating 4 and 5)**
-For user review title with rating of 4 and 5, below are some of the frequent words observed:

  -Positive Sentiment: "Good," "Excellent," "Best," "Nice," "Satisfactory"
  -Banking Services: "Account," "Savings Account," "Service," "Bank," "Charge," "App"
  -Customer Experience: "Friendly," "Easy Use," "Improve," "Trusted"

![image](https://github.com/user-attachments/assets/0e499c1b-9d08-4673-b2b1-9f4bf55a51d7)

#### Feature Extraction ⛲




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
