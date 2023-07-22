# IMDB Dataset BERT
Fine-tuning BERT machine learning on an [IMDB movie reviews dataset](https://ai.stanford.edu/~amaas/data/sentiment/) to predict the rating and a sentiment of a review. Regression was chosen instead of classification for two reasons:
1) The original dataset does not contain any samples with ratings 5 and 6. Because of that, it would be unlikely for a classification model to predict the correct rating of such reviews if given to a model.
2) The classification model would equally penalize errors that are off by a large and a small amount.

Because the rating values are discrete (1 - 10), the results were rounded to the nearest integer. The ones that were less than one were assigned a value of 1 and the ones greater than 10 were assigned a value of 10.

Metrics values on a test dataset:

Metric | Value
---|---
MSE | 2.525892
Accuracy of binary classification (pos/neg) | 0.933480
Accuracy for multilabel classification (1-10) | 0.460360
Precision | 0.508720
Recall | 0.460360
F-score | 0.478250

[Flask app with this model](https://github.com/SergeyKeik/RatingPredictionFlaskApp)
