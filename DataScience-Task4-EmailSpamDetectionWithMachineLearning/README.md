# Email Spam Detection with Machine Learning

## Objective
This project builds a Natural Language Processing (NLP) binary classifier that 
distinguishes spam SMS messages from legitimate (ham) messages using TF-IDF 
feature extraction and supervised machine learning models.

This task was completed as part of the **Oasis Infobyte Summer Internship Program 
(SIP)** — Data Science Track, Task 4.

## Dataset
- **Source**: SMS Spam Collection Dataset (Kaggle / UCI Machine Learning Repository)
- **Size**: 5,572 messages (after removing duplicates: reduced accordingly)
- **Columns used**: 
  - `v1` — label (`ham` or `spam`)
  - `v2` — raw message text
- 3 additional unnamed columns in the raw CSV (mostly null, caused by stray commas 
  in a handful of messages) were dropped during preprocessing.

## Tech Stack
- Python 3
- pandas, numpy
- scikit-learn (TF-IDF Vectorizer, Multinomial Naive Bayes, Logistic Regression)
- NLTK (stopword removal)
- matplotlib, seaborn (visualisations)
- WordCloud (bonus visualisation)
- Jupyter Notebook / Google Colab

## Workflow

1. **Data Loading & Cleaning**
   - Loaded raw CSV, dropped unused/junk columns
   - Removed duplicate rows
   - Checked class distribution (spam vs ham)

2. **Text Preprocessing**
   - Lowercased all text
   - Removed punctuation and digits
   - Removed English stopwords using NLTK

3. **Feature Extraction**
   - Applied TF-IDF Vectorization (max 5,000 features) to convert cleaned text 
     into numeric feature vectors

4. **Model Training**
   - Split data into 80% train / 20% test (stratified to preserve class ratio)
   - Trained two classifiers:
     - Multinomial Naive Bayes
     - Logistic Regression

5. **Evaluation**
   - Assessed both models on Accuracy, Precision, Recall, F1-Score
   - Generated confusion matrices for each model

6. **Bonus Visualisation**
   - Generated WordClouds for spam vs ham messages to visually compare the most 
     frequent terms in each class

## Results

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---|---|---|---|
| Multinomial Naive Bayes | 0.9668 | 0.9912 | 0.7584 | 0.8593 |
| Logistic Regression | 0.9596 | 0.9906 | 0.7047 | 0.8235 |

**Best performing model: Multinomial Naive Bayes** — it achieved higher accuracy 
and a stronger F1-score than Logistic Regression. Both models showed very high 
precision (~99%), meaning false positives (legitimate messages flagged as spam) 
were rare. Recall was comparatively lower for both models, reflecting the dataset's 
class imbalance (~87% ham vs ~13% spam) and the models' conservative bias toward 
predicting "ham."

## Why Recall Matters for Spam Detection
Recall measures how many actual spam messages were correctly identified. In this 
task, both models missed a meaningful portion of spam (low recall relative to 
precision), which means some spam still reaches the user unfiltered. Depending on 
the deployment context, this trade-off between precision and recall may need to be 
tuned — for example, using class weighting or adjusting the decision threshold — 
based on whether the priority is catching more spam or minimizing false alarms on 
real messages.

## Repository Structure
## How to Run
1. Clone this repository
2. Ensure required libraries are installed:
3. Open `EmailSpamDetection.ipynb` in Jupyter Notebook or Google Colab
4. Run all cells sequentially (top to bottom)

