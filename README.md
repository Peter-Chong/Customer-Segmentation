# Customer Segmentation

<img src="https://github.com/Peter-Chong/Customer-Segmentation/blob/main/Images/RFM-model-segments-768x432.png" height="400"/>

## Problem Statement

Audible offered me a 3 months special offer before I click the unsubscribe button. I thought it was a great deal and continued to subscribe for another three months. That enticed me to think about whether the offer is provided to every churning customer? And if that is not the case, how does Audible knows who to give the offer to? Is there a way a company segment their customers and provide special offers to certain cluster since that cluster is more valuable to them? 

## Project Overview

* Performed exploratory data analysis and created plots for KPIs such as Growth Rate and Monthly Retention Rate  
* Measured Recency, Frequency and Monetary (RFM) on customer dataset
* Applied unsupervised K-Means Clustering to segment customers into 3 different groups  

## [Exploratory Data Analysis](https://nbviewer.jupyter.org/github/Peter-Chong/Customer-Segmentation/blob/main/Notebooks/Data%20Transformation%20%26%20EDA.ipynb)

It is important that we observe some of the important key performance indicators from the dataset and draw some insights.  
  
In the bar and line graph below, we notice that the revenue is cyclical. The company's revenue peaks at the end of both years. The reason for this phenomenon might due to 2 different reasons. Either the companies sell a lot of Christmas or new year related products, or the company holds clearance at the end of each year. More business contexts are required to understand this phenomenon.

<img src="https://github.com/Peter-Chong/Customer-Segmentation/blob/main/Images/Revenue_Plot.png" />

It is also important for us to compare the revenue earned from existing and new customers. The graph below shows that existing customers contribute to a larger part of the company's revenue throughout the period. We may conclude that the company is good at retaining its existing customer. However, the company should put more effort into luring new customers.  

<img src="https://github.com/Peter-Chong/Customer-Segmentation/blob/main/Images/New_vs_Old.png" />

## [Customer Segmentation with K-Means Clustering & RFM](https://nbviewer.jupyter.org/github/Peter-Chong/Customer-Segmentation/blob/main/Notebooks/Customer%20Segmentation%20with%20K-Means%20Clustering.ipynb) 

We will use the RFM model to segment the customers. After creating the respective indicators' column, we try to cluster them into k number of clusters. We will also use the elbow method to determine k values.  
  
RFM stands for Recency, Frequency and Monetary value. These metrics are important indicators of a customer's behavior.  
**Recency:** Number of days since the last purchase date  
**Frequency:** Total number of transactions made by a customer  
**Monetary:** Total value of transactions by each customer  
  
After obtaining 3 scores from the RFM model, we add them together and divide them into 3 groups.

<img src="https://github.com/Peter-Chong/Customer-Segmentation/blob/main/Images/Value_Group.png" />

<img src="https://github.com/Peter-Chong/Customer-Segmentation/blob/main/Images/Plot.png" />

**Customer behavior and potential targeting techniques for each loyalty level:**  
**High:** People in this group are more frequent buyers with average days since the last purchase is 31 days and the average number of times they have transacted in the platform is about 23 times. Also, their average sales value is 9,800 pounds. These are the most loyal customers, who not only bought the most recent and most often, but also heavy spenders. The company should reward these customers so they can help promote the brand.

**Medium:** People in this middle group on average have made a purchase 48 days ago. Their frequency and monetary values are 4 times and 1.2k pounds respectively.

**Low:** This is a dormant group with averaging 392 days since they last made a purchase. They have transacted around 2 times with an average sale of 650 pounds. These are customers who visited once and never came back. Surveys should be conducted to know what went wrong and avoid doing the same mistake to a new customer.

## Future Scope  

I would like to use probabilistic models such as Pareto-NBD, BG-NBD, MBG-NBD & Gamma-Gamma to predict future Customer Lifetime Value.

## Code and Resources:  
**Programming Language:** Python  
**Packages:**  Pandas, Plotly, Scikit-Learn
**Data Source:** https://archive.ics.uci.edu/ml/datasets/Online+Retail+II  
**Resources:**  
https://www.cloudkettle.com/blog/how-to-leverage-the-rfm-model-to-drive-customer-segmentation/  
https://medium.com/analytics-vidhya/marketing-analytics-rfm-modeling-855ebec18014  
