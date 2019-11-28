---
layout: post
title: Tweet Sentiment for Superhero Movies
description: Analyzing Tweets
img: /img/spider.jpg
---

<br>
#### Twitterverse Sentiment Analysis for Spiderman: Into The Spider-Verse(2018)  and Aquaman(2018) Movies
<br>
<img src="../spiderman_vs_aquaman_img/aqua_vs_spider.jpg">

Gathering 1600 tweets with the #Spiderman hashtag, and 1600 tweets using #Aquaman, the following graph was produced with the results from a trained Naive Bayes Classifier, a model that classified the sentiments of text as positive or negative. The analysis was done using Python's NLTK library, which includes a repository of 'Positive' and 'Negative' tweets, so every tweet had to fall in either one of the two categories. But what about if we want another category, like 'Neutral'? A second analysis was done using Pyhton's library TextBlob. This is an out-of-the-box sentiment analyzer which gave us a new 'Positive' and 'Negative' result, with an additional 'Neutral' sentiment result.

<br>
#### Analyzing using Naive Bayes Classifier and NLTK
<br>

<img src="../spiderman_vs_aquaman_img/output_4_0.png">

<br>
__Example of a tweet that was classified as Positive__: 'baby. baby boy🥰 #SpiderVerse'
<br>

<br>
__Example of a tweet that was classified as Negative__: 'So now ppl saying #AQUAMAN making a billion dollars is fixed?????'
<br>


<br>
#### Classifier Precision Stats
<br>

   positive precision: 0.993<br>
   positive recall: 0.991<br>
   positive F-measure: 0.992<br>
   negative precision: 0.991<br>
   negative recall: 0.993<br>
   negative F-measure: 0.992<br>

<br>
#### Classifier Acurracy on Labeling Sentiment
<br>

The following matrix shows that the classifier used in this case may have incorrectly labeled a percentage of tweets as negative/positive:

       |      n      p |
       |      e      o |
       |      g      s |
   ----+---------------+
   neg | <49.6%>  0.3% |
   pos |   0.5% <49.5%>|
    ----+---------------+
    

Now let's check the results when adding a 'Neutral' category into the mix, and using a different sentiment classifier, the TextBlob classifier:

<img src="../spiderman_vs_aquaman_img/output_14_0.png">

In both analysis, the movie 'Spiderman: Into the Spiderverse' showed more of a positive sentiment and less negative sentiment than 'Aquaman'. 

<br>
#### Box Office Results :
<br>

How popular are these movies in terms of ticket sales? The domestic box office sales for 7 weekends between December of 2018 and January of 2019 are shown below:

<img src="../spiderman_vs_aquaman_img/gross.png">

__The total worlwide box office grosses__<br>

__*<font color=#006994>Aquaman(2018) :  USD 1,148,161,807</font>*__

__*<font color=#B11313>Spiderman: Into The Spider-Verse(2018) :  USD 375,540,831</font>*__

