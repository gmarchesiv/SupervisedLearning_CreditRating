# Supervised learning applied to transaction approval 

This notebook contains the analysis for a series of credit scoring models for a direct account payment gateway company.

A payment gateway is a merchant service provided by an e-commerce application company that authorizes credit card or direct payments processing for e-businesses, online retailers, bricks and clicks, or traditional brick and mortar. This particular gateway company authorizes direct payments to merchants from customers' bank accounts. The gateway has no online connection to banks, so it must rely on its own scoring models to determine which customers to approve. Bad transactions occur when customers do not have funds in their accounts at the time. Merchants get paid immediately, so default risk stays with the gateway company.

The company currently has access to scores from two credit rating providers, yet still uses a manual process to approve the transactions. Unless they get specific confirmation by phone from the customer's bank that the customer's account is empty, the transaction is approved. Hence, they are not leveraging the data from the providers. Bad (insolvent) transactions are frequent. The client wants to know how to use the data they have effectively to have a better risk model and be more profitable. The sector in which the company operates is risky. The commerces do not take credit cards, only direct payments. Commerces that use these methods generally attract riskier clients.

The analysis presents alternative credit socring models using supervised machine learning methods that combine these scores and other available data. The data is from a private direct payment processing company. Only features pertaining to the analysis are shown in the dataset. A logistic regression model and a KNN model will be compared to score 1 and score 2 by themselves as well as the interaction term of both. The hypothesis is that ML models can provide additional insight to the independent scores.   

The results are included in the notebook.

## Feature description
- `score_1`: client risk category depending on score from provider 1. Five possible categories: excellent, good, medium, bad  and no data (nd)
- `risk_score1`: binary variable according to risk profile from provider 1. Excellent and good are assigned a score of 0. The rest of the categories get a score of 1. 
- `score_2`:  client risk category depending on score from provider 2. Five possible categories: excellent, good, medium, bad  and no data (nd)
- `risk_score2`: binary variable according to risk profile from provider 2. Excellent and good are assigned a score of 0. The rest of the categories get a score of 1. 
- `interaction_1`: interaction term between score_1 and score_2. If both have a score of 1, the variable will be 1, i.e a risky client. In other cases, the variable will be 0.  
- `interaction_2`: its a more stringent definition of risk. Only the combinations of excellent, excellent and good,excellent in both permutations are considered 0. The rest are considered 1 (i.e risky). 
- `transaction`: es is the dollar amount of the transaction
- `bad_transaction`: binary variable where 1 corresponds to a bounced transaction (bad electronic check) and 0 is a succesful transaction (i.e the customer had the necessary funds). 
- `state`: two letters corresponding to the state in the United States
- `population`: binary variable where 1 is assigned to the most populous states: California, Texas, Florida, New York y Pennsylvania 
- `sc_control`: binary variable where 1 is assigned to the state of South Carolina. It has a disproportionate amount of transactions in the dataset for the size of its population. 
