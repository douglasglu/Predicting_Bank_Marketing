# Predicting the Success of Bank Telemarketing

**Collaborators**: Douglas Lu

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

## Business Problem

The core business prolblem at hand relates to building a classfier to predict whether a client will subscribe to a term deposit. On top of building a predictive classifier, we would also want to determine the key influential factors that drive a prospect or client's decision to subscribe to a term deposit. By building a predictive model and identifying key factors, banks can improve their sales pipeline and increase effciency by reducing time, resources, and costs when reaching out to prospects and clients, while maintaining a non-invasive relationship with all clients. 

## Data
The data obtained from the link, which is related to a direct marketing campaign by a Portuguese Financial Institution: http://archive.ics.uci.edu/ml/datasets

**Target Data**: 

Output variable (desired target):
  1.  has the client subscribed a term deposit? (binary: "yes","no")

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

As the core of this business problem is a classification problem, we will seek to utilize machine learning models including Logistic Regression, Random Forest, XG Boost, Gradient Boost, and Neural Networks to evaluate our model. 

Logistic Regression: <insert additional analysis>
  
Random Forest: <insert additional analysis>
  
XG Boost: <insert additional analysis>
  
Gradient Boost : <insert additional analysis>
  
Neural Network: <insert additional analysis>
  
  

## Analysis
  
insert analysis of best performing model as well as evaluation of said model
insert why this model performed the best
insert analysis of second best-performing model as well as evaluation of said model
insert why this model performed the second-best

## Results
  
interpret results of best model and secondary model and how it relates to business problem as well as how it can help banks improve

## Conclusions

draw conclusions from the project as well as steps for improvement
  
## Next Steps

highlight factors for model improvement, preprocessing and collection
highlight use cases of said project and business recommendation
  
## Repository Structure

```
├── data     <-- data files
│   ├──    <--- cleaned data file
│   ├──  <--- raw data file
│   └── 
├── images     <--- pictures from online/internally generated  
├── 0  <-- first notebook : cleans and explores the data
├── 0    <-- second notebook : models for the cleaned data
├── Presentation.pdf     <-- presentation slides
├── README.md
```
