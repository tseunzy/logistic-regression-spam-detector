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

### 2. Feature Extraction (Bag-of-Words)

    - Builds a vocabulary from all unique words
    - Converts each message into a word-count vector
    - Normalizes counts into relative frequency 

### 3. Logistic Regression (From Scratch)

    Implemented manually:
    - Sigmoid function
    - Cost_function
    - Gradient_descent
    - Binary cross-entropy loss

### 4. Evaluation

    - Accuracy
    - Confusion matrix (manual)
    - Precision, Recall, F1-score (manual)

## 📊 Results

- **Accuracy**: ~97%+
- **Precision**: High — few false positives
- **Recall**: High — catches most spam
- **F1 Score**: Balanced performance

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

- `predict_spam("Congratulations you won a free prize click now")`
- `predict_spam("Hey are we meeting for lunch today")`

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to open an issue or submit a pull request.