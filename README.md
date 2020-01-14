## Sentiment analysis of business articles using Machine Learning and Natural Language Processing

**The goal** of this project is making predictions on stock price movements based on business articles. The stress is here to use business articles which contain only considerable news about the company (i.e. introducing a new product) including its qauterly report articles. In this project I was trying to avoid using articles which make direct prediction/deduction of the recent stock prices.

The challenge: making prediction on a market which is considered to be effective. A **market is effective**, because the existing share prices always incorporate and reflect all relevant information.

Here is an example, where business information had an affect on stock prices:

![Tesla example](https://github.com/apy444/nlp_sentiment_business_articles/blob/master/img/Tesla_example.png)

### The findings:

With the Multinomial Naive Bayes model I was able to reach an **accuracy of 59%**. The model is more accurate in making prediction to a negative way (aka the stock price will drop) than to a positive way. The following image shows the model classification.

![Tesla example](https://github.com/apy444/nlp_sentiment_business_articles/blob/master/img/model_classification.png)

### The methodology:

**1. Collecting news articles and stock prices.**

For the modeling purpose I was collecting article headlines of ten major companies starting from January 1 2010.
See the webscraper code [here.](https://github.com/apy444/nlp_sentiment_business_articles/blob/master/data/Scraping_wsj_headlines.ipynb)
The scraped articles were collected into a Mongodb database.
The source of the stock prices was [finance.yahoo.com](finance.yahoo.com).

**2. Preprocessing of the articles**

This process included the removal of not relevant articles (i.e. blog, opinion, book), removal of articles which mention the stock price movements, or did not have considerable effect on stock prices. The impact on price is considerable if the stock price change compared to the S&P500 average is more than 1.5 percent point and the trading volume is above the 2 weeks average. This latter approach gives the label (positive-1, negative-0) of the articles.

The preprocessing also included the tokenization, stemming and removing of stopwords. See the code [here.](https://github.com/apy444/nlp_sentiment_business_articles/blob/master/data/Preprocessing%20final.ipynb)

The dataset was split randomly to train and test set.

**3. Model building**

For the model building the most essential part is the Tf-Idf vectorization. It stands for “Term Frequency – Inverse Document Frequency" which are the components of the resulting scores assigned to each word or ngrams. This vectorizer results in an inverse frequency. The most frequent words get the lowest score, "the most interesting" words get higher score. 

The following models were trained:

- Naive Bayes Model using NLTK library
- Logistic Regression
- K-Nearest Neighbors
- XG Boosting
- Support Vector Machine
- Multinomial Naive Bayes Model
- Bernoulli Naive Bayes Model
- Gaussian Naive Bayes Model

Generally saying, the above models all resulted in a substantial overfitting. To improve the model performance by reducing the overfitting we should involve more articles and focus on one specific industry. See the technical notebook [here.](https://github.com/apy444/nlp_sentiment_business_articles/blob/master/Technical%20notebook%20final.ipynb)

**4. The most driving positive and negative features:**

The WordCloud reflects the feature importance by the size of the words.

![Positive words](https://github.com/apy444/nlp_sentiment_business_articles/blob/master/img/pos_words.png)

![Negative words](https://github.com/apy444/nlp_sentiment_business_articles/blob/master/img/neg_words.png)

