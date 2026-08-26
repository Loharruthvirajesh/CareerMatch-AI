# CareerMatch AI — Resume Classification & Job Matching System

## 📌 Project Overview

**CareerMatch AI** is an NLP and Machine Learning project designed to automate the initial classification of resumes into relevant career categories.

The project addresses a common recruitment challenge: **manually reviewing large numbers of resumes is time-consuming, subjective, and difficult to scale.** The goal was to build an intelligent system that can process resume text, identify meaningful information from candidate profiles, and classify resumes into suitable job-role categories.

The project demonstrates an end-to-end machine learning workflow, from **data cleaning and exploratory analysis to NLP preprocessing, feature engineering, model training, evaluation, and model selection.**

---

## 🎯 Problem Statement

Recruiters may receive hundreds or thousands of resumes for different job roles. Manually screening each resume can:

* Consume significant time and resources
* Introduce subjective decision-making
* Make large-scale resume screening difficult
* Make it challenging to consistently identify the most relevant career category

### Objective

Build a machine learning system that can:

1. Process raw resume text
2. Clean and normalize unstructured resume data
3. Extract meaningful textual features
4. Represent resumes numerically using NLP techniques
5. Classify resumes into relevant career categories
6. Compare multiple machine learning algorithms
7. Select the best-performing model based on evaluation metrics

---

## 📊 Dataset

The project uses a resume dataset containing **962 records** with two primary fields:

* `Category` — target career/job category
* `Resume` — raw resume text

The dataset contains **25 career categories**, including:

* Data Science
* Python Developer
* Java Developer
* Business Analyst
* DevOps Engineer
* Database
* HR
* Testing
* Automation Testing
* Blockchain
* Hadoop
* SAP Developer
* ETL Developer
* Network Security Engineer
* Mechanical Engineer
* Civil Engineer
* Electrical Engineering
* And other career categories.

---

## 🔍 Data Quality & Exploration

The initial dataset contained **962 records** and no missing values. However, the analysis identified **795 duplicate records**.
Instead of blindly training a model on duplicated data, the project investigated duplicate resumes and verified that there were no resumes appearing under multiple career categories.

After duplicate removal:

* Original records: **962**
* Duplicate records removed: **795**
* Clean records: **167**
* Remaining duplicate records: **0**
* Remaining duplicate resumes: **0**

This data-quality step was important to reduce the risk of the model learning from repeated examples.

---

## 🧹 NLP & Text Preprocessing

Because resumes are unstructured text, NLP preprocessing was performed before machine learning.

The preprocessing pipeline included:

* Text cleaning
* Normalization
* Removal of unnecessary characters and formatting
* Stop-word removal
* Tokenization
* Token-count analysis

The cleaned resume text was stored as `clean_resume`, and the text was subsequently tokenized using NLTK.

This transformed noisy resume content into a more consistent representation suitable for machine learning.

---

## 🧠 Feature Engineering — TF-IDF

To convert resume text into numerical features, the project used **TF-IDF (Term Frequency–Inverse Document Frequency)**.

The vectorizer was configured with:

* Maximum features: **5,000**
* N-gram range: **1–2**
* Sublinear TF enabled

The model was fitted **only on the training data** and then used to transform the test data, preventing information leakage from the test set.

The resulting feature matrices contained:

* Training data: **132 × 5,000**
* Testing data: **34 × 5,000**

## The final classification problem contained **25 career categories**.

## 🤖 Machine Learning Models

Three classification algorithms were trained and compared:

1. **Logistic Regression**
2. **Linear Support Vector Machine (SVM)**
3. **Multinomial Naive Bayes**

The dataset was divided using an **80/20 stratified train-test split**:

* Training samples: **132**
* Testing samples: **34**

Stratification was used to maintain representation of the career categories across training and testing datasets.

---

## 📈 Model Performance

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score

| Model                   |   Accuracy |  Precision |     Recall |   F1 Score |
| ----------------------- | ---------: | ---------: | ---------: | ---------: |
| **Logistic Regression** | **91.18%** | **87.00%** | **90.00%** | **87.43%** |
| Linear SVM              |     88.24% |     81.00% |     86.00% |     82.10% |
| Naive Bayes             |     32.35% |     12.30% |     20.00% |     13.89% |

## The results show that **Logistic Regression performed best** among the evaluated models, achieving **91.18% test accuracy** and the highest F1 score.

## 🏆 Final Model

Based on the evaluation results, **Logistic Regression** was selected as the best-performing classifier.

The model achieved:

**91.18% Accuracy**

**87.43% Macro F1 Score**

The project therefore demonstrates that traditional machine learning combined with TF-IDF can effectively classify resume text across multiple career categories.

---

## 💾 Model Artifacts

The project also creates reusable preprocessing artifacts for future inference:

* `tfidf_vectorizer.pkl`
* `label_encoder.pkl`

These artifacts allow the trained text representation and category encoding to be reused when processing new resume data.

---

## 🛠️ Technology Stack

**Programming Language**

* Python

**Data Analysis**

* Pandas
* NumPy

**Data Visualization**

* Matplotlib
* Seaborn

**Natural Language Processing**

* NLTK
* TF-IDF

**Machine Learning**

* Scikit-learn
* Logistic Regression
* Linear SVM
* Multinomial Naive Bayes

**Development Environment**

* Jupyter Notebook

---

## 🔄 Project Workflow

```text
Raw Resume Dataset
        ↓
Data Understanding & EDA
        ↓
Duplicate Detection & Removal
        ↓
Text Cleaning
        ↓
Stop-word Removal
        ↓
Tokenization
        ↓
Train/Test Split
        ↓
TF-IDF Feature Engineering
        ↓
Label Encoding
        ↓
Model Training
        ↓
Model Evaluation
        ↓
Model Comparison
        ↓
Best Model Selection
        ↓
Reusable Model Artifacts
```

---

## 💡 Key Takeaways

This project demonstrates practical experience with:

* Working with **unstructured text data**
* Identifying and resolving **data-quality issues**
* Applying **NLP preprocessing techniques**
* Performing **feature engineering using TF-IDF**
* Preventing **data leakage during feature extraction**
* Handling **multi-class classification**
* Comparing multiple machine learning algorithms
* Evaluating models using multiple performance metrics
* Saving reusable ML preprocessing artifacts
* Translating a real-world recruitment problem into a machine learning solution

---

## 🚀 Future Improvements

The current project focuses on resume classification. The system could be extended into a complete recruitment intelligence platform by adding:

* Resume upload interface
* Automated resume parsing
* Skill extraction
* Job-description matching
* Resume-to-job similarity scoring
* Candidate ranking
* Explainable recommendations
* Streamlit deployment
* REST API integration
* Larger and more diverse resume datasets
* Advanced NLP models such as BERT or sentence embeddings

---

## 👩‍💻 Author

**Ruthvi Lohar**

Data Analytics | Machine Learning | NLP | AI

This project was developed as a hands-on machine learning project to demonstrate an end-to-end approach to solving a real-world recruitment and resume-screening problem.

