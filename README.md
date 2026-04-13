# Assignment-39
# Aspect-Based Sentiment Analysis for E-commerce Reviews

Github link : https://github.com/omshinde-alt07/Assignment-39

## Overview

This project focuses on sentiment analysis for e-commerce reviews at two levels:

* **Review-Level Classification**: Predicts one overall sentiment for the complete review.
* **Aspect-Level Classification**: Detects sentiment for specific product aspects such as camera, battery, delivery, and customer support.

The goal is to build a smarter NLP system that captures mixed opinions inside a single review.

---

## Problem Statement

A review may contain both positive and negative feedback at the same time.

Example:

> Amazing camera quality but the battery is atrocious and customer support was unhelpful.

Traditional review-level models return one label only, while aspect-level models identify:

* Camera Quality -> Positive
* Battery -> Negative
* Customer Support -> Negative

---

## Why Aspect-Level is Harder

Aspect-level sentiment is more challenging because the model must:

1. Detect multiple aspects in one sentence.
2. Link each sentiment phrase to the correct aspect.
3. Handle contrast words like **but**, **however**, **although**.
4. Understand negation and sarcasm.
5. Process mixed sentiment in the same review.

This is why review-level F1 can be higher than aspect-level F1.

---

## Approach

The pipeline includes:

1. Text preprocessing

   * Lowercasing
   * Cleaning text
   * Tokenization
   * Stopword handling

2. Feature Engineering

   * TF-IDF features
   * N-grams
   * Aspect keywords
   * Negation handling
   * Contrast detection

3. Modeling

   * Logistic Regression baseline
   * Transformer upgrade (BERT / RoBERTa / XLM-R)

4. Evaluation

   * Precision
   * Recall
   * F1 Score

---

## Results

* **Review-Level Classifier:** 88% F1
* **Aspect-Level Classifier:** 71% F1
* **Target Improvement:** 80%+ F1 using transformer-based ABSA models

---

## Example Output

Input Review:

```text
Amazing camera quality but the battery is atrocious and customer support was unhelpful.
```

Predicted Aspect Sentiments:

```text
Camera Quality      -> Positive
Battery             -> Negative
Customer Support    -> Negative
```

---

## Tech Stack

* Python
* Pandas
* Scikit-learn
* NLP preprocessing
* Transformers (optional)

---

## How to Run

```bash
pip install pandas scikit-learn
python main.py
```

---

## Future Improvements

* Fine-tune BERT for ABSA
* Add Hinglish / code-mixed reviews
* Handle sarcasm better
* Real-time dashboard for product teams
* Aspect trend analytics by product category

---

## Business Value

Aspect-level sentiment helps product teams understand exactly what users like or dislike. Instead of knowing a review is negative, teams learn whether the issue is battery, delivery, support, or quality.

---

## Author

Om Shinde
