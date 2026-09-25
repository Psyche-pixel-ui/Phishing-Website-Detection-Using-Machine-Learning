# Phishing Website Detection Using Machine Learning

## About the Project

This project uses **Machine Learning** to detect whether a website URL is likely to be a **phishing website** or a **not phishing website**.

The system analyzes different features of a URL, such as its length, number of dots, HTTPS usage, IP address, suspicious words, TLD, special characters, digits, and entropy. These features are used by a machine learning model to classify the URL.

## Machine Learning Problem

This project uses **binary classification**.

The system has two possible predictions:

* **Phishing Website**
* **Not Phishing Website**

The target variable is called `label`:

* `1` = Phishing Website
* `0` = Not Phishing Website

## Dataset

The project uses the **Phishing URLs Dataset with Extracted Features** from Kaggle.

The dataset contains **160,064 URL records** with extracted URL-based features.

### Main Features

* URL
* URL Length
* Number of Dots
* HTTPS
* IP Address
* Number of Subdirectories
* Number of Parameters
* Suspicious Words
* TLD (Top-Level Domain)
* Special Character Count
* Digits Count
* Entropy

The dataset contains phishing and benign URLs. It is highly imbalanced, so the project considers class balancing during model training and evaluation.

## Machine Learning Models

The following models are used or considered for comparison:

1. **Decision Tree**
2. **Random Forest**
3. **Logistic Regression**
4. **Naive Bayes**

Random Forest is used as the initial model because it can work with different URL features and is suitable for classification.

## Data Preparation

Before training the models, the dataset is checked and prepared.

The preparation includes:

* Checking missing or empty values
* Checking the number of rows and columns
* Checking data types
* Separating the target variable
* Preparing categorical features such as TLD
* Checking class imbalance
* Splitting the data into training and testing sets

The dataset is divided using an **80/20 train-test split** with stratification.

## Model Evaluation

The models are evaluated using several metrics:

* **Accuracy** – shows the overall number of correct predictions.
* **Precision** – shows how many URLs predicted as phishing are actually phishing.
* **Recall** – shows how many actual phishing URLs were detected.
* **F1-Score** – combines precision and recall.
* **Confusion Matrix** – shows correct and incorrect predictions for both classes.
* **False Positive Rate** – shows how many safe URLs were incorrectly classified as phishing.

Because the dataset is highly imbalanced, accuracy alone is not enough to evaluate the model.

The project also uses **stratified 5-fold cross-validation** on the training data.

## Expected Output

The system receives a URL and its extracted features and produces a prediction.

Example:

```text
Input:
URL and extracted URL features

Output:
Phishing Website
```

or

```text
Input:
URL and extracted URL features

Output:
Not Phishing Website
```

## Google Colab Notebook

You can open and run the project using Google Colab:

[Open Project in Google Colab]([https://colab.research.google.com/drive/17q2R9ARhG8pSAthujLrfRUu448U8zaoT?usp=sharing](https://colab.research.google.com/drive/17q2R9ARhG8pSAthujLrfRUu448U8zaoT?usp=sharing))

## Technologies Used

* Python
* Google Colab
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Machine Learning

## Project Goal

The goal of this project is to create a machine learning system that can identify suspicious URLs and help users recognize possible phishing websites before trusting them.

## Authors

**Zeth Gabriel Rodaje**
**Mary Ann Nicolas**

## References

Adi, V. (2025). *Phishing URLs dataset with extracted features* [Data set]. Kaggle.

Alkhalil, Z., Hewage, C., Nawaf, L., & Khan, I. (2021). Phishing attacks: A recent comprehensive study and a new anatomy. *Frontiers in Computer Science, 3*, 563060.

Sahingoz, O. K., Buber, E., Demir, O., & Diri, B. (2019). Machine learning based phishing detection from URLs. *Expert Systems with Applications, 117*, 345–357.
