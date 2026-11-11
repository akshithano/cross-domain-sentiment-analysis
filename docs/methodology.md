
# Methodology

## 1. Dataset Preparation

Three datasets are combined:

- Phone reviews
- IMDb movie reviews
- Yelp restaurant reviews

Each dataset is converted into a shared structure with text, sentiment label, and domain.

## 2. Sentiment Label Mapping

The labels are mapped into three sentiment classes:

- Negative: 0
- Neutral: 1
- Positive: 2

## 3. Feature Extraction

The notebook tests two vectorization methods:

- CountVectorizer
- TfidfVectorizer

The following parameters are optimized:

- N-gram range: (1,1), (1,2), (1,3)
- Stopword removal: enabled or disabled
- Maximum features: 3,000, 5,000, 10,000

## 4. Classification

Logistic Regression is used with balanced class weights.

The classifier is evaluated using accuracy and macro F1-score.

## 5. Genetic Algorithm

Each chromosome represents four feature configuration choices:

1. Vectorizer type
2. N-gram range
3. Stopword setting
4. Maximum feature count

The algorithm performs:

1. Population initialization
2. Fitness evaluation
3. Tournament selection
4. Crossover
5. Mutation
6. Elitism

The notebook uses a population size of 8, five generations, and a mutation rate of 0.20.

## 6. Cross-Domain Evaluation

One review domain is excluded from the training data.

The model is trained using the remaining domains and evaluated on the excluded domain.

This provides an experiment for studying generalization to unseen review domains.
