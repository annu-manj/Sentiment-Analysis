# Sentiment-Analysis  
The "Amazon Alexa Review - Sentiment Analysis" project is focused on analyzing customer reviews of Amazon Alexa products to predict whether the sentiment expressed in a given review is positive or negative. 

## 1. Dataset  
Amazon Alexa reviews dataset (amazon_alexa.tsv).

## 2. Exploratory Data Analysis (EDA)  
**Analyzing Rating Distribution:**  The distribution of ratings is visualized using bar plots, and the percentage distribution of each rating value is calculated. This helps in understanding how customers are rating the product.  
**Feedback Analysis:** The project examines the feedback column, which indicates whether the customer had a positive or negative experience. The distribution of feedback is analyzed, and specific reviews for positive and negative feedback are extracted for further inspection.  
**Variation Analysis:** The "variation" column, which could represent different product versions or models, is analyzed to see how ratings vary across these variations. The mean rating for each variation is calculated and visualized.  

## 3. Text Analysis and Visualization
Review Length Analysis: The length of reviews is analyzed based on whether the feedback is positive or negative. Histograms are used to visualize the distribution of review lengths for different feedback categories.
Word Cloud Generation: Word clouds are generated to visualize the most common words in positive and negative reviews. This provides insights into the language used by customers in different sentiment categories.  

## 4. Data Preprocessing
**Text Cleaning:** The reviews undergo preprocessing to prepare them for modeling. This involves:  
    1. Removing non-alphabetic characters.  
    2. Converting text to lowercase.  
    3. Splitting the text into words.  
    4. Removing stopwords (common words like "and," "the," etc., which do not contribute to sentiment).  
        Stemming words using the Porter Stemmer, which reduces words to their base form (e.g., "running"   becomes "run").  


## 5. Feature Extraction  
Bag of Words (BoW) Model: The CountVectorizer is used to convert the text data (corpus) into a matrix of token counts, also known as a Bag of Words. This matrix is used as the input (features) for the machine learning models. The vectorizer is limited to the 2,500 most frequent words to reduce dimensionality.  

The resulting feature matrix (X) and the target variable (y, representing feedback) are extracted. The CountVectorizer is saved using pickle for future use.

## 6. Data Splitting and Scaling   
**Train-Test Split:** The dataset is split into training and testing sets, with 70% of the data used for training and 30% for testing. This split ensures that the model's performance can be evaluated on unseen data.
Feature Scaling: The feature matrix is scaled using MinMaxScaler to ensure that all features are within the range [0, 1]. This is particularly important for algorithms like Random Forest that can be sensitive to feature scaling.
## 7. Modeling and Evaluation  
**Random Forest Classifier:** The project uses a Random Forest classifier, a robust ensemble learning method that builds multiple decision trees and combines their predictions. The model is trained on the scaled training data (X_train_scl and y_train).

**Model Accuracy:** The accuracy of the model is calculated on both the training and testing data to evaluate how well it generalizes to new data.  ##
**Confusion Matrix:** The predictions on the test set are compared to the true labels using a confusion matrix, which shows the counts of true positives, true negatives, false positives, and false negatives. This helps in understanding the types of errors the model is making.    
## 8. Model Saving
The trained Random Forest model and the scaler used for feature scaling are saved using pickle. This allows the model to be loaded and used for prediction on new data without retraining.
