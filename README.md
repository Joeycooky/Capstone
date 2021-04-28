# DSI Capstone Project - Sentiment analysis and Topic modeling on airline tweets


## Problem Statement
An airline industry — one of the world most competitive market—have been exploring numerous attempt to improve customer satisfaction. Therefore, understanding customer needs via feedback analysis is essential. Although multiple feedback channels such as hotline, direct email, journey report have been employed, they are all arduous. Thus making a social media analysis a more compelling approach. **This project will focus on identifying negative sentiment tweets about the airline and categorize them into subcategories and direct them to related departments to solve problems and developing improvement strategies promptly.”**


**List of model used in the project:**
![Result](https://github.com/Joeycooky/DSI_CapstoneProject/blob/main/images/sentiment_classifier_result.png)

1. Metamodel : to handle metadata such as `tweet_created` (which was engineered into days_of_week and part_of_day), `char_length` and `word_length`
1. Textual model : to handle tweet messages in the columns `text`

Both model will be trained using `LogisticRegression` and `RandomForestClassifier`, finally, the accuracy model (tuned by GridSearchCV) will be selected as a candidate model.


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

![Overall](https://github.com/Joeycooky/DSI_CapstoneProject/blob/main/images/overall_performance.png)

- From the metadata including `days of week`, `parts of day`, `char_length`, `word_length` , the metamodel (LogisticRegression) can learned and achieved 72.1 % accuracy
- From the textual data, the texual model can achieved 83.4% accuracy
- The combined model (which take prediction of both metamodel and textual model as input achieved 84.2% accuracy, an only marginal improvement from the textual model
- The combined model have given weight of 0.05% to the metamodel and 99.95% to the texual model which mean that almost all knowledge and wisdom, the model has acquired from the data, came from the text not metadata.

![Keywords](https://github.com/Joeycooky/DSI_CapstoneProject/blob/main/images/top20_kw.png)

By looking at the log coefficient ...
- the top 20 keywords describing negative sentiment as plotted in red shaded bars
- the top 20 keywords indicating positive sentiment as plotted in blue shaded bars

We can see that tweets containing keywords such as `[hour, hr, delayed, delay, hold, cancelled] and/or [worst, fail, suck, rude, terrible, bad, disappointed]` will likely to be a negative sentiment tweet

![Topic](https://github.com/Joeycooky/DSI_CapstoneProject/blob/main/images/topic.png)

The negative sentiment can be grouped into 4 different topic where

1. Topic 1 : could be flight related problems since it contains keywords ['flight', 'delay']
1. Topic 2 : could be luggage related problem since it includes keywords ['luggage', 'agent']
1. Topic 3 : could be reservation / ticketing problems because it have related keywords such as ['reservation', 'phone', 'ticket']
1. Topic 4 : could be customer services problems since it contains ['call', 'service', 'customer', 'response']

## Future scope
![future_scope](https://github.com/Joeycooky/DSI_CapstoneProject/blob/main/images/future_scope.png)

- The future scope of this project will be including building a topic classifier to filter negative feedback into several topic then redirect them to different teams.
- In the future, if we got more data, it is possible that the suitable number of topic may change. At that time, we can recluster them and retrain the topic classifier.
