# Stroke Prediction

<div>
<img src="https://github.com/gprzy/stroke-prediction/blob/main/assets/stroke.jpeg" width="50%" height="50%"/>
</div>

[![Open in colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gprzy/stroke-prediction/blob/main/stroke_prediction.ipynb)
[![GitHub license](https://img.shields.io/github/license/microsoft/ML-For-Beginners.svg)](https://github.com/gprzy/stroke-prediction/blob/main/LICENSE)

This project is a professional test for the position of Data Scientist, in which a problem of predicting stroke in patients is explored with machine learning. Furthermore, several steps of a typical data science project are covered, such as EDA, feature selection, as well as testing tree-based and neural network models.
 
 # Problem
 
According to the World Health Organization (WHO) stroke is the 2nd leading cause of death globally, responsible for approximately 11% of total deaths.
This dataset is used to predict whether a patient is likely to get stroke based on the input parameters like gender, age, various diseases, and smoking status. Each row in the data provides relavant information about the patient. Continue reading [here](https://www.kaggle.com/fedesoriano/stroke-prediction-dataset).

# Binary classification

The problem can be approached as a binary classification task, in which the main objective is to correctly classify patients who are most likely to have a stroke. The data in question is unbalanced, making it difficult and inaccurate to use metrics such as accuracy. In this case, the metric chosen was the KS (Kolmogorov-Smirnov), as well as the ROC curve. From the metrics above, the equal error rate (EER) was calculated, as well as the optimal threshold to correctly classify the largest number of stroke patients as likely to have stroke (true positives).

Data can be obtained here: https://www.kaggle.com/fedesoriano/stroke-prediction-dataset

According to the [data source](https://www.kaggle.com/fedesoriano/stroke-prediction-dataset), this is the description of the features:

- `id`: unique identifier
-  `gender`: "Male", "Female" or "Other"
- `age`: age of the patient
- `hypertension`: 0 if the patient doesn't have hypertension, 1 if the patient has hypertension
- `heart_disease`: 0 if the patient doesn't have any heart diseases, 1 if the patient has a heart disease
- `ever_married`: "No" or "Yes"
- `work_type`: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"
- `Residence_type`: "Rural" or "Urban"
- `avg_glucose_level`: average glucose level in blood
- `bmi`: body mass index
- `smoking_status`: "formerly smoked", "never smoked", "smokes" or "Unknown"*
- `stroke`: 1 if the patient had a stroke or 0 if not

# Results

The **recall** in test, using the ``StackingClassfier`` (combining ``RanfomForestClassifier``, ``LinearSVC`` and ``MLP``) was **94%** for stroke patients (**59 of 63 correct predictions** in affirmative cases). Furthermore, the ``RanfomForestClassifier`` model was loaded into a class for use, as well as subjected to SHAP analysis for explainability.

<br>

<div align="center">
<img src="https://github.com/gprzy/stroke-prediction/blob/main/assets/summary.jpg" width="85%" height="80%"/> <br>
The SHAP chart is about the <code>RanfomForestClassifier</code>, as is the ROC curve. The confusion matrix is about <code>StackingClassifier</code>.
</div>
