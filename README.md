![neobank_wallpaper](./Images/neobank_wallpaper.png)

# Predicting the Success of Bank Telemarketing

**Contributor**: Douglas Lu

## Table of Contents
* [Overview](#Overview)
* [Business Problem](#Business-Problem)
* [The Data](#The-Data)
* [Methods](#Methods)
* [Analysis](#Analysis)
* [Results](#Results)
* [Conclusions](#Conclusion)
* [Next Steps](#Next-Steps)
* [Repository Structure](#Repository-Structure)

## Overview

Acquiring new prospects in order to accumulate additional assets under management is one of the key important avenues of growth for a financial institution. As prospects and clients earn a bank's trust, they will become more inclined to deposit their savings with the bank. Once a bank earns the trust of its users, assets become revenue streams as clients begin to venture into opening additional accounts, on top of their savings account, such as brokerage accounts, retirement accounts, line of credits, mortgages, as well as private equity and venture capital accounts. In a world where interest rates are very low, it becomes even more imperative to capture the trust of prospects and clients, as traditional banks and neo-banks compete for assets. 

In today's financial services industry, client data has become another key differentiator for an institution's abiliity to surivive in this hyper-competitve environment. One key way for financial institutions to provide a better overall customer experience for its prospects and clients is to leverage the power of machine learning, specifically when it pertains to prospecting clients and soliciting new financial products while minimzing the intrusive nature of soliciting as well as the time and resources dedicated to soliciting new products.  

![neobank_wallpaper_2](./Images/neobank_wallpaper_2.jpeg)

## Business Problem

Acquiring new prospects in order to accumulate additional assets under management is one of the key important avenues of growth for a financial institution. As prospects and clients earn a bank's trust, they will become more inclined to deposit their savings with the bank. Once a bank earns the trust of its clients, assets become revenue streams as clients begin to venture into opening additional accounts, on top of their savings account, such as brokerage accounts, retirement accounts, line of credits, mortgages, as well as private equity and venture capital accounts. In a world where interest rates are very low, it becomes even more imperative to capture the trust of prospects and clients, as traditional banks and neo-banks compete for assets.

In today's financial services industry, client data has become another key differentiator for an institution's abiliity to surivive in this hyper-competitve environment. One key way for financial institutions to provide a better overall customer experience for its prospects and clients is to leverage the power of machine learning, specifically when it pertains to prospecting clients and soliciting new financial products while also minimzing the intrusive nature of soliciting as well as the time and resources dedicated for telemarketing campaigns.

The core business prolblem at hand relates to building a classfier to predict whether a client will subscribe to a term deposit, with the aim of identifying key features that may drive campaign efficiency. On top of building a predictive classifier, we would also want to determine the key influential factors that drive a prospect or client's decision to subscribe to a term deposit. By building a predictive model and identifying key factors, banks can improve their sales pipeline and increase effciency by reducing time, resources, and costs when reaching out to prospects and clients, while maintaining a non-invasive relationship with all clients. 

## Data

The dataset of this project pertains to direct telemarketing campaigns of a Portuguese banking institution. Information about the bank's client, as well as social and economic attributes, are all captured within this dataset through 41,118 client touchpoints across different 20 features. The objective and goal at hand is to predict and classify whether a client that has been reached out to will subscribe to a bank's term deposit or not. The telemarketing campaigns were based on phone calls made to clients. Oftentimes, more than one point of contact to the same client was required in order to assess if the product (bank term deposit) was subscribed by the client.

Further details of the origins of the data can be found in the link: https://archive.ics.uci.edu/ml/datasets/Bank+Marketing

Citation: [Moro et al., 2014] S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems, Elsevier, 62:22-31, June 2014
**Target Data**: 

Output variable (desired target):
1 - has the client subscribed a term deposit? (binary: "yes","no")

Input variables:
Bank Client Data:
   
1 - age (numeric)

2 - job : type of job (categorical: "admin.","blue-collar","entrepreneur","housemaid","management","retired","self-employed","services","student","technician","unemployed","unknown")
3 - marital : marital status (categorical: "divorced","married","single","unknown"; note: "divorced" means divorced or widowed)

4 - education (categorical: "basic.4y","basic.6y","basic.9y","high.school","illiterate","professional.course","university.degree","unknown")
   
5 - default: has credit in default? (categorical: "no","yes","unknown")
   
6 - housing: has housing loan? (categorical: "no","yes","unknown")
   
7 - loan: has personal loan? (categorical: "no","yes","unknown")
   
related with the last contact of the current campaign:

8 - contact: contact communication type (categorical: "cellular","telephone") 

9 - month: last contact month of year (categorical: "jan", "feb", "mar", ..., "nov", "dec")

10 - day_of_week: last contact day of the week (categorical: "mon","tue","wed","thu","fri")

11 - duration: last contact duration, in seconds (numeric). Important note:  this attribute highly affects the output target (e.g., if duration=0 then y="no"). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.
  
other attributes:
12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
  
13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
  
14 - previous: number of contacts performed before this campaign and for this client (numeric)

15 - poutcome: outcome of the previous marketing campaign (categorical: "failure","nonexistent","success")
  
social and economic context attributes
  
16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)
  
17 - cons.price.idx: consumer price index - monthly indicator (numeric)     

18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)     

19 - euribor3m: euribor 3 month rate - daily indicator (numeric)

20 - nr.employed: number of employees - quarterly indicator (numeric)

## Methods

As the core of this business problem is a classification problem, we will seek to utilize machine learning models including Logistic Regression, Decision Tree, Random Forest Classifier, K-Nearest Neighbors Algorithm, Gradient Boosting, and XG Boost to evaluate our model. 

As a traditional measurement of model performance, accuracy is primarily used as a metric to guage how well a model is doing. However, due to the class imbalance, we will not be using accuracy as our common measurement of model performance as the models will tend to fit the majority class better. Instead, we will use ROC (Receiver Operating Characteristic) and AUC (Area Under Curve) as our performance measurement.

As an alternative metric to accuracy, AUC provides a more appropriate understanding of how well our model is doing, with ROC graphs providing us with a deeper view into our optimal precision-recall tradeoff balances as the ROC curve depicts the true positive rate against the false positive rate of our classification models. While an AUC of 0.5 or 50% is no better than randomly guessing, we aim to achieve an AUC of between 0.5 and 1.0 across our models. We want our models to be able to distinguish clearly between the subscribed and unsubscribed class.

## Analysis

Logistic Regression Model: The first model we will utilize is the Logistic Regression Model, in which we obtained an AUC score of 0.80 on the training data and 0.79 on the validation data. However, we know that there is a class imbalance in our dataset due to most clients not having a term deposit, thus we will subsequently utilize a balanced class weight in our logistic regression model to see if our model improves.

Logistic Regression Balanced Model: After iterating through our logistic regression model, we will now try to add class_weight as balanced to our new logistic regression model. In our balanced class weight model, we obtained an AUC score of 0.714 on the training data and 0.711 on the validation data. Unsurprisingly, our model's predictiability went down after our dataset has been balanced out.

Decision Tree Model: We see that our Decision Tree Model's AUC Score improves greatly when compared to the weighted logistic regression model, with an AUC score of 0.802 and 0.801 for training and testing data. We were also able to begin pick up on the model's feature importances, with the top 3 feature importance being duration, nr.employed, and cons.confidence.index. Let's see if these three feature importance remains the top three for other models.

Random Forest Algorithm Model: We see that our Random Forest Model's AUC Score improves greatly when compared to the previous model, with an AUC score of 0.91 and 0.81 for training and testing data. However, the disparity between the AUC scores also suggests that this model may be overfitting on the data. We were also able to begin pick up on the model's feature importances, with the top 3 feature importance this time around being duration, euribor3m, and nr.employed.

K-Nearest Neighbors Model: We see that our KNN's AUC Score produces an AUC score of 1.0 and a test AUC score of 0.79, suggesting that the model is severly overfitting to the training data.

Gradient Boosting Model: We see that the Gradient Boostin Model's AUC Score improves greatly to 0.825 and 0.801 respectively for training and test data. We were also able to pick up on the model's feature importances, with the top 3 feature importance being duration, nr.employed, and euribor3m. It seems like these three features continue to be one of the more important features across the board. 

XG Boost Model: We see that the XG Boost Model's AUC Score is 0.872 and 0.810 respectively for training and test data. Similar to other models, we were also able to pick up on the model's feature importances, with the top 3 feature importance being nr.emoployed, duration, and pdays_0.

## Results
  
When evaluating across all models deployed for this project, we are able to identify a 0.815 AUC Score for our Random Forest Model, followed by an AUC Score of 0.81 from our XG Boost and an AUC score of 0.802 from our Decision Tree Model. Furthemore, from our top performing model, we were able to identify our top 3 features that we can utilize as a way to further recommend the bank during its next telemarketing campaign. In conclusion, we would recommend the bank to focus on the duration of each call, the 3-month European interest rate, and pay attention to the number of employees working for the firm.

With regards to the duration of each call, we saw that on average, 4 to 5 minutes is spent over the phone speaking with the client. However, we could explore reducing the average call time down to the median call time of 3 minutes.

Secondly, we would like to pay close attention to the 3-month European interest rates and recommend the bank to deploy its telemarketing campaign when interest rates are high.

Lastly, we would recommend the bank to initiate its telemarketing campaign with the help from as many employees as possible. As the bank expands, so should its customer base. While only the first recommendation pertains to the client-base, the second and third recommendation rely more on macroeconomic and economic factors. Contrary to how one might believe that client-specific data may have driven the sucess of obtaining more term deposit subscriptions, macroeconomic and economic factors seem to carry more importance.

## Conclusions

Although the dataset contains a huge class imbalance, by adjusting the scoring method from accuracy to AUC scores allows us to evaluate the dataset with consideration of the class im balance. We've witnessed how machine learning algorithms helps us not only identify and predict which customers are likely to subscribe to a term deposit, but also drew conclusions regarding key features that drive the model. We also saw how iterative the machine learning process is, where features and variables as well as parameters can heavily influence the outcome and performance of each model. 
  
## Next Steps

As always, gathering additional data would help improve the model. Furthermore, exploring additional economic factors, such as the European stock market performance, household discretionary spending, and Portugual's GDP could add additional color to the model. 

In addition, we would also like to take a deeper dive into the three key features and identify different threshold levels of improvement. For instance, what exactly would be the optimal call duration with a client? At what specific range of interest rates should the bank deploy its telemarketing campaign? Lastly, does expanding the bank's employee base contribute to the success of the telemarketing campaign or are there other noises that contribute to this insight? 
  
## Repository Structure

```
├── data <-- bank-additional-full.csv primary data
├──<--- bank-additional-names.txt
├──<--- bank.csv
├── Images <--- Pictures and Screenshots from Online/Internally Generated Sources
├── Main Notebook <-- Primary Notebook: Cleans, Explores, and Models the Data   
├── Presentation.pdf  <-- Presentation Slides
├── README.md 
```
