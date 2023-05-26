# Stroke Prediction Model - Rennala

This repository contains code for a stroke prediction model based on the "Stroke Prediction Dataset." The dataset includes various features related to individuals' health and lifestyle factors and whether they have experienced a stroke. The goal is to develop a model that can predict the likelihood of a stroke based on these features.

## Files

- `healthcare-dataset-stroke-data.csv`: The original dataset containing the stroke-related features.
- `train.csv`: Training data used to build the prediction model.
- `test.csv`: Test data for evaluating the model's performance.
- `sample_submission.csv`: A sample submission file for the competition.
- `submission.csv`: The final submission file generated by the model.
- `model.ipynb`: The main Python script containing the model training and prediction functions.
- `gradio.ipynb`: The support Python script implementing an interface using gradio.
- `stroke_model.pkl` : The model that is created in `model.ipynb`. Used in gradio
- `readme.md`: This readme file providing an overview of the project.

## Data Preprocessing

- The missing values in the "bmi" column are imputed using a decision tree regressor.
- The "gender" column is encoded as numeric values (0 for Male, 1 for Female, and -1 for Other).
- The "gender" column's "Other" category is replaced with "Female."
- Two new features, "morbid" and "obese," are created based on the "bmi" values.
- The "risk_factors" feature is calculated based on several relevant features.

## Feature Engineering

- Label encoding is applied to the "gender," "ever_married," and "work_type" columns.
- One-hot encoding is performed for the "smoking_status" column.
- The "id" and "Residence_type" columns are dropped from the dataset.

## Model Training

- The dataset is split into training and validation sets.
- LightGBM (Gradient Boosting Machine) is used as the classification model.
- The model is trained using 5-fold cross-validation.
- The area under the ROC curve (ROC-AUC) is used as the evaluation metric.
- The model's feature importances are plotted.

## Model Evaluation

- The model's performance is evaluated on the validation set using ROC-AUC.
- The ROC curves for each fold are displayed.
- The mean ROC-AUC score over the 5-fold cross-validation is calculated.

## Generating Predictions

- The trained model is used to generate predictions for the test dataset.
- The predictions are stored in the "submission.csv" file.

## Prediction Interface - Gradio

The code includes a Gradio-based interface for making stroke risk predictions. The `predict` function takes various input parameters such as name, gender, age, health conditions, and lifestyle factors. It preprocesses the inputs and uses the trained model to predict the risk of stroke. The prediction result is returned as a message.

## Authors
- Sıla Sinem Soydan
- Ceren Çatkın
- Mehmet Arif Kuzgun    
***Established by IKC™***
