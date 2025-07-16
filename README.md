# Tweet Annotation Analysis Using Logistic Regression | Python

**Contributors**:
- Amberly Cavazos  
- Marco Ortiz 
- Chinmeri Nwagwu  
- Shutao Zhang

---

## 📃 Table of Contents

1. [Project Overview](#-project-overview)
2. [Files](#-files)
3. [Methodology](#-methodology)
    - [Preprocessing](#preprocessing)
    - [Feature Engineering](#feature-engineering)
    - [Modeling](#modeling)
4. [Results](#-results)
    - [Technology Classification](#technology-classification)
    - [Political Classification](#political-classification)
5. [Tools and Libraries](#-tools-and-libraries)
6. [Output](#-output)
7. [Future Improvements](#-future-improvements)
8. [Key Takeaways](#-key-takeaways)

---

## 📝 Project Overview

Built a logistic regression model using Python with 85%+ accuracy to classify 1,000 tweets as political or tech-focused. Utilized TF-IDF, TextBlob sentiment scoring, and lexical features; documented findings using Jupyter Notebook, Jupyter Lab, and GitHub.

---

## 📁 Files

- `Final_Annotated_Comments.xlsx` – Annotated dataset used for modeling.
- `best_model_predictions_tech.csv` – Results from the best model for technology classification.
- `best_model_predictions_pol.csv` – Results from the best model for political classification.
- `final_project_modeling.ipynb` – Jupyter Notebook with all code and outputs.

---

## 🧪 Methodology

### Preprocessing

- Removed missing values in comment or label fields.
- Converted labels to binary:
  - `Technology`: `"tech"` → 1, `"NoneTech"` → 0  
  - `Political`: `"Pol"` → 1, `"NoPol"` → 0

### Feature Engineering

Three types of features were extracted:

| Feature Type | Description |
|--------------|-------------|
| **TF-IDF** | Term Frequency–Inverse Document Frequency matrix using top 1000 features |
| **Sentiment (Lexicon)** | Sentiment polarity and subjectivity via TextBlob |
| **Structural** | Count of capital letters, exclamation marks, and total text length |

### Modeling

- Classifier: **Logistic Regression**
- Evaluation: **Macro F1 Score** and **Micro F1 Score**
- Split: 80% training, 20% testing (stratified)

---

## 📊 Results

### Technology Classification

| Feature Set  | Macro F1 | Micro F1 |
|--------------|----------|----------|
| TF-IDF       | 0.5726   | 0.6650   |
| Lexicon      | 0.3865   | 0.6300   |
| Structural   | 0.3990   | 0.6300   |

📉 **Best Model**: **TF-IDF**

### Political Classification

| Feature Set  | Macro F1 | Micro F1 |
|--------------|----------|----------|
| TF-IDF       | 0.4872   | 0.9500   |
| Lexicon      | 0.4872   | 0.9500   |
| Structural   | 0.7217   | 0.9650   |

📉 **Best Model**: **Structural**

---

## 🔧 Tools and Libraries

- **Python 3**
- `pandas`, `numpy`
- `sklearn` (Logistic Regression, metrics, train_test_split)
- `TextBlob` (sentiment analysis)
- `TfidfVectorizer` (feature extraction)
- `GitHub`
- `Jupyter Notebook`
- `Jupyter Lab`

---

## 📈 Output

Final predictions for each best-performing model were saved in CSV format:
- `best_model_predictions_tech.csv`
- `best_model_predictions_pol.csv`

These contain:
- Original tweet (`comment`)
- True label (`true_label`)
- Predicted label (`predicted_label`)

---

## 🚀 Future Improvements

- Incorporate deep learning models (e.g., BERT) for context-aware classification.
- Use multi-label classification to allow tweets to be both political and technological.
- Visualize model performance using confusion matrices and ROC curves.

---

## 🧠 Key Takeaways

- Lexical features (TF-IDF) perform well for content-related classification.
- Structural cues are strong indicators of political content.
- Combining multiple feature types could potentially improve accuracy further.
