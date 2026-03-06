# spam_url_classification

This is a deep learning pipeline for malicious URL detection using TF-IDF feature extraction and a Pytorch deep neural netwoek classifier. The goal of this project is to build a machine learning model capable of classifying URLs based on textual patterns.

The model leverages n-gram features extracted from URLs and sends it into a neural network architecture to learn patterns and classify links that are malicious or not.

# Dataset

The train dataset contains URL strings and their associated labels(0 is benign, 1 is malicious)
The test dataset only contains URLs without labels for prediction.

# Feature Engineering 

The n-grams are created, then TFIDF vectorizer reads the URL text, generates n-gram tokens, computes TF-IDF numbers, then outputs a feature matrix of (number of URLs, number of features). 

# Model Architecture

These created n-dimension feature vector is sent to Deep URL classifier, a Deep Neural Network that calculates the probability of a URL's maliciousness

For the loss function, Binary Cross Entropy (BCELoss) loss was used.
Adam was used as the optimizer, with a learning rate of 0.001.
An Early Stopping mechanism was implemented to prevent overfitting. Training stops when validation loss stops improving for a defined number of epoches, saving the best model, and updating the least loss.

# Evaluation

The model is evaluated using AUC-ROC score (Area Under the Receiver Operating Characteristic Curve), which measures a binary classifier's performance by plotting the True Positive Rate against the False Positive Rate at various thresholds, resulting in a score between 0.0 and 1.0. 
