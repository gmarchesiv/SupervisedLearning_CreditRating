# Supervised learning applied to transaction approval 

This notebook contains the analysis for a series of credit scoring models for a direct account payment gateway company.

A payment gateway is a merchant service provided by an e-commerce application service provider that authorizes credit card or direct payments processing for e-businesses, online retailers, bricks and clicks, or traditional brick and mortar. This particular gateway company authorizes direct payments to merchants from customers bank accounts. The gateway has no online connection to banks, so it must rely on its own scoring models to determine which customers to approve. Bad transactions occur when customers do not have funds in their accounts at the time. Merchants get paid immediately, so default risk stays with the gateway company.

The company currently has scores from two credit rating providers, yet has a manual process to approve the transactions. Unless they get specific confirmation by phone from the customer's bank that the customer's account is empty, the transaction is approved. Hence, they are not leveraging the data from the providers. Hence, bad (insolvent) transactions are frequent. The client wants to know how to use the data they have effectively to have a better risk model and be profitable. The sector in which the company operates is risky. The commerces do not take credit cards, only direct payments. Commerces that use these methods are generally in riskier economic activities and therefore, attract riskier clients.

The analysis presents alternative credit socring models using supervised machine learning methods that combine these scores and other available data. The data is from a private direct payment processing company. Only features pertaining to the analysis are shown in the dataset. A logistic regression model and a KNN model will be compared to score 1 and score 2 by themselves as well as the interaction term of both. The hypothesis is that ML models can provide additional insight to the independent scores.   

The result of this analysis should advise the company on a model that will make their business more profitable.

