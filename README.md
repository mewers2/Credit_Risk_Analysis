# Credit_Risk_Analysis

## Project Overview
The purpose of this project is to evaluate credit card risk using a supervised machine learning algorithm and a dataset consisting of both input data and output data.  Since credit risk is typically quite unbalanced, meaning that most loans are good loans as opposed to high risk, the goal is to address this unbalance through the use of resampling the data.  This project applies four different types of resampling and then utilizes two machine learning models that are known to reduce bias, in order to predict credit risk.

## Results

### Resampling Technique Results (each used logistic regression model)

Each of these four iterations tested a different resampling technique with the original dataset to address the unbalance in the data and then applied the resampled data to a logistic regression machine learning model.

#### Random Oversampling

![naive_oversampling](https://github.com/mewers2/Credit_Risk_Analysis/blob/main/Resources/naive_oversampling.png)

- The random oversampling classifier yielded a 0.661 balanced accuracy score, which indicates 66.1% of the predictions are correct.
- The random oversampling classifier precision metric is 0.01 at predicting high-risk loans.  Meaning 1% of positive high-risk predictions are correct.
- The random oversampling classifer recall scored 0.72 at correctly predicting high-risk loans.  Meaning 72% of the actual high-risk loans were predicted correctly.

#### SMOTE Oversampling

![smote](https://github.com/mewers2/Credit_Risk_Analysis/blob/main/Resources/smote.png)

- The SMOTE oversampling classifier yielded a 0.658 balanced accuracy score, which indicates 65.8% of the predictions are correct.
- The SMOTE oversampling classifier precision metric is 0.01 at predicting high-risk loans.  Meaning 1% of positive high-risk predictions are correct.
- The SMOTE oversampling classifer recall scored 0.62 at correctly predicting high-risk loans.  Meaning 62% of the actual high-risk loans were predicted correctly.

#### Undersampling

![cc_undersampling](https://github.com/mewers2/Credit_Risk_Analysis/blob/main/Resources/cc_undersampling.png)

- The centroid clustering undersampling classifier yielded a 0.544 balanced accuracy score, which indicates 54.4% of the predictions are correct.
- The centroid clustering undersampling classifier precision metric is 0.01 at predicting high-risk loans.  Meaning 1% of positive high-risk predictions are correct.
- The centroid clustering undersampling classifer recall scored 0.69 at correctly predicting high-risk loans.  Meaning 69% of the actual high-risk loans were predicted correctly.

#### Combination Resampling (SMOTEENN)

![combo_resampling](https://github.com/mewers2/Credit_Risk_Analysis/blob/main/Resources/combo_resampling.png)

- The combination SMOTEENN classifier yielded a 0.671 balanced accuracy score, which indicates 67.1% of the predictions are correct.
- The combination SMOTEENN classifier precision metric is 0.01 at predicting high-risk loans.  Meaning 1% of positive high-risk predictions are correct.
- The combination SMOTEENN classifer recall scored 0.77 at correctly predicting high-risk loans.  Meaning 77% of the actual high-risk loans were predicted correctly.


### Ensemble Machine Learning Models

Each of these iterations ran the original dataset through an ensemble classifier to resample it and reduce the bias and make predictions.

#### Balanced Random Forest Classifier

![brf](https://github.com/mewers2/Credit_Risk_Analysis/blob/main/Resources/brf.png)

- The balanced random forest classifier yielded a 0.787 balanced accuracy score, which indicates 78.7% of the predictions are correct.
- The balanced random forest classifier precision metric is 0.04 at predicting high-risk loans.  Meaning 4% of positive high-risk predictions are correct.
- The balanced random forest classifer recall scored 0.67 at correctly predicting high-risk loans.  Meaning 67% of the actual high-risk loans were predicted correctly.

#### Easy Ensemble Classifier

![ez_ensemble](https://github.com/mewers2/Credit_Risk_Analysis/blob/main/Resources/ez_ensemble.png)

- The easy ensemble classifier yielded a 0.925 balanced accuracy score, which indicates 92.5% of the predictions are correct.
- The easy ensemble classifier precision metric is 0.07 at predicting high-risk loans.  Meaning 7% of positive high-risk predictions are correct.
- The easy ensemble classifer recall scored 0.91 at correctly predicting high-risk loans.  Meaning 91% of the actual high-risk loans were predicted correctly.

## Summary
Based on the results reported above, the first four resampling techinques which employed a logistic regression model all performed at a less than 68% accuracy rate with the combination resampling (SMOTEENN) scoring the highest at 67.1% and the centroid clustering undersampling scoring the lowest at 54.4%.  All four resampling techniques scored a 1% precision metric and their sensitivities varied between 62% and 77%.  None performed well enough to earn a recommendation for use with predicting credit risk.

The ensemble classifiers performed better.  The balanced random forest classifier was able to raise its accuracy to 78.7%, marginally better than the others, raised a precision score of 4% and a 67% sensitivity score.  The balanced random forest classifier performed slightly better than the others, but not well enough to recommend for use.  Lastly, the easy ensemble classifier produced a 92.5% accuracy score, 7% precision score, and a 91% sensitivity score.  If the purpose for the machine learning credit risk prediction is to develop a model that excels at recall, the easy ensemble classifier is the recommended model here.  If the purpose of the credit risk prediction is to be precise, none of these models perform well enough for real application, at worst 1% and at best 7% precision simply will not perform at a useful level.