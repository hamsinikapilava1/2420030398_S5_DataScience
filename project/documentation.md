1. Introduction

Social media generates huge volumes of text reflecting public opinion in real time. This 
project uses sentiment analysis to automatically determine whether a tweet expresses a 
positive, negative, or neutral sentiment, with applications in brand monitoring, customer 
service, and market research.

2. Problem Statement

Tweets are short, informal, and noisy — full of hashtags, mentions, slang, and links. The task 
is to build a system that cleans this text, converts it into a numerical form suitable for 
machine learning, and accurately predicts sentiment.

3. Objectives

- Explore a real-world tweet sentiment dataset.
- Perform EDA to understand class distribution and vocabulary patterns.
- Clean and preprocess tweet text.
- Extract features using TF-IDF vectorization.
- Train a Logistic Regression classifier.
- Evaluate the model with standard classification metrics.
- Build a reusable prediction function for new tweets.

4. Dataset

The Twitter US Airline Sentiment dataset, containing about 14,600 tweets aimed at major US 
airlines (American, Delta, Southwest, United, US Airways, Virgin America), collected in 
February 2015. Each tweet is labeled positive, negative, or neutral.

5. Methodology

The pipeline follows these stages: data acquisition, exploratory data analysis, text 
preprocessing, TF-IDF feature extraction, train/test split, model training, and evaluation.

5.1 Data Preprocessing
Tweet text is lowercased, and URLs, mentions, hashtag symbols, punctuation, and numbers are 
removed. Stopwords are filtered out, and Porter stemming is applied to reduce words to their 
root form.

5.2 Feature Extraction
Cleaned text is converted into TF-IDF vectors, which weigh words by their importance relative 
to the whole dataset.

5.3 Model Training
An 80/20 stratified train/test split is used. A Logistic Regression classifier is trained on 
the TF-IDF features to predict sentiment.

5.4 Evaluation
The model is evaluated on the test set using accuracy, precision, recall, F1-score, and a 
confusion matrix to understand where it performs well and where it confuses classes.

6. Results

The model reaches reasonable accuracy on the held-out test set. Negative tweets form the 
majority class, so precision and recall are typically stronger there than for positive and 
neutral tweets. Word clouds show negative tweets are dominated by complaint-related language, 
while positive tweets center on appreciation-related words.

7. Limitations

- Class imbalance biases predictions toward the negative class.
- TF-IDF doesn't capture word order or context, so sarcasm and negation are often missed.
- The model is trained on airline tweets and may not generalize well to other domains.
- Porter stemming occasionally distorts words.
- Slang or misspellings not seen during training are ignored.

8. Future Scope

Future improvements could include using word embeddings or transformer models (BERT, RoBERTa) 
for better context understanding, addressing class imbalance with techniques like SMOTE, testing 
other classifiers, tuning hyperparameters, supporting multilingual and emoji-aware text, 
deploying the model as a live API or web app, and adding aspect-based sentiment analysis to 
identify sentiment toward specific topics within a tweet.

9. Conclusion

This project demonstrates a complete, working pipeline for tweet sentiment analysis using 
classical NLP and machine learning. Combining text cleaning, TF-IDF, and Logistic Regression 
produces a model that classifies tweets with reasonable accuracy and gives interpretable 
insight into both the dataset and the model's behavior — a solid foundation for real-world 
sentiment monitoring applications.
