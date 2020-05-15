#  Topic Modeling LDA Using Spark for Machine Learning 

## How to run the project

The project is done in jupyter notebooks after installing spark. To get the same results, one should run the notebooks in the same order given below:
* First one should run EDA file to get the schema, read the file count words, characters along with different graphical presentation
* Second Data Processing file to clean the data thoroughly, first removing punctations, lower casing words, lemmitization, stemming and removing all words less than 3.
* Third file one should run is Machine learning, we applied LDA model.
* Fourth one should be Validation.
* Last one is Testing file.
All results will be same.


## Introduction 

In this project, we are using spark to do machine learning. Our dataset is  `Amazon Product Review Dataset` and analyze reviews using natural language processing (NLP).Here we are using  algorithm "Topic Modeling " is a type of statistical modeling for discovering the abstract “topics” that occur in a collection of documents. Latent Dirichlet Allocation (LDA) is an example of topic model and is used to classify text in a document to a particular topic. It builds a topic per document model and words per topic model, modeled as Dirichlet distributions.


## About Data 

We used Amazon raw review dataset that was 34gb in zipped format and 120gb otherwise. We did EDA, DataProcessing along with Count vectorizer(files in Topic modeling folder) on that data but after that as data is too big and we were performing analysis on personal computer it stopped working when we tried to fit model. We thought to proceed with department's Datascience lab but we only have access on Tuesdays. Therefore we choose Amazon Magazine_Subscription data to proceed with.
`Amazon's Magazine Subscription dataset's online link is here http://deepyeti.ucsd.edu/jianmo/amazon/index.html.

## Topic Modeling:

For our project, we have to implement NLP on the dataset, in order to do that,we followed the following machine learning steps:

1. Exploratory Data Analysis (EDA)
2. Data Processing 
3. Machine Learning(Implementing Algorithms,Topic Modelling LDA)
4. Validation
5. Testing your Model

## 1. EDA 

In this part, We did the following steps:

1. Prepared graphical representation of `overall`
2. We found the most common words along with their frequency and graphical representation.
3. Got the count of all words in reviewText variable.
4. Counted the total number of characters in the whole dataset


## 2. Data Processing

Data Processing is the most important part of the project is to apply text processing to the dataset. 

For this purpose we performed following steps:

1. Removed punctations.
2. Lowercased words
3. Removed stopwords
4. Did Lemmatization
5. Stemming
6. Tokenization
7. Removed short words (len(word) > 3)

## 3. Machine Learning

For applying machine learning, as we have reviews in words, we have to vectorize the words to do analysis therefore we applied count vectorizer approach to vectorize the data. After that we remove null values from our data and splitted the dataset into two parts i.e., training and test datasets in 7:3 ratio. After that we applied Latent Dirichlet allocation (LDA) model in our dataset. In this process, we got top 20 Topics along with their weights. We plotted wordcloud on top 6 topics. After this we transformed the model and got topic distributions of topics. We also got topic matrix.

## 4. Validation

For validation of topic modeling best is to do coherence score as this measures score a single topic by measuring the degree of semantic similarity between high scoring words in the topic but Spark doesn't have any package for that therefore perplexity measure is used here for validation.

Perplexity is a statistical measure of how well a probability model predicts a sample.

## 5. Testing

For testing, we applied LDA model on two reviews that were neither from training nor from test. We took one online review some lipstick product and our data is of Magazine Subscription. This is five rating review. Other review is of dress and of one rating. We took the review in a dataframe then did the preprocessing to remove any biasedness and after countvectorizing, fitted the model. Model took term "wife" in fine rating and "worst" in one rating with very high topicDistribution. After this we also calculated the perplexity score.
