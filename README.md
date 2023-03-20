# Text-Difficulty-Prediction-Clustering-TopicModel


DATASET: https://www.kaggle.com/competitions/umich-siads-696-f22-predicting-text-difficulty

The purpose of this project wasn't to achieve the highest accuracy from the beginning. It was more of an exploration on how to use different nlp methods 
for text analysis. Methods includes supervised learning, clustering and topic modeling. 

-------------------------------------------------------
### A. Supervised Learning Model for Predicting Text Difficulty

The purpose of this part is to build a supervised learning classification model where we will be able to predict whether each document(sentence) in the dataset extracted from Wikipedia needs to be simplified.In the end, we hope to find a "best" model for predicting the text difficulty. The two classes are defined as following:

Class 0: the sentence does NOT need to be simplified (Not Difficult).

Class 1: the sentence DOES need to be simplified (Difficult).

For supervised learning, we have explored four different types of algorithms. The feature representations are the same for the four models. It’s the feature representation extracted from Word2Vec using Bag of Words.

See SUP_MODEL_Final.ipynb for details and vis. 
https://github.com/YanyingJiangUmich/Text-Difficulty-TopicModel-Clustering/blob/main/SUP_MODEL_Final.ipynb



-------------------------------------------------------
### B. Unsupervised Learning - K-Means Clustering

Since we don’t have a target variable, the goal of our unsupervised learning approach is not to make predictions on the text difficulty. We will instead use unsupervised learning algorithms to discover the patterns in the dataset, for instance, how many clusters are there? What are the most popular topics? Then we will incorporate these findings as a way of feature representation and enhance our supervised learning models accordingly. The two models used in this section are K-Means and Topic Modeling, which will be illustrated in details below.

See UNSUP_MODEL_Final.ipynb for details and vis
https://github.com/YanyingJiangUmich/Text-Difficulty-TopicModel-Clustering/blob/main/UNSUP_MODEL_Final.ipynb



-------------------------------------------------------
### C. Topic Modeling 

Although we were able to identify some patterns of clusters from the K-Means clustering method, we were not able to tell what are the topics of each cluster. We believe that topic modeling can bring us more insights. One of the most common approaches for topic modeling is Latent Dirichlet Allocation (LDA), which assumes that each document is a mixture of topics, and each topic is a distribution over words.

In order to estimate the topic-word distributions, LDA requires a matrix of word frequencies for each document in the collection.Therefore we use a different feature representation directly extracted from the original dataset, leveraging TF-IDF. By weighting the word frequencies based on their importance in the collection, TF-IDF helps to filter out common and less meaningful words, and highlight the words that are most relevant to the topics. This can improve the accuracy and interpretability of the topic models, by reducing the influence of noise and irrelevant words. We firstly performed lowering, stopwords removal, punctuation removal and stemming on the original dataset, and then used the TF-IDF model provided in Gensim package.

See Topic_Modeling_Final.ipynb for details and vis
https://github.com/YanyingJiangUmich/Text-Difficulty-TopicModel-Clustering/blob/main/Topic_Modeling_Final.ipynb
