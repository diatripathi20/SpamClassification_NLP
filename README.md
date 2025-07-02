SMS Spam Classification using Machine Learning and NLP
======================================================

This project involves building a machine learning model to classify SMS messages as either spam or ham (not spam). Since SMS data is often informal and noisy, the goal was to improve classification accuracy by cleaning the data before training.

Objectives:

- Normalize noisy text messages by removing inconsistencies like abbreviations, phonetic spellings, and misspellings
- Engineer features to improve classification performance
- Train and compare multiple ML models
- Evaluate how much accuracy improves after cleaning the data

Dataset:

The primary dataset is the SMS Spam Collection available on Kaggle. Additional datasets were used:
- A clean text corpus for building a bigram language model
- A list of personal names to help distinguish names from malformed words

Approach:

1. Noise Cleaning Process
   - Generate possible corrections for out-of-vocabulary (OOV) words using edit distance, phonetics, and string similarity
   - Detect whether an OOV word is genuinely incorrect or just a personal name
   - Choose the most appropriate correction based on scoring and context

2. Preprocessing
   - Convert messages to lowercase
   - Remove special characters and digits
   - Tokenize and lemmatize text
   - Remove common stopwords

3. Feature Engineering
   - Word count
   - Presence of numbers
   - Presence of currency symbols
   - Oversampling was applied to address class imbalance (majority were ham)

4. Model Training
   - Models used: Naive Bayes, Decision Tree, Random Forest, and a Voting Classifier
   - Trained using scikit-learn
   - Evaluated using 10-fold cross-validation and F1-score

Results:

After applying noise cleaning, all models performed better. The Random Forest model gave the best performance with an F1-score of 0.992.

For example:
- "get credit score" → correctly classified as spam
- "get cradit score" → originally misclassified, but after noise correction, also identified as spam

Future Work:

- Improve ill-formed word detection with whitelists
- Use bootstrapping to improve training data quality
- Extend the approach to handle text in other languages

How to Use:

1. Clone the repository
2. Open the notebook in Jupyter or Google Colab
3. Run the code to preprocess the data and train the models

GitHub repo: https://github.com/diatripathi20/SpamClassification_NLP

Maintained by:
diatripathi20
