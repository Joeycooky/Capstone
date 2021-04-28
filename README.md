# DSI Capstone Project - Sentiment analysis and Topic modeling on airline tweets


## Problem Statement
An airline industry — one of the world most competitive market—have been exploring numerous attempt to improve customer satisfaction. Therefore, understanding customer needs via feedback analysis is essential. Although multiple feedback channels such as hotline, direct email, journey report have been employed, they are all arduous. Thus making a social media analysis a more compelling approach. **This project will focus on identifying negative sentiment tweets about the airline and categorize them into subcategories and direct them to related departments to solve problems and developing improvement strategies promptly.”**


**List of model used in the project:**
[Result]


**Evaluation metrics:**  
- **Accuracy** will be used as an evaluation metrics for sentiment classifier model.

- **Observation-based approaches** will be used to evaluate the topic modeling result.

**Baseline performance:**  
The performance of our sentiment classifier model will be compared against the ratio of the majority class (negative sentiment) at **62.7%**

## About the dataset
- The dataset was downloaded from [Kaggle : Twitter US Airline Sentiment](https://www.kaggle.com/crowdflower/twitter-airline-sentiment)
- It contains 14,640 rows and 15 columns, where only [`airline_sentiment`, `text`, `tweet_created`] will be used for sentiment classification.
- `negativereason` will be refurbishing as a ground truth for topic modeling and keyword in `text` will be using as a feature for topic modeling.

## Executive Summary

![Overall](https://github.com/Joeycooky/DSI_Project_2/blob/main/images/coef_overall.png)

Among all models in our study, an ElasticNet regressor with polynomial has the best predictive performance (evaluated by RMSE). However, considering interpretability, the simpler version without polynomial transformation is much easier to interpret and be understood by non-technical user.
Although numerous factors impacted the property value, some of the factors worth mentioning are ...
- Although price tend to increase with the total area of the house, living area is the most expensive part of it.
- From the perspective of property reseller, while overall quality directly means high resell price, we could consider buying an average quality house and focus on renovation to boost its price.
- With a limited budget, focus on kitchen renovation and refurbishing external appearance by repainting.
- If there is no garage, don't waste your time building one. It won't add much value to the house.

for detailed analysis please go to ...
1. <a href = https://github.com/Joeycooky/DSI_Project_2/blob/main/Code/EDA.ipynb > Exploratory Data Analysis </a>
1. <a href = https://github.com/Joeycooky/DSI_Project_2/blob/main/Code/model_polyorder2.ipynb > Model, Prediction and Conclusion </a>
