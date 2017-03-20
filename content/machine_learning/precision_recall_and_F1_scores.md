Title: Precision, Recall, and F1 Scores   
Slug: precision_recall_and_F1_scores     
Summary: An explanation of precision, recall, and F1 scores.    
Date: 2016-12-09 11:00    
Category: Machine Learning   
Tags: Model Evaluation  
Authors: Chris Albon


## Some Terms:

Positive (P): Observation is positive (for example: is an apple)

Negative (N): Observation is not positive (for example: is not an apple).



True Positive (TP): Observation is positive, and is predicted to be positive.

False Negative (FN): Observation is positive, but is predicted negative.



True Negative (TN): Observation is negative, and is predicted to be negative.

False Positive (FP): Observation is negative, but is predicted positive.



## Error:

Proportion of all predictions that are incorrect. Error is a measurement of how bad a model is.

$$error = \frac{FP+FN}{FP+FN+TP+TN} = \frac{\text{incorrect predictions}}{\text{all predictions}}$$



## Accuracy:

Proportion of all predictions that are correct. Accuracy is a measurment of how good a model is.

$$accuracy = \frac{TP+FN}{TP+FN+TP+TN} = \frac{\text{correct predictions}}{\text{all predictions}}$$



## False Positive Rate:

Proportion of all negative observation that are predicted incorrectly. False positive rate is a measure of how good a model is at predicting negative cases.

$$FPR = \frac{FP}{FP+TN} = \frac{FP}{N} = \frac{\text{predicted to be positive}}{\text{all negative observations}}$$




## True Positive Rate:

Proportion of all positive observation that are predicted incorrectly. True positive rate is a measure of how good a model is at predicting positive cases.

$$TPR = \frac{TP}{TP+FN} = \frac{TP}{P} = \frac{\text{predicted to be positive}}{\text{all positive observations}}$$



## Precision:

Proportion of all positive predictions that are correct. Precision is a measure of how many positive predictions were actual positive observations.

$$Precision = \frac{TP}{TP+FP} = \frac{\text{positive predicted correctly}}{\text{all positive predictions}}$$



Memory aid: "**P**recision is about the **P**redicted **P**ositives": correctly **P**redicted **P**ositives divided by all **P**redicted **P**ositives, $\frac{\text{Correctly Predicted Positive}}{\text{All Predicted Positive}}$.

## Recall:

Same as TPR. Proportion of all real positive observations that are correct. Precision is a measure of how many actual positive observations were predicted correctly.

$$Recall = TPR = \frac{TP}{TP+FN} = \frac{TP}{P} = \frac{\text{predicted to be positive}}{\text{all positive observations}}$$



Memory aid: "Recall is about the re-all (real) positives" $\frac{\text{Correctly Predicted Positive}}{\text{All Real Positives}}$



## F1 Score:

The [harmonic mean](https://en.wikipedia.org/wiki/Harmonic_mean) of precision and recall. F1 score is an 'average' of both precision and recall. We use the harmonic mean because it is the appropriate way to average ratios (while arthmetric mean is appropriate when it conceptually makes sense to add things up).

$$F1 = 2\frac{Precision * Recall}{Precision + Recall}$$