Aquaman was clearly a winner in the box office by more than double. According to the tweeter sentiment, 'Spiderman: Into the Spider-Verse' should've done much better. 

    
*The tweets were saved in my [Kaggle](https://www.kaggle.com/marchman/spiderman-and-aquaman-tweets/data) profile and can be downloaded from there*

*Acknowledgements: Mukesh Chapagain in his blog found [here.](http://blog.chapagain.com.np/python-nltk-twitter-sentiment-analysis-natural-language-processing-nlp/)*

*Spiderman and Aquaman toy images courtesy of Adobe Stock Photos https://stock.adobe.com/co/*

{::options parse_block_html="true" /}

<details><summary markdown="span"><u>Click here to toggle hide\show code</u></summary>

```python
#Get the twitter_samples database with 5000 positive tweets and 5000 negative tweets
import nltk
nltk.download('twitter_samples')
import json
# nltk.download("twitter_samples")
from nltk.corpus import twitter_samples
print (twitter_samples.fileids())#Show that files loaded correctly. Should show three files.
    


# Create a dictionary to convert emoticons into words
def load_dict_smileys():
    
    return {
        ":‑)":"smiley",
        ":-]":"smiley",
        ":-3":"smiley",
        ":->":"smiley",
        "8-)":"smiley",
        ":-}":"smiley",
        ":)":"smiley",
        ":]":"smiley",
        ":3":"smiley",
        ":>":"smiley",
        "8)":"smiley",
        ":}":"smiley",
        ":o)":"smiley",
        ":c)":"smiley",
        ":^)":"smiley",
        "=]":"smiley",
        "=)":"smiley",
        ":-))":"smiley",
        ":‑D":"smiley",
        "8‑D":"smiley",
        "x‑D":"smiley",
        "X‑D":"smiley",
        ":D":"smiley",
        "8D":"smiley",
        "xD":"smiley",
        "XD":"smiley",
        ":‑(":"sad",
        ":‑c":"sad",
        ":‑<":"sad",
        ":‑[":"sad",
        ":(":"sad",
        ":c":"sad",
        ":<":"sad",
        ":[":"sad",
        ":-||":"sad",
        ">:[":"sad",
        ":{":"sad",
        ":@":"sad",
        ">:(":"sad",
        ":'‑(":"sad",
        ":'(":"sad",
        ":‑P":"playful",
        "X‑P":"playful",
        "x‑p":"playful",
        ":‑p":"playful",
        ":‑Þ":"playful",
        ":‑þ":"playful",
        ":‑b":"playful",
        ":P":"playful",
        "XP":"playful",
        "xp":"playful",
        ":p":"playful",
        ":Þ":"playful",
        ":þ":"playful",
        ":b":"playful",
        "<3":"love"
        }

#Clean and Tokenize tweets
import string
import re
import emoji
 
from nltk.corpus import stopwords 
stopwords_english = stopwords.words('english')
 
from nltk.stem import PorterStemmer
stemmer = PorterStemmer() #This is used to reduce the words to their stem word ('likely' becomes 'like').

from nltk.tokenize import TweetTokenizer

#Use a variable for the positive, negative and all tweets using their respective file name:
pos_tweets = twitter_samples.strings('positive_tweets.json')
neg_tweets = twitter_samples.strings('negative_tweets.json')
all_tweets = twitter_samples.strings('tweets.20150430-223406.json')

# Create a function that cleans and tokenizes tweets
def cleanAndTokenizeTweets(tweet):
    # remove stock market tickers like $GE
    tweet = re.sub(r'\$\w*', '', tweet)
 
    # remove old style retweet text "RT"
    tweet = re.sub(r'^RT[\s]+', '', tweet)
 
    # remove hyperlinks
    tweet = re.sub(r'https?:\/\/.*[\r\n]*', '', tweet)
    
    # remove hashtags
    # only removing the hash # sign from the word
    tweet = re.sub(r'#', '', tweet)
    
    # Convert emojis into words
    tweet = emoji.demojize(tweet)
    
    # Convert emoticons into words
    SMILEY = load_dict_smileys()  
    words = tweet.split()
    reformed = [SMILEY[word] if word in SMILEY else word for word in words]
    tweet = " ".join(reformed)
 
    # tokenize tweets
    tokenizer = TweetTokenizer(preserve_case=False, strip_handles=True, reduce_len=True)
    tweet_tokens = tokenizer.tokenize(tweet)
 
    tweets_clean = []    
    for word in tweet_tokens:
        if (word not in stopwords_english and # remove stopwords
                word not in string.punctuation): # remove punctuation
            #tweets_clean.append(word)
            stem_word = stemmer.stem(word) # stemming word
            tweets_clean.append(stem_word)
 
    return tweets_clean

#Create a bag of words function that uses the function cleanAndTokenizeTweets(), then returns the bag.
def bag_of_words(tweet):
    words = cleanAndTokenizeTweets(tweet)
    words_dictionary = dict([word, True] for word in words)    
    return words_dictionary

#Create a list of bags of words with all positive tweets
pos_tweets_set = []
for tweet in pos_tweets:
    pos_tweets_set.append((bag_of_words(tweet), 'pos')) 
    
#Create a list of bags of words with all negative tweets
neg_tweets_set = []
for tweet in neg_tweets:
    neg_tweets_set.append((bag_of_words(tweet), 'neg'))

# Radomize pos_reviews_set and neg_reviews_set
# doing so will output different accuracy result everytime we run the program
from random import shuffle 
shuffle(pos_tweets_set)
shuffle(neg_tweets_set)

#Train on 80% of tweets and test on 20% of tweets
train_set = pos_tweets_set[1000:] + neg_tweets_set[1000:]
test_set = pos_tweets_set[:1000] + neg_tweets_set[:1000]
 
print('Test tweets:',len(test_set),'Train tweets:',len(train_set)) # Check the number of tweets in test and train


#Training Classifier and Calculating Accuracy
from nltk import classify
from nltk import NaiveBayesClassifier
 
classifier = NaiveBayesClassifier.train(train_set)
 
accuracy = classify.accuracy(classifier, test_set)

from collections import defaultdict
from nltk.metrics import precision, recall, f_measure, ConfusionMatrix

actual_set = defaultdict(set)
predicted_set = defaultdict(set)
 
actual_set_cm = []
predicted_set_cm = []
 
for index, (feature, actual_label) in enumerate(test_set):
    actual_set[actual_label].add(index)
    actual_set_cm.append(actual_label)
 
    predicted_label = classifier.classify(feature)
 
    predicted_set[predicted_label].add(index)
    predicted_set_cm.append(predicted_label)


   

import pandas as pd
import matplotlib.pyplot as plt
plt.style.use('ggplot')

%matplotlib inline

SpidermanDF = pd.read_csv('Spiderman Tweets.csv')

#Create bag of words for each of the SpiderVerse tweets
Spider_text_set = []
for text in SpidermanDF['Text']:
    Spider_text_set.append(bag_of_words(text))

#Classify each bag of words
Spider_result = []
for bag in Spider_text_set:
    Spider_result.append(classifier.classify(bag))

SpidermanDF['Sentiment'] = Spider_result #Create a new column for the sentiment

plotSeries = SpidermanDF['Sentiment'].value_counts() #Get the number of negatives and positives

AquamanDF = pd.read_csv('Aquaman Tweets.csv')

Aquaman_text_set = []
for text in AquamanDF['Text']:
    Aquaman_text_set.append(bag_of_words(text))

#Classify each bag of words
Aquaman_result = []
for bag in Aquaman_text_set:
    Aquaman_result.append(classifier.classify(bag))

AquamanDF['Sentiment'] = Aquaman_result #Create a new column for the sentiment
plotSeries1 = AquamanDF['Sentiment'].value_counts()

# Plot

fig = plt.figure(facecolor="white",figsize=(10,8))
bar_width = 0.4
ax = fig.add_subplot(1, 1, 1)
r = [0,0.5] #Space between bars
tick_pos = [i + (bar_width/40) for i in r]

ax1 = ax.bar(r, plotSeries.values, width=bar_width, label='Spiderman', color='#B11313',edgecolor='white' )
ax2 = ax.bar(r, plotSeries1.values, bottom=plotSeries.values, width=bar_width, label='Aquaman', 
             color='#006994',edgecolor='white')
ax3 = ax.bar(r, plotSeries1.values, bottom=plotSeries.values, width=bar_width, color='#006994',edgecolor='white')
ax.set_ylabel("Count", fontsize=14, style='italic')
ax.set_xlabel("Sentiment", fontsize=14, style='italic')
ax.legend(loc='best')
plt.xticks(tick_pos, ["Positive", "Negative"], fontsize=14)
plt.yticks(fontsize=13)

for r1, r2 in zip(ax1, ax2): #Code to configure text inside each plot
    h1 = r1.get_height()
    h2 = r2.get_height()
    plt.text(r1.get_x() + r1.get_width() / 2., h1 / 2., "%d" % h1, ha="center", va="center", 
             color="white", fontsize=13, fontweight="bold")
    plt.text(r2.get_x() + r2.get_width() / 2., h1 + h2 / 2., "%d" % h2, ha="center", va="center", 
             color="white", fontsize=13, fontweight="bold")
plt.legend(prop={'size': 13})
plt.title('Sentiment Analysis on Tweets about\n Spiderman and Aquaman Movies')
plt.show()


print('pos precision:', precision(actual_set['pos'], predicted_set['pos']))
print('pos recall:', recall(actual_set['pos'], predicted_set['pos'])) 
print('pos F-measure:', f_measure(actual_set['pos'], predicted_set['pos']))
print('neg precision:', precision(actual_set['neg'], predicted_set['neg']))
print('neg recall:', recall(actual_set['neg'], predicted_set['neg'])) 
print('neg F-measure:', f_measure(actual_set['neg'], predicted_set['neg'])) 

cm = ConfusionMatrix(actual_set_cm, predicted_set_cm)
print (cm.pretty_format(sort_by_count=True, show_percents=True, truncate=9))

# Now use the TextBlob classifier to do a new analysis which includes a neutral category for sentiment

```python
import pandas as pd
from textblob import TextBlob
import re
import emoji #Import emoji library to turn emojis into words that express sentiment

spider = pd.read_csv("Spiderman Tweets.csv")
aqua = pd.read_csv("Aquaman Tweets.csv")

spider.head()



def clean_tweet(tweet): 
    ''' 
    Utility function to clean tweet text by removing links, special characters 
    using simple regex statements. 
    '''
    # remove stock market tickers like $GE
    tweet = re.sub(r'\$\w*', '', tweet)
 
    # remove old style retweet text "RT"
    tweet = re.sub(r'^RT[\s]+', '', tweet)
 
    # remove hyperlinks
    tweet = re.sub(r'https?:\/\/.*[\r\n]*', '', tweet)
    
    # remove hashtags # only removing the hash # sign from the word
    tweet = re.sub(r'#', '', tweet)
    #Convert emoji into word
    tweet = emoji.demojize(tweet)
    
    # Convert Smileys into words
    SMILEY = load_dict_smileys()  #Use the function created for the first analysis
    words = tweet.split()
    reformed = [SMILEY[word] if word in SMILEY else word for word in words]
    tweet = " ".join(reformed)
    
    return ' '.join(re.sub("(@[A-Za-z0-9]+)|([^0-9A-Za-z \t])|(\w+:\/\/\S+)", " ", tweet).split()) 


def get_tweet_sentiment(tweet): 
    ''' 
    Utility function to classify sentiment of passed tweet 
    using textblob's sentiment method 
    '''
    # create TextBlob object of passed tweet text 
    analysis = TextBlob(tweet) 
    # set sentiment 
    if analysis.sentiment.polarity > 0: 
        return 'positive'
    elif analysis.sentiment.polarity == 0: 
        return 'neutral'
    else: 
        return 'negative'

# Apply functions to spiderman series and create Sentiment column
spider["Text"] = spider["Text"].apply(clean_tweet)
spider["Sentiment"] = spider["Text"].apply(get_tweet_sentiment)

# Apply functions to aquaman series and create Sentiment column
aqua["Text"] = aqua["Text"].apply(clean_tweet)
aqua["Sentiment"] = aqua["Text"].apply(get_tweet_sentiment)

%matplotlib inline

plot_spider = spider["Sentiment"].value_counts()
plot_aqua = aqua['Sentiment'].value_counts()

# Plot

fig = plt.figure(facecolor="white",figsize=(10,8))
bar_width = 0.4
ax = fig.add_subplot(1, 1, 1)
r = [0,0.5,1] #Space between bars
tick_pos = [i + (bar_width/40) for i in r]

ax1 = ax.bar(r, plot_spider.values, width=bar_width, label='Spiderman', color='#B11313',edgecolor='white' )
ax2 = ax.bar(r, plot_aqua.values, bottom=plot_spider.values, width=bar_width, label='Aquaman', 
             color='#006994',edgecolor='white')
ax3 = ax.bar(r, plot_aqua.values, bottom=plot_spider.values, width=bar_width, color='#006994',edgecolor='white')
ax.set_ylabel("Count", fontsize=14, style='italic')
ax.set_xlabel("Sentiment", fontsize=14, style='italic')
ax.legend(loc='best')
plt.xticks(tick_pos, ["Positive", "Negative","Neutral"], fontsize=14)
plt.yticks(fontsize=13)

for r1, r2 in zip(ax1, ax2): #Code to configure text inside each plot
    h1 = r1.get_height()
    h2 = r2.get_height()
    plt.text(r1.get_x() + r1.get_width() / 2., h1 / 2., "%d" % h1, ha="center", va="center", 
             color="white", fontsize=13, fontweight="bold")
    plt.text(r2.get_x() + r2.get_width() / 2., h1 + h2 / 2., "%d" % h2, ha="center", va="center", 
             color="white", fontsize=13, fontweight="bold")
plt.legend(prop={'size': 13})
plt.title('Sentiment Analysis on Tweets about\n Spiderman and Aquaman Movies')
plt.show()
```