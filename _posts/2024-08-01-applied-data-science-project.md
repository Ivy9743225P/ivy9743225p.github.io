---
layout: post
author: Ivy Loi
title: "Applied Data Science Project"
categories: ITD214
---
<u>**BUSINESS UNDERSTANDING**</u>

### Background:
IJJ Pte Ltd is a medium-sized bank headquartered in Singapore, serving a diverse clientele ranging from individual customers to small and medium enterprises (SMEs). As a growing financial institution, the bank aims to strengthen its market position by leveraging technology and data-driven strategies/insights. 

### Problem Statement
IJJ Pte Ltd struggles to attract high-value customers, optimize marketing efforts, and address customer complaints, impacting customer loyalty and business growth.

### Business Goal
To enhance customer retention, improve marketing strategies, and effectively resolve customer complaints for better satisfaction and brand loyalty.

### Objective 1 : Attract and Retain High-Value Customers (Jimmy)
Utilize customer data analytics to identify and target high-value clients.
### Objective 2 : Enhance Marketing Performance (Joycelyn)
Implement proven marketing strategies to improve customer engagement (measured by whether a customer has signed up for term deposit in this case).
### Objective 3 : Analyze customer feedback related to product and services. (Ivy)
Leverage bank review analysis to identify opportunities for enhancing IJJ's product and service offerings, ultimately improving customer experience and driving business growth.



## Work Accomplished
<Objective 3>
Analyze customer feedback related to product and services: Leverage bank review analysis to identify opportunities for enhancing IJJ's product and service offerings, ultimately improving customer experience and driving business growth.
![image](https://github.com/user-attachments/assets/4e35eff3-f43e-4fd2-9b91-66b79ee46ffc)


### Data Preparation
Data Collection Sources
Source link: https://www.kaggle.com/code/tanshihjen/sentimentanalysis-bankreviewsdataset/input [Total # of columns: 10 (after cleaning: 6 columns); Total # of rows: 1000]


Acquire/Select Data
Topic: bank reviews 
Selected based on its mixture of positive, neutral and negative reviews
Includes feedback on ratings, review title, rating title to provide more insights on the feedback from each individual 
![image](https://github.com/user-attachments/assets/afc19da9-6512-454c-a842-b99c8e6f33f2)

Data Field Description
Columns: ‘author’, ‘date’, ‘address’, ‘bank’, ‘rating’, ‘review_title_by_user’, ‘review’, ‘bank_image’,  ‘rating_title_by_user’, ‘useful_count’ 

Data Types: ‘author’ (string), ‘date’ (string), ‘address’(string), ‘bank’ (string), ‘rating’ (number) review_title_by_user’ (string), ‘review’ (string), ‘bank_image’ (string),  ‘rating_title_by_user’ (string), ‘useful_count’ (string)
![image](https://github.com/user-attachments/assets/ba3b5430-ec5e-498e-a731-8d8a66dd3ce7)

![image](https://github.com/user-attachments/assets/2d356bab-3dec-45ab-9372-8e37655336b5)

Column Description

author: The user who authored the review, providing valuable insights into the reviewer's identity and perspective.

date: The date when the review was submitted, offering a temporal dimension to the dataset and enabling time-based analysis.

address: The geographical location from which the review was written, contributing to understanding regional trends and variations in banking experiences.

bank: The user's numerical assessment of the bank's service, indicating user satisfaction on a numerical scale.

**rating**: The user who authored the review, providing valuable insights into the reviewer's identity and perspective.

**review_title_by_user**: The user-assigned title to their review, summarizing the essence of their feedback in a concise manner.

**review**: The detailed content of the user's review about the bank, providing the primary textual data for analysis and insights.

bank_image: The URL pointing to the bank's logo or image relevant to the review, facilitating visual associations with the bank.

**rating_title_by_user**: The user-assigned title to their rating, potentially offering additional context to the rating value.

useful_count: The count of users who found the review helpful, reflecting the impact and usefulness of the review among other users.
![image](https://github.com/user-attachments/assets/320a4eab-f321-4c59-b73a-fc64a6f20132)


**Base information on dataset**
Reviews were gathered from 620 users/individual over a period of 4-5 months.  
Missing values: 4 
There are total of 10 columns and 1000 rows with data points from Rating, Review Title, Review, and Rating Title. These are useful information that can be used in the sentiment analysis. There are some data points that can be meaningless and does not provide much insights for the analysis of feedback.
![image](https://github.com/user-attachments/assets/4accc7dc-8aa9-4332-803f-795a84385125)

![image](https://github.com/user-attachments/assets/1051cc24-1f3b-47a1-a3c7-ae0b4acb6263)
![image](https://github.com/user-attachments/assets/db5c3245-0cf6-470d-90f8-a966f52787ab)
![image](https://github.com/user-attachments/assets/0fbdbfa8-a93a-41a7-b8f5-7ed97aa42d4d)



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
