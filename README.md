
# Sentiment  Analysis  of  Twitter  Data  using  different  Machine  Learning Techniques

Sentiment Analysis examines and processes the emotions expressed  in  textual  data.  In  other  words,  the  Sentiment Analysis determines whether the given information is positive, negative,  or  neutral  when  it  comes  to  a  particular  topic  or product.
This project will take input from user and will fetch latest tweets based on the keyword and will tell the polarity of the tweets by using different Machine Learning Algorithms.


## Badges



![PyPI - Python Version](https://img.shields.io/pypi/pyversions/3)
## Installation

Basic programming knowledge of Python is required.

Python must be installed on the machine in order to run this code. The libraries twitter, nltk, re, csv, time, and json will be used. The first two libraries will almost certainly need to be installed. The Python interpreter is already included with the rest. It's still a good idea to double-check if they're current.

**NLTK:**

The Natural Language Toolkit (NLTK) is a Python framework that serves as the foundation for text processing and classification. NLTK can be used to do tasks such as tokenization, tagging, filtering, and text manipulation.
Various trainable classifiers (for example, the Nave Bayes Classifier) are also included in the NLTK library.
A bag-of-words model, which is a form of unigram model for text, is created using the NLTK package. The number of times each word appears in this model is counted. The collected data can be utilised to train classifier models. The sentiment of the full tweets is calculated by utilising a sentiment lexicon to assign a subjective score to each word.


Tweepy: tweepy is the official Twitter API's python client.
Use the pip command to install it:

```bash
  pip install tweepy
```
TextBlob is a Python library for manipulating textual data.
Use the pip command to install it:
```bash
  pip install textblob
```

We'll also need to run the following script to install certain NLTK corpora:
```bash
  python -m textblob.download_corpora
```
(Corpora is nothing more than a big and well-organized collection of texts.)
    
 **Authentication:**
 To use the Twitter API to retrieve tweets, users must first create an App using their Twitter account. To do so, follow these steps:

* Open this [link](https://developer.twitter.com/en/portal/projects-and-apps) and click the ‘Create New App' button.
* Complete the application form. The callback url field can be left blank.
* You will be routed to the app page after the app has been created.
* Open the tab labelled "Keys and Access Tokens."
* Take notes on the terms "Consumer Key," "Consumer Secret," "Access Token," and "Access Token Secret."

We follow these 3 major steps in our program:

* Authorize twitter API client.
* Make a GET request to Twitter API to fetch tweets for a particular query.
* Parse the tweets. Classify each tweet as positive, negative or neutral.

First of all, we create a TwitterClient class. This class contains all the methods to interact with Twitter API and parsing tweets. We use __init__ function to handle the authentication of API client and to call the Twitter API to fetch tweets.

TextBlob is a high-level library that is built on top of the NLTK library. Using some simple regex, we first call the clean tweet method to remove links, special characters, and other elements from the tweet.
The following processing is done over text by the textblob library when we pass tweet to generate a TextBlob object:

* Tokenize the tweet, which means separating words from the rest of the text.
* Stopwords should be removed from the tokens.
* (Stopwords are commonly used words that have no bearing on text analysis, such as I, am, you, are, and so on.)
* Tag the tokens with POS (part of speech) tags and only use significant features/tokens like adjectives, adverbs, and so on.
* Pass the tokens to a sentiment classifier, which assigns a polarity between -1.0 and 1.0 to the tweet sentiment and classifies it as positive, negative, or neutral.

Here's how you make a sentiment classifier:

* TextBlob makes use of a collection of movie reviews that has previously been categorised as favourable or negative.
* Each favourable and negative review is analysed for positive and negative characteristics.
* Positive and negative characteristics are now labelled in the training data. A Naive Bayes Classifier is used to train this data.

Steps in Naive Bayes Classifier:

1- Build a vocabulary (list of words) of all the words resident in our training data set.

2- Match tweet content against our vocabulary — word-by-word.

3- Build our word feature vector.

4- Plug our feature vector into the Naive Bayes Classifier.

Maximum Entropy Classifier:

The input to an instance of the Maximum Entropy Evaluator is made up of four parameters:

1- Number of tweets to train on (filesubset)

2- Minimum number of occurences a feature must have appeared to be included as a feature (min_occurences)

3- The number of iterations to run GIS (max_iter)

4- What n-grams to use (grams, a list)


Then we utilise the TextBlob class's sentiment.polarity function to get the polarity of a tweet ranging from -1 to 1.



Then, we classify polarity as:
```bash
  if analysis.sentiment.polarity > 0:
       return 'positive'
  elif analysis.sentiment.polarity == 0:
       return 'neutral'
  else:
       return 'negative'
```
Finally, the parsed tweets are returned to the user. The tweets can then be subjected to various types of statistical analysis. For example, we tried to find the percentage of favourable, negative, and neutral tweets regarding a query in the above application.


### USAGE:

After installation, just run the main.py file and enter the keyword. After the code finishes the compilation it will return the percentage of positive, negative and neutral tweets. 


### Screenshots

![ScreenShot](https://raw.github.com/harshil-lu/Sentiment_Analysis_using_ML/main/img/screenshot_1.png)

![ScreenShot](https://raw.github.com/harshil-lu/Sentiment_Analysis_using_ML/main/img/screenshot_2.png)



### Contact:

For any queries mail me at hprajap3@lakeheadu.ca



### Roadmap

- Need further work to improve the accuracy.

- Can use more datasets.

- Can add frontend part for clear understanding.

  
### Contributing

Contributions are always welcome!


Please adhere to this project's `code of conduct`.

  
### Acknowledgements

https://textblob.readthedocs.io/en/dev/quickstart.html#sentiment-analysis

https://textblob.readthedocs.io/en/dev/_modules/textblob/en/sentiments.html

https://www.ijcaonline.org/research/volume125/number3/dandrea-2015-ijca-905866.pdf
### License

No License required. Everything is open source.


### Project Status

Sentiment Analysis is a fun approach to think about how Natural Language Processing can be used to make automated decisions about text. It's used to analyse social media trends and, on occasion, for marketing objectives. Thanks to current, ready-to-use modules, creating a Sentiment Analysis programme in Python is not difficult. This code is a simple demonstration of how to use this type of application. This is only for educational reasons, as the code described here is far from being ready for production.
Further research can be done in this domain but right now I am completing my part here.

THANK YOU.

  
