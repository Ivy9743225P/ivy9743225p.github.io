---
layout: post
author: Ivy Loi
title: "Applied Data Science Project"
categories: ITD214
---

## Project Background
Provide an overview of your team's project business goals and objectives and state the objectives that you are working on. 

### BUSINESS UNDERSTANDING 💬

#### Background:
IJJ Pte Ltd is a medium-sized bank headquartered in Singapore, serving a diverse clientele ranging from individual customers to small and medium enterprises (SMEs). As a growing financial institution, the bank aims to strengthen its market position by leveraging technology and data-driven strategies/insights. 

#### Problem Statement
IJJ Pte Ltd struggles to attract high-value customers, optimize marketing efforts, and address customer complaints, impacting customer loyalty and business growth.

#### Business Goal
To enhance customer retention, improve marketing strategies, and effectively resolve customer complaints for better satisfaction and brand loyalty.

![image](https://github.com/user-attachments/assets/ed027e87-12be-4545-baa4-6685cd5660b6)

Below are the three objectives to address above problem in achieving the overall business goal. 
#### Objective 1 : Attract and Retain High-Value Customers (Jimmy)
Utilize customer data analytics to identify and target high-value clients.
#### Objective 2 : Enhance Marketing Performance (Joycelyn)
Implement proven marketing strategies to improve customer engagement (measured by whether a customer has signed up for term deposit in this case).
#### Objective 3 : Analyze customer feedback related to product and services. (Ivy)
Leverage bank review analysis to identify opportunities for enhancing IJJ's product and service offerings, ultimately improving customer experience and driving business growth.

#### Tools 🔨
The tools used to develop the project:
- Jupyter Notebook - Python

This report will focus on objective 3. 

**Objective 3**:
Analyze customer feedback related to product and services: Leverage bank review analysis (using sentiment analysis) to identify opportunities for **enhancing IJJ's product and service offerings**, ultimately **improving customer experience** and **driving business growth**.

![image](https://github.com/user-attachments/assets/dbb7babf-50db-48fe-ac57-957dda20668c)

![image](https://github.com/user-attachments/assets/5b69b294-164c-4edb-8080-e7a2607b8e5a)


## Work Accomplished
Document your work done to accomplish the outcome

### DATA REVIEW 👓
Data Collection Sources
Source link: https://www.kaggle.com/code/tanshihjen/sentimentanalysis-bankreviewsdataset/input
[Total # of columns: 10 (after cleaning: 6 columns); Total # of rows: 1000]


**Acquire/Select Data**
Topic: bank reviews 
Selected based on its mixture of positive, neutral and negative reviews
Includes feedback on ratings, review title, rating title to provide more insights on the feedback from each individual 


**Data Field Description** 
Columns: ‘author’, ‘date’, ‘address’, ‘bank’, ‘rating’, ‘review_title_by_user’, ‘review’, ‘bank_image’,  ‘rating_title_by_user’, ‘useful_count’ 

Data Types: ‘author’ (string), ‘date’ (string), ‘address’(string), ‘bank’ (string), ‘rating’ (number) review_title_by_user’ (string), ‘review’ (string), ‘bank_image’ (string),  ‘rating_title_by_user’ (string), ‘useful_count’ (string)

![image](https://github.com/user-attachments/assets/6c6bcb6a-cad6-4faf-8c4f-57a44c41dec8)


**Column Description**

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

![image](https://github.com/user-attachments/assets/cd76c917-edda-4808-94a6-47ca8a48ad43)

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


### DATA CLEANING & TRANSFORMATION 🧼


**Kept relevant columns only** 

![image](https://github.com/user-attachments/assets/d318f157-0ffa-419f-9a39-77128c05525b)
![image](https://github.com/user-attachments/assets/3996a38c-3987-42b6-842e-128f53c4c7a5)


**Removed leading and trailing whitespace for more consistent data format**

![image](https://github.com/user-attachments/assets/87a978d2-5055-413b-b49d-e24540e822d5)
![image](https://github.com/user-attachments/assets/058fea48-ddda-41d1-879a-1d263d5ea2e0)

**Identify duplicates under review column - no duplicates found**

![image](https://github.com/user-attachments/assets/01702352-91fb-49c7-902a-e75f8a898d80)


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


**POS Tagger + Lemmatization**

-Applied POS tagger and lemmatization on review column. It helps with word sense disambiguation and better feature represenation. Used POS tag+lemmatization instead of stemming as lemmatization preserves sentiment nuances and considers the context of words

![image](https://github.com/user-attachments/assets/71e2b7cd-7f40-4520-b751-d8221b900554)

![image](https://github.com/user-attachments/assets/9240875a-3778-4b8b-80cf-ca21c76975a0)

**Displaying the "cleansed" review (review_modified) column

![image](https://github.com/user-attachments/assets/0581d128-d677-4b7c-8379-a049cc0fd127)

Text Preprocessing/cleansing pipeline:

![image](https://github.com/user-attachments/assets/f44dd44a-f931-4862-b1f4-0428e34a9dbc)


### DATA EXPLORATION 📊

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

### FEATURE EXTRACTION 🧬

**Tokenization & Word Frequency/Occurences**

-Perform text vectorization using Word Frequency/Occurences method by taking the review_modified and calculates the frequency of each word. 
-There are 1,284 different words (vocabulary size) in the entire collection of review_modified. In terms of outcomes, there are total of 26,743 occurrences which is the total number of words across the reviews_modified column, counting repetitions.

![image](https://github.com/user-attachments/assets/bc083744-a4bb-41d5-bef4-d99c763bfec9)

![image](https://github.com/user-attachments/assets/8314d329-d1bc-4933-b810-8ef7852d5a9f)

**Top 10 words by frequency**

![image](https://github.com/user-attachments/assets/ad4e293a-7ac0-45bd-8fe2-f112e91d8d0b)

**Using N-grams as features for sentiment analysis**

-The model not only learns from individual words but also captures relationships between consecutive words, which improves sentiment classification.

![image](https://github.com/user-attachments/assets/833dc2fe-1453-4cd6-8344-3ae90213cffe)


### MODELLING 🗜️

**<u>Model 1.1</u>**
→ Model training for predicting sentiment using multinomial logistic regression based on current dataset (skewed data)

→ Metrics:

  -Showing high accuracy of 0.873
  -Class 2 - positive takes up majority of the class, dominating predictions (precision & recall close to 1.00).
  -Classes 0 and 1 are ignored, as can be observed in 0% recall for Class 0 and Class 1.
  -Macro Avg F1-score (unweighted mean) is low at 0.31, indicating poor performance on minority classes(0 and 1).

![image](https://github.com/user-attachments/assets/886422de-83bf-439f-93ab-279bc27e9e6b)


**<u>Model 1.2</u>**
→ Undersampling (RandomUnderSampler) & Oversampling (SMOTE) to handle imbalance dataset
→ Training and evaluation of logistic regression model on resampled data using undersampling and SMOTE to handle class imbalance. The undersampled data (X_resampled, y_resampled) can then be used to train the machine learning model for sentiment analysis. The key improvement is addressing the class imbalance, which can significantly improve the performance of the model, where positive reviews constitues majority of the class

→ Metrics:

  -Accuracy is at 57% (dropped by 30.3% from 87.3% in the previous imbalanced model)
  -Macro Avg F1-score at 0.40 (improved from 0.31)
  -Better recall for minority classes (0 & 1) but at the cost of overall accuracy.

![image](https://github.com/user-attachments/assets/2c5a4389-b0d4-4351-8dae-01f1887d4cda)

**<u>Model 2.1</u>**
→ Model training for predicting sentiment using Naive Bayes based on current dataset (skewed data)

→ Metrics:

-Overall Accuracy of 87.3%, quite close to the accuracy for multinomial regression model.
-Class 0: precision, recall and F1 score is low at 0, this is the same for Class 1.
-Model performs well on Class 2 with F1 score of 0.93.
-Model is highly biased towards Class 2 as can be observed from the metrics due to imbalanced data

![image](https://github.com/user-attachments/assets/c61e7609-797d-4b3f-9876-f38e54417244)

**<u>Model 2.2</u>**
→ Undersampling (RandomUnderSampler) & Oversampling (SMOTE) to handle imbalance dataset
→ Training and evaluation of Naive Bayes model on resampled data using undersampling and SMOTE to handle class imbalance. The undersampled data (X_resampled, y_resampled) can then be used to train the machine learning model for sentiment analysis. The key improvement is addressing the class imbalance, which can significantly improve the performance of the model, where positive reviews constitues majority of the class

→ Now we have 17 reviews for each sentiment (Negative, Neutral, Positive).

→ Metrics:

-Accuracy is at 57% (dropped by 30.3% from 87.3 in the previous imbalanced model, and increased slightly by 0.7% as compared to multimonial logistics regression model (resampled version).
-This is expected as resampling forces the model to learn from all classes, reducing bias toward the majority class.- Class 0 and 1 now have non-zero F1 scores, meaning the model is at least making some correct predictions for these classes.
-Recall improved for class 1 (0.35), meaning more instances of class 1 are now correctly classified.
-Macro Avg F1-score at 0.40 (improved from 0.31), meaning the model is now more balanced across all classes.


**Hyperparameter tuning need to be applied to help improve the performnce of the imbalanced and resampled data.**

![image](https://github.com/user-attachments/assets/f54eac15-ee2e-484b-87af-29b2a428d9e0)


### HYPERPARAMETER TUNING & MODEL EVALUATION 🧪

Key Takeaways:

✔ Naive Bayes model (imbalance data - tuned) has the highest accuracy (0.87) after hyperparameter tuning of the 4 models above, however, its macro avg F1 score (0.31) shows poor performance in class balance.

✔ Hyperparameter tuning helped Logistic Regression slightly with class balancing but did not significantly improve overall accuracy. No much change for Naive Bayes performance. Class imbalance is still an issue, especially for minority classes (0 and 1). Resampling helps with class balance but lowers overall accuracy.

✔ Best Model for Accuracy would be Naive Bayes (imbalance data -tuned) while best model for detecting minority class would be Logistics Regression Model (resampled data -tuned) with accuracy of 53% and better recall for minority class.

![image](https://github.com/user-attachments/assets/5533db27-2661-4c1a-ab33-83b7f9985668)
![image](https://github.com/user-attachments/assets/65853d00-226f-4f6a-95aa-bd26fc2d7593)


### NEW PREDICTION ⏳

**Predicting new reviews (based on positive, neutral and negative sentiment) to test the 4 models**

→ Applied the same preprocessing steps per training model.

→ Apart from relooking and prioritising on their service improvement and invest in customer service training based on above analysis, IJJ bank can also leverage on the model to predict sentiments and track customer satisfaction over time. It also helps identify pain points where the bank can relate and enable a more proactive outreach to address the issue. The bank reviews can also be used to discover trends and emerging customer needs that can help to guide the development of new products/features that align with customer preferences and pain points.

→ Based on below predictions across all 4 models, Naive Bayes (Resampled data)-Tuned model has the highest number of correct predictions among the 4 models.

  -Logistics Regression (Imbalance data)-Tuned: 33.3% (3 correct out of 9 predictions)
  -Logistics Regression (Resampled data) -Tuned 55.5% (5 correct out of 9 predictions)
  -Naive Bayes (Imbalanced data)-Tune: 33.3% (3 correct out of 9 predictions)
  -Naive Bayes (Resampled data)-Tuned: 67% (6 correct out of 9 predictions) -> Best model among all, slightly better vs LR resampled model

![image](https://github.com/user-attachments/assets/cfc74603-5cd0-4d34-aa5a-f3804dc8d385)


**Models with Resampled data (Logistics Regression and Naive Bayes)**

Generally, the models with resampled data are better at capturing neutral/negative reviews (miniority class) as compared to the models trained with imbalanced data.

Let's compare both resampled models (no major difference in their performance metrics) on more neutral and negative reviews. (10 neutral and 10 negative reviews).

Logistics Regression (Resampled data) -Tuned: 50% (10 correct out of 20 predictions) -> Performed slightly better as compared with NB resampled model
Naive Bayes (Resampled data)-Tuned: 35% (7 correct out of 20 predictions)
We also looked at how these "resampled data" models are predicting on positive bank reviews. as their accuracy on positive reviews could be compromised during the resampling phase. Based on 8 positive reviews:

  -Logistics Regression (Resampled data) -Tuned: 50% (4 correct out of 8 predictions) -> Performed slightly better as compared with NB resampled model
  -Naive Bayes (Resampled data)-Tuned: 37.5% (3 correct out of 8 predictions)

![image](https://github.com/user-attachments/assets/e74f28a3-119c-4730-aad4-0dc211e6ceeb)


### FINAL CONCLUSION & RECCOMENDATION 🕵️

While it is important to predict positive reviews, the identification of neutral and negative reviews are equally or more crucial. In banking, overlooking negative or neutral feedback can have serious consequences (reputational damage, regulatory issues, customer churn). We need to understand customer real feedback and thoughts, to have better overall view of customer sentiment which in the long run build more trust. Identifying negative and neutral feedback is essential for improving customer satisfaction and addressing underlying issues.

In conclusion, <span style="color: orange;""Logistics Regression (Resampled data) -Tuned" model</span> is generally the better option for analyzing bank reviews. It provides a <span style="color: orange;">more balanced approach</span> that prioritizes accuracy and risk mitigation as compared with the other models.

Another alternative would be to <span style="color: brown;">use both models</span> - model with resample data can be used for <span style="color: brown;">internal purpose, risk management and customer/service recovery</span> and model with imbalance data that are good at predicting positive reviews, for <span style="color: brown;">marketing purpose</span>.

![image](https://github.com/user-attachments/assets/a523c973-ca71-47da-b701-b88b98724010)

The next step for IJJ would be to deploy the model for business use.

Deploy model for batch processing or real-time. IJJ can run sentiment analysis on periodic basis on large volume of customer feedback.

From there, identify and categorize the negative sentiments into different groupings to **identify critical areas for improvement - customer services, product issues, new products, loan issues etc**. Mitigation/recommendation can be made on policy based on customer complaints. Training of employees based on interactions and feedback rated negatively by customers. **Tracking of sentiment trends over time** should be implemented to measure service improvement (leverage of visualization tool such as Power BI or Tableau). This will then help with driving customer experience and build trust, in **reducing the likelihood of customer leaving for competitors** (customer feel heard and will more likely to remain loyal).

For the positive reviews, it can be used for marketing/brand building and strengthen customer relationships.

**Marketing/brand building**: IJJ can consider featuring customer testimonials and feedback on bank's website/social media to boost branding and reputation. Identify what customer love in general use these insights to craft marketing messages for marketing campaigns, promote the service/products that frequently mentioned in the positive reviews.

**Strengthen customer relationship**: Sentiment anallysis can also be used to pinpoint services, staffor features that customer appreciate the most. IJJ can replicate them as best practices by training employess based on highly rated customer interactions and consider inviting happy/satisfied customers to exclusive events to build long-term relationships thus encouraging repeated business. From the positive feedback, IJJ can also identify features that customer love and expand them/innovate new products.

By leveraging insights on customer sentiments, IJJ bank can **enhance their marketing strategies**, increase **customer retention** and **stengthen customer relationship**, ultimately **driving business growth**.

![image](https://github.com/user-attachments/assets/ff5112c6-aa32-4482-b301-2bd2dda537ac)

Rationale behind option of models: Logistics Regression and Naive Bayes models: Both are relatively computationally efficient and simple models, suitable for smaller datasets.

IJJ can consider training other models (such as Random Forest, SVM or deep learning models) when the bank reviews dataset becomes larger in future.

This is not a one-time exercise, the commitment to improvement is crucial for IJJ in fostering better customer satisfaction, which is **essential for customer retention**. IJJ also needs to continuously collect customer feedback for more insights and better train the models (and have more balanced dataset) for prediction. Simple cycle-loop that IJJ needs to adopt:

-> Customers provide feedback

-> IJJ analyzes the feedback

-> IJJ takes action to improve

-> IJJ measures the impact of those actions

-> The cycle repeats

![image](https://github.com/user-attachments/assets/e026616e-3f6a-476d-a10e-9ccfac9d33e0)


### AI ETHICS 🤖
Discuss the potential data science ethics issues (privacy, fairness, accuracy, accountability, transparency) in your project. 

#### 1. Privacy
- Sensiive/confidential information that could identify the author (customer) such as names, account details etc.
- During sentiment analysis review, ensure all the reviews are anonymized (remove the author column) as before the analysis.

#### 2. Data Storage & Security
- Storing sensitive review data would require robust security measures to prevent unauthorized access and data breaches.
- Consider implementing access controls, strong encryption, and conduct regular security audits. Important to adhere to data privacy regulations like GDPR etc. 
  
#### 3. Accuracy & Reliability
- Some sentiment analysis models may misinterpret context or sarcasm which could lead to inaccurate sentiment classification
- Evaluate the model performance using diverse test dataset (reviews) to test the model prediction. Continue to collect more feedback and train the model with bigger training dataset.
  Explore using deep learning model such as LSTM and incorporate methods like attention mechanism to understand misclassification and improve model robustness.

#### 4. Accountability
- Incorrectly classified sentiment can affect business decision - such as wrongly flagging a neutral review as negative could lead to unnecesary customer service escalations/damage to brand reputation.
- Consider implementing a human-in-the-loop system where mixed/highly ambiguous sentiments are manually reviewed. Assign someone who is responsible for monitoring and correcting model outputs.

#### 5. Fairness
- Need to be wary if the training data for sentiment analysis model is biased - e.g. overrepresenting cetain demographics leading to unfair treatment of certain groups (model is trained mostly on review from native English speakers, very few exmaples from non-native speakers or gender bias in sentiment predictions)
- Augment the dataset with reviews from a diverse range of language backgrounds. Ensure the training dats is diverse and representative of the bank's customer base.

#### 6. Transparency
- Understandng the model explainability - how the sentiment analysis model arrives at its conclusion. Customer should also be aware and informed about how their review data is being used and for which purpose. 
- Use explainable AI techniques to provide insights into the model's deicion making process, document the model's training data, architecture and performance metrics. Explain how customer feedback data is being used and protected by providing clear and concise privacy policies. Also, it's good to be transparent about the limitations of the sentiment analysis model. 


#### SOURCE CODES & DATASETS ℹ️
Upload your model files and dataset into a GitHub repo and add the link here. 
