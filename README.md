# Customer-Churn-Prediction

## Problem Statement
The problem of customer engagement, retention and churn affects the businesses (Sparkify, in this case) globally. The impact is potential loss of business worth millions in revenue. A successful solution would be to classify vulnerable users before they leave, so that the company can offer them discounts and incentives. Acquiring new customers are generally more expensive than upgrading and satisfying existing customers.

## Product Position Statement
For the companies who wish to retain the customers, Customer Churn Prediction is a churn prediction tool that provides precise customer churn prediction based on the customer logs present with the companies. Unlike other tools which does not take up several critical variables, our product uses customers demographics, their behaviour, app events (logging in, adding a friend) and so on.

## Source of Data
The data has been sourced from Udacity which is about an imaginary music service provider Sparkify, similar to Spotify and Pandora. The given customer's dataset is logs of customers behaviour such as basic information about each user as well as the specific action they have taken at that time.

In this project, our goal is handling a customer churn problem by building predictive model on a medium dataset (~6GB) of customer's activities on the service and attempt to predict customers who will churn based on their past behaviours.

Dataset: [Click here](https://drive.google.com/file/d/16EtjE2Fmo0j8aRPUbIacJT0B-47BIQ63/view?usp=sharing)

## About the dataset
With 543k rows there are 18 columns which are representing customers demographics, app events and so on. As in every company, Sparkify has churn problems and needs to control the churn action. According to the data provided to us the churn rate is 20% in the Sparkify.

1. 18 Features:
+ Artist — which has 17656 unique artists in it
+ Auth — authentication level
+ firstName — first name of the user
+ gender — gender of the user
+ itemInSession — log count in a session
+ length — length of the song played (in seconds)
+ location — user location
+ method — GET or PUT HTTP request method
+ page — page with which user is currently interacting
+ registration — timestamp of user’s registration
+ sessionId — session of the log
+ song — song played by user
+ status — HTTP code of status — 200, 307, 404
+ ts — timestamp of a given interaction
+ userAgent — what user used as streaming service (Mac/Linux/Windows/iPhone/etc.)
+ userId — unique id of the user

2. Rows: 543k rows 

## Exploratory Data Analysis
1. The dataset was imbalanced. SMOTE technoque was used to make it balanced.
2. OS and Browser Distribution: 
  + Most of users opt for Windows as the OS and most of users use Chrome web browser. 
  + iPad has 0 churn rate but proportion of iPad users are very low. 
  + Linux, MacOS, Ubuntu and Windows users has nearly 20% churn rate but iPhone users 60% churn rate. 
  + Maybe there is a problem with user experience. Users who are using Firefox web browser churn rate is nearly 30%. Both OS and Browser attributes can be good predictors for churn.
3. Gender Distribution: There was no significant churn rate difference in Gender.
4. Location: Location can be good estimator because some location has nearly 100% churn rate. 
5. Free vs Paid Customers Distribution: It was interesting that both paid and free customers have nearly same churn rate. We expected that paid customers have high churn rate, but it is not true in this case. 

## Model Results
We implemented Logistic Regression, Random Forest, GBT and Naive Bayes classifiers.

1. Train Time: NaivesBayes is the Best
2. F1 Score: GBTClassifier is the Best
3. Accuracy Score:  GBTClassifier is the Best
4. Precision:  GBTClassifier is slightly higher than the Random Forest
5. Recall: Random Forest as well GBTClassifier produce the same recall time.
6. When we look at the F1 Score,  GBTClassifier beats the others. On the other hand, recall of both  RandomForest and GBTClassifier is 1. It means that both the models caught all churners correctly.

## Conclusion
1. GBTClassifier Churn Prediction model can help Sparkify to identify approx. 98% of the users who would churn.
2. F1 Score: ~98.92%
3. Accuracy: ~98.93%
4. The company can use special promotions or other measures to prevent them from cancelling the service. 
5. Sparkify has two types of customers: Free Tier and Paid Tier. For example company can offer Paid Tier Subscription for 1 month to the Free Tier churner customers with no charge or company can offer promotion to the Paid Customers. These kind of actions provide increasing of customer satisfaction willingly or unwillingly also prevent the customers churn actions.
