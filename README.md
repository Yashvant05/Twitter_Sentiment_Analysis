# Twitter Sentiment Analysis using Machine Learning

This project is a Twitter Sentiment Analysis system built using Machine Learning and Natural Language Processing (NLP). The goal of the project is to classify tweets as either **Positive** or **Negative** based on the textual content of the tweet.

The model is trained on the popular **Sentiment140 dataset**, which contains 1.6 million tweets collected from Twitter. By learning patterns from a large amount of tweet data, the system can understand the sentiment and emotional tone behind user-generated text.

---

# Project Overview

Social media platforms generate a huge amount of textual data every day. Understanding user sentiment from this data is useful in many real-world applications such as:

- Product review analysis
- Brand monitoring
- Political opinion analysis
- Customer feedback systems
- Social media analytics

This project demonstrates how NLP and Machine Learning techniques can be used to build a sentiment classification system.

---

# Dataset

Dataset used: **Sentiment140 Dataset**

- Source: Kaggle
- Size: 1.6 Million Tweets
- File Size: ~238 MB

The original dataset contains the following columns:

- Target
- ID
- Date
- Flag
- User
- Text

For this project, only:
- `target`
- `text`

were used.

---

# Technologies Used

- Python
- Pandas
- NumPy
- NLTK
- Scikit-learn
- XGBoost
- Google Colab
- Matplotlib
- Seaborn

---

# Machine Learning Workflow

## 1. Data Collection

The dataset was directly downloaded from Kaggle into Google Colab using the Kaggle API.

---

## 2. Data Pre-processing

Since machine learning models cannot understand raw text directly, several NLP preprocessing techniques were applied.

### Text Cleaning
- Removed punctuation
- Removed numbers
- Removed special characters
- Converted all text to lowercase

### Stopword Removal
Common English words such as:
- I
- me
- myself
- the
- is

were removed because they do not contribute much to sentiment prediction.

### Stemming
The PorterStemmer algorithm was used to reduce words to their root form.

Examples:
- acting → act
- actor → act
- actress → act

This helps reduce dimensionality and improves learning efficiency.

---

# Feature Extraction

The cleaned tweets were converted into numerical vectors using:

## TF-IDF Vectorizer

TF-IDF (Term Frequency - Inverse Document Frequency) assigns importance scores to words based on how frequently they appear in the dataset.

This allows the model to identify words that strongly contribute to positive or negative sentiment.

---

# Train-Test Split

The dataset was divided into:

- 80% Training Data
- 20% Testing Data

The training set was used to train the model, while the testing set was used to evaluate model performance on unseen data.

---

# Models Used

The following machine learning models were trained and tested:

## 1. Logistic Regression
A strong baseline model for binary classification problems.

## 2. Linear Support Vector Classifier (LinearSVC)
A highly efficient model for large-scale text classification tasks using sparse TF-IDF features.

## 3. XGBoost Classifier
An advanced gradient boosting algorithm widely used in machine learning competitions and real-world applications.

---

# Model Accuracies

| Model | Accuracy |
|---|---|
| Logistic Regression | 77.66% |
| LinearSVC | 76.96% |
| XGBoost | 70.88% |

The ANN model achieved the highest accuracy among the tested models.

The close training and testing accuracies indicate that the models generalize reasonably well and are not heavily overfitting.

---

# Model Saving

The trained model and TF-IDF vectorizer were saved using the `pickle` library.

This allows predictions on new tweets without retraining the model.

Saved files:
- `sentiment_model.pkl`
- `tfidf_vectorizer.pkl`

---

# How to Run the Project

## Step 1: Open Google Colab

Upload the notebook file to Google Colab.

---

## Step 2: Setup Kaggle API

1. Create a Kaggle account
2. Verify your email/phone
3. Go to:
   - Kaggle Account Settings
4. Download:
   - `kaggle.json`

Upload the `kaggle.json` file into the Colab session.

---

## Step 3: Download Dataset

Use the Kaggle API command to download the Sentiment140 dataset directly into Colab.

---

## Step 4: Run the Notebook

Execute all cells sequentially:
- Import libraries
- Load dataset
- Preprocess text
- Apply TF-IDF
- Train models
- Evaluate models

---
