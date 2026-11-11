
# Cross-Domain Sentiment Analysis Using Genetic Algorithm-Based Feature Optimization

## Overview

This project explores cross-domain sentiment classification using Natural Language Processing and machine learning.

The system uses a Genetic Algorithm (GA) to search for effective text feature configurations and Logistic Regression to classify sentiment across different review domains.

The project focuses on evaluating how well a model trained on certain review domains generalizes to an unseen domain.

## Domains

Three review domains are used:

- Phone reviews
- Movie reviews (IMDb)
- Restaurant reviews (Yelp)

The combined dataset contains 119,893 records before the domain-specific train/test splits.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- TF-IDF Vectorization
- Count Vectorization
- Logistic Regression
- Genetic Algorithm

## Methodology

### 1. Data Preparation

The datasets are loaded and converted into a common structure containing review text, sentiment labels, and domain information.

The sentiment labels are mapped into three classes:

- 0: Negative
- 1: Neutral
- 2: Positive

The datasets are cleaned by removing missing values and standardizing their columns.

### 2. Text Feature Extraction

Two text vectorization methods are evaluated:

- TF-IDF Vectorizer
- Count Vectorizer

The configuration search considers:

- N-gram range
- Vectorizer type
- Stopword removal
- Maximum number of features

### 3. Classification

Logistic Regression is used as the classification algorithm.

The model uses balanced class weights and is evaluated using:

- Accuracy
- Macro F1-score

### 4. Genetic Algorithm-Based Optimization

A Genetic Algorithm searches for suitable feature extraction configurations.

Each individual represents a combination of feature extraction settings.

The algorithm uses:

- Random population initialization
- Fitness evaluation
- Tournament selection
- Crossover
- Mutation
- Elitism

The search runs with a population size of 8 across 5 generations.

### 5. Cross-Domain Evaluation

The generalist evaluation excludes one domain from training and uses that domain as the unseen evaluation domain.

This process is designed to examine how well the model generalizes to review data from a different domain.

## Dataset Summary

| Domain | Records |
|---|---:|
| Phone reviews | 49,997 |
| Movie reviews | 50,000 |
| Restaurant reviews | 19,896 |
| Total | 119,893 |

The original datasets are not included in this repository.

## Results

One completed held-out experiment is documented below.

| Evaluation | Accuracy | Macro F1 |
|---|---:|---:|
| Restaurant-specific model | 0.8465 | 0.7207 |
| Generalist model evaluated on restaurant reviews | 0.6917 | 0.5477 |

The generalist model was trained using the phone and movie review domains, with restaurant reviews held out for evaluation.

These results illustrate the challenge of transferring sentiment classification across domains.

## Project Structure

```text
cross-domain-sentiment-analysis/
├── README.md
├── requirements.txt
├── notebooks/
│   └── cross_domain_sentiment_analysis.ipynb
├── results/
│   └── model_performance.md
└── docs/
    └── methodology.md
```

## How to Run

1. Clone the repository.
2. Install the required Python libraries.
3. Place the required datasets in the expected data directory.
4. Update the dataset paths in the notebook.
5. Open the notebook in Google Colab or Jupyter Notebook.
6. Run the cells in sequence.

## Future Improvements

- Evaluate additional review domains.
- Improve generalization across unseen domains.
- Experiment with alternative optimization strategies.
- Compare Logistic Regression with other classification algorithms.
- Use validation data for Genetic Algorithm fitness evaluation.

## Authors

Developed as an academic machine learning project.
