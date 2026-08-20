# LebanonPulse

LebanonPulse is a machine learning project for sentiment analysis of Lebanese Arabic reviews.

The project investigates whether a sentiment classifier can reliably detect negative feedback when the dataset contains many more positive reviews than negative ones.

## Dataset

The project uses the OCLAR (Opinion Corpus for Lebanese Arabic Reviews) dataset from the UCI Machine Learning Repository.

The original dataset contains 3,916 Lebanese Arabic reviews with ratings from 1 to 5 stars.

For binary sentiment classification:
- 1–2 stars were labeled **Negative**
- 4–5 stars were labeled **Positive**
- 3-star reviews were excluded because their sentiment is more ambiguous

This resulted in 3,498 reviews:
- 3,047 Positive
- 451 Negative

## Method

Two models were compared:

1. Baseline TF-IDF + Logistic Regression
2. TF-IDF + Logistic Regression with balanced class weights

The dataset was divided into 80% training and 20% testing data.

## Results

| Model | Accuracy | Negative Recall | Negative F1 |
|---|---:|---:|---:|
| Baseline | 89.6% | 18.9% | 0.318 |
| Balanced | 88.0% | 65.6% | 0.584 |

Although the baseline achieved slightly higher overall accuracy, it detected only 18.9% of negative reviews. Class balancing increased negative recall to 65.6% while reducing overall accuracy only slightly.

This demonstrates why accuracy alone can be misleading for imbalanced datasets.

## Demo

The final notebook includes a simple function that accepts a Lebanese Arabic review and predicts whether its sentiment is Positive or Negative.

## Tools

- Python
- pandas
- scikit-learn
- matplotlib
- Google Colab

## Limitations

The dataset is relatively small and highly imbalanced. Sentiment labels are based on star ratings, which may not always perfectly represent the sentiment expressed in the text. Future work could explore larger datasets, neutral sentiment, aspect-based sentiment analysis, and transformer-based Arabic language models.
