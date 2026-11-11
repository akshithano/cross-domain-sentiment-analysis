
# Model Performance

## Domain-Specific Experiments

| Domain | Accuracy | Macro F1 |
|---|---:|---:|
| Phone reviews | 0.7080 | 0.6659 |
| Movie reviews | 0.8985 | 0.8985 |
| Restaurant reviews | 0.8465 | 0.7207 |

## Held-Out Domain Experiment

The generalist model was trained using phone and movie reviews, while restaurant reviews were excluded from training.

| Evaluation | Accuracy | Macro F1 |
|---|---:|---:|
| Generalist model on unseen restaurant reviews | 0.6917 | 0.5477 |

## Interpretation

The results show that domain-specific models and generalist models can behave differently when evaluated across review domains.

The held-out restaurant experiment demonstrates the difficulty of transferring sentiment classification patterns between different types of reviews.

Note: The notebook contains additional experiments for other held-out domains. Their final results should be added after verifying the complete output.
