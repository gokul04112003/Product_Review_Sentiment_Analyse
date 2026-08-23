# 🤖 Product Review Sentiment Analysis using Transformers

## 📌 Overview

This project develops a sentiment analysis system for product reviews using **Transformer-based sentence embeddings** combined with traditional machine learning classifiers.

The system classifies customer reviews into three sentiment categories:

- 🟢 Positive
- 🟡 Neutral
- 🔴 Negative

The project uses the pre-trained **Sentence Transformer `all-MiniLM-L6-v2`** to convert product reviews into numerical sentence embeddings. These embeddings are then used to train and evaluate **Random Forest** and **Gradient Boosting** classifiers.

The final model selected for deployment is the **Random Forest classifier with Transformer embeddings**, based on its test performance and generalization compared with Gradient Boosting.

---

## 🎯 Problem Statement

Customer reviews contain valuable information about customer satisfaction, product performance, usability, and perceived value.

However, manually analyzing a large number of reviews is difficult and time-consuming.

This project aims to automatically classify product reviews into:

- Positive
- Neutral
- Negative

This can help businesses identify customer satisfaction levels and discover areas that may require improvement.

---

## 🎯 Objective

The main objectives of this project are:

1. Load and process product review data.
2. Perform basic data cleaning and exploratory data analysis.
3. Generate sentence-level embeddings using a pre-trained Transformer model.
4. Train machine learning classifiers using the generated embeddings.
5. Evaluate model performance using Accuracy and F1 Score.
6. Compare Random Forest and Gradient Boosting models.
7. Select the better-performing model for final deployment.

---

## 📊 Dataset

The dataset contains product review information with the following columns:

| Column | Description |
|---|---|
| `Product ID` | Unique identification number for each product |
| `Product Review` | Customer review or opinion about the product |
| `Sentiment` | Sentiment associated with the review |

### Dataset Statistics

- Original records: **1,007**
- Columns: **3**
- Missing values: **0**
- Duplicate rows: **2**
- Duplicate rows were removed before modeling.

The dataset contains a majority of positive reviews, while neutral and negative reviews are significantly smaller classes.

---

## 🧠 Methodology

The overall workflow of the project is:

```text
Product Reviews
       │
       ▼
Data Loading
       │
       ▼
Data Cleaning
       │
       ├── Missing Value Check
       └── Duplicate Removal
       │
       ▼
Exploratory Data Analysis
       │
       ▼
Sentence Transformer
(all-MiniLM-L6-v2)
       │
       ▼
Sentence Embeddings
       │
       ▼
Train-Test Split
       │
       ├───────────────┐
       ▼               ▼
Random Forest    Gradient Boosting
       │               │
       ▼               ▼
   Evaluation       Evaluation
       │               │
       └───────┬───────┘
               ▼
        Model Comparison
               │
               ▼
        Final Model Selection
