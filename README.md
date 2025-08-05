# URL Classification using Naive Bayes and SVM

This project is a machine learning classifier to detect and categorise URLs as malicious or benign using:
- Naive Bayes
- Support Vector Machine (SVM)

Dataset used:  
https://www.kaggle.com/datasets/sid321axn/malicious-urls-dataset

The dataset contains URLs labelled as:
- benign
- defacement
- malware
- phishing

---

## How it works

### 1. Install required packages
Make sure you install imbalanced-learn:

### 2. Load and preprocess data
- Load the CSV file using pandas
- Use a 10% random sample for faster training
- Extract the 'url' column as features (X)
- Extract the 'type' column as labels (y)
- Encode labels using LabelEncoder

### 3. Train-test split
- 80% training, 20% testing
- Stratified split to preserve label distribution

### 4. Build classifier pipelines
**Naive Bayes pipeline:**
- TfidfVectorizer
- SMOTE (for class balancing)
- MultinomialNB

**SVM pipeline:**
- TfidfVectorizer
- SMOTE
- SVC (RBF kernel)

### 5. Train the models
- Fit both pipelines on training data

### 6. Evaluate the models
- Generate predictions on test data
- Print classification report and confusion matrix

---

## Sample Output

**Naive Bayes Accuracy:** ~81%  
**SVM Accuracy:** ~93%

**Naive Bayes:**
- High precision for benign and defacement
- Lower performance on phishing URLs

**SVM:**
- Excellent performance across all categories
- Strong precision and recall for benign, defacement, and malware
- Slightly lower recall for phishing

---

## Conclusion

- Both classifiers performed well, but **SVM outperformed Naive Bayes** with higher accuracy and better balance across all URL types.
- SVM is better at handling complex decision boundaries in this multi-class problem.
- Naive Bayes is faster and simpler, but less accurate, especially for phishing detection.
- This project shows that basic ML models with proper preprocessing (like TF-IDF + SMOTE) can give solid results for text classification tasks like URL filtering.

---

## How to run (Google Colab)

1. Upload `malicious_phish.csv` to your Colab session
2. Copy the code into a notebook
3. Run all cells to train and evaluate both models

---

## Libraries used

- pandas
- numpy
- scikit-learn
- imbalanced-learn
