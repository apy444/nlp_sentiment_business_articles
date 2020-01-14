## Sentiment analysis of business articles using Machine Learning and Natural Language Processing

**The goal** of this project is making predictions on stock price movements based on business articles. The stress is here to use business articles which contain only considerable information about the company (i.e. introducing a new prodect) including its financial statetment and qauterly report articles. In this project I was trying to avoid using articles which make direct prediction/deduction of the recent stock prices.

The challenge: making prediction on a market which is considered to be effective. A **market is effective**, because the existing share prices always incorporate and reflect all relevant information.

Here is an example, where business information had an affect on stock prices:

![Tesla example](https://github.com/apy444/nlp_sentiment_business_articles/blob/master/img/Tesla_example.png)

### The findings:

With the Multinomial Naive Bayes model I was able to reach an accuary of 59%. The model is more accurate in making prediction to a negative way (aka the stock price will drop) than to a positive way. The following image shows the model classification.

![Tesla example](https://github.com/apy444/nlp_sentiment_business_articles/blob/master/img/model_classification.png)
