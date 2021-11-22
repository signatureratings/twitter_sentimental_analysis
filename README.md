## Abstract

We introduce a novel approach for automatically classifying the sentiment of Twitter messages. These messages are
classified as either positive or negative with respect to a
query term. This is useful for consumers who want to research the sentiment of products before purchase, or companies that want to monitor the public sentiment of their
brands. There is no previous research on classifying sentiment of messages on microblogging services like Twitter.
We present the results of machine learning algorithms for
classifying the sentiment of Twitter messages using distant
supervision. Our training data consists of Twitter messages
with emoticons, which are used as noisy labels. This type of
training data is abundantly available and can be obtained
through automated means. We show that machine learning algorithms (Naive Bayes, Maximum Entropy, and SVM)
have accuracy above 80% when trained with emoticon data.
This paper also describes the preprocessing steps needed in
order to achieve high accuracy. The main contribution of
this paper is the idea of using tweets with emoticons for
distant supervised learning.

## Introduction

Consumers can use sentiment analysis to research products
or services before making a purchase. Marketers can use this
to research public opinion of their company and products,
or to analyze customer satisfaction. Organizations can also
use this to gather critical feedback about problems in newly
released products.
There has been a large amount of research in the area of sentiment classification. Traditionally most of it has focused on
classifying larger pieces of text, like reviews [9]. Tweets (and
microblogs in general) are different from reviews primarily
because of their purpose: while reviews represent summarized thoughts of authors, tweets are more casual and limited to 140 characters of text. Generally, tweets are not as
thoughtfully composed as reviews. Yet, they still offer companies an additional avenue to gather feedback. There has
been some work by researchers in the area of phrase level and
sentence level sentiment classification recently [11]. Previous
research on analyzing blog posts includes [6].
Previous research in sentiment analysis like Pang et al. [9]
have analyzed the performance of different classifiers on movie
reviews. The work of Pang et al. has served as a baseline
and many authors have used the techniques provided in their
paper across different domains. Pang et al. also make use
of a similar idea as ours, using star ratings as polarity signals in their training data. We show that we can produce
comparable results on tweets with distant supervision.
In order to train a classifier, supervised learning usually requires hand-labeled training data. With the large range of
topics discussed on Twitter, it would be very difficult to
manually collect enough data to train a sentiment classifier
for tweets. Our solution is to use distant supervision, in
which our training data consists of tweets with emoticons.
This approach was introduced by Read [10]. The emoticons
serve as noisy labels. For example, :) in a tweet indicates
that the tweet contains positive sentiment and :( indicates
that the tweet contains negative sentiment. With the help of
the Twitter API, it is easy to extract large amounts of tweets
with emoticons in them. This is a significant improvement
over the many hours it may otherwise take to hand-label
training data. We run classifiers trained on emoticon data
against a test set of tweets (which may or may not have
emoticons in them).
We present the results of our experiments and our thoughts
on how to further improve results. To help visualize the util-
ity of a Twitter-based sentiment analysis tool, we also have
a web application with our classifiers1
. This can be used by
individuals and companies that may want to research sentiment on any topic.

## Aproach  
Our approach is to use different machine learning classifiers
and feature extractors. The machine learning classifiers are
Naive Bayes, Maximum Entropy (MaxEnt), and Support
Vector Machines (SVM). The feature extractors are unigrams, bigrams, unigrams and bigrams, and unigrams with
part of speech tags. We build a framework that treats classifiers and feature extractors as two distinct components.



## ML methods

Naive Bayes
Maximum Entropy
Support Vector Machines