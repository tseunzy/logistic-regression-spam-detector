# SMS Spam Classifier (Logistic Regression)

This project builds an SMS spam detector using a manual implementation of **Logistic Regression** with **Gradient Descent** — without using scikit-learn models.

The goal is to understand how classification works internally by implementing the core math step by step.

---

## Project Overview

SMS spam detection is a binary classification problem:
    - **SPAM** → 1
    - **HAM** → 0

This project:

    - Cleans raw SMS text
    - Converts text into numeric features using Bag-of-Words
    - Trains Logistic Regression from scratch using gradient descent
    - Evaluates performance using accuracy and a manual confusion matrix
    - Includes a simple function to predict whether a new message is spam or ham

---

## Dataset

The dataset is loaded from `SMS6.csv`.

Important columns used:
    - Column **6** → Label (`HAM` or `SPAM`)
    - Column **7** → Message text

## Methods Used

### 1. Text Cleaning

    - Lowercasing
    - Removing digits
    - Removing punctuation
    - Removing extra whitespace

## 2. Feature Extraction (TF-IDF)
- Builds a vocabulary from all unique words (filtered by minimum frequency ≥ 2)
- Computes **Term Frequency** (word count / total words in message)
- Computes **Inverse Document Frequency** (penalizes common words, rewards rare ones)
- Produces a TF-IDF weighted feature matrix

# 3. Feature Scaling
- **Z-score normalization** (StandardScaler) applied to training set
- Test set scaled using training set mean and standard deviation (prevents data leakage)



## 4. Logistic Regression (From Scratch)

    Implemented manually:
    - Sigmoid function
    - Cost_function
    - Gradient_descent
    - Binary cross-entropy loss
    - L2 regularization (prevents overfitting)

## 5. Evaluation

- Accuracy, Precision, Recall, F1-score (all computed manually)
- Confusion matrix (manual)
- Train vs Test comparison (overfitting detection)


##  Results

| **Accuracy** | ~98%+ | ~97%+ |
| **Precision** | High | High — few false positives |
| **Recall** | High | High — catches most spam |
| **F1 Score** | High | Balanced performance |

- No significant overfitting (train-test accuracy gap < 2%)

##  Visualizations

- **Cost curve** — shows convergence over iterations
- **Training accuracy curve** — tracks learning progress
- **Confusion matrix heatmap** — shows TP, TN, FP, FN
- **Probability distribution** — shows model confidence for SPAM vs HAM
- **Top indicator words** — highest weighted words for SPAM and HAM

---

## How to Run

    1. Clone the repository
    2. Install dependencies
    3. Run the notebook or Python script

### Requirements
    - Python 3.x
    - numpy
    - pandas
    - matplotlib

---

## Example Usage

The project includes a `predict_spam(text)` function:

- predict_spam("Congratulations you won a free prize click now")
- predict_spam("Hey are we meeting for lunch today")

---
## WHat I improved 

1. **TF-IDF > Bag of Words** — weighting by word importance improves accuracy
2. **Stop words removal** — removes noise from common words
3. **L2 regularization** — prevents the model from overfitting to training data
4. **Z-score scaling** — ensures all features are on the same scale for gradient descent
5. **Everything from scratch** — no sklearn models used, only numpy


## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to open an issue or submit a pull request.