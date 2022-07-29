# Diabetes-Detection
The goal of this project was to detect Diabetes using XGBoost based on the information of more than 70,000 patients through the questionnaire that they filled out for the Organization for Disease Control and Prevention.
## Table of Contents
- [Project Description](https://github.com/mahvash-siavashpour/Diabetes-Detection/blob/main/README.md#project-description)
- [Dataset](https://github.com/mahvash-siavashpour/Diabetes-Detection/blob/main/README.md#Dataset)
- [Preprocessing](https://github.com/mahvash-siavashpour/Diabetes-Detection/blob/main/README.md#Preprocessing)
- [XGBoost Model](https://github.com/mahvash-siavashpour/Diabetes-Detection/blob/main/README.md#XGBoost-Model)
- [Hyperparameter Tuninning](https://github.com/mahvash-siavashpour/Diabetes-Detection/blob/main/README.md#Hyperparameter-Tuninning)
## Project Description
In this project a Diabetes detection model has been constructed using XGBoost or Extreme Gradient Boost, which is an open source library used for parallel tree boosting. After construnction the model, it is trained on the information of more than 70,000 patients through the questionnaire that they filled out for the Organization for Disease Control and Prevention.
## Dataset
The data used in this project is the information of more than 70,000 patients through the questionnaire that they filled out for the Organization for Disease Control and Prevention. The dataset contains 22 columns as described bellow:
- HighBP: High Blood Pressure
- High Cholesterol
- Cholesterol Check: Whether the patient has done a cholesterol check
- BMI: Body Mass Index
- Smoker
- Stroke
- HeartDiseaseorAttack
- Physical Activity
- Fruits
- Veggies
- Heavy Alcohol Consumption
- Any Health Care
- No Doctor because of Cost: Whether the patient posponed or canceled a doctor's appointment due to the costs
- General Health
- Mental Health
- Physical Health
- Difficulty Walking
- Sex: Gender
- Age
- Education
- Income
## Preprocessing
Before doing any training, a series of preprocessing has been done on the data. 
1. NULL Values: 
  First I found all null values and then replace them by either the mean(numerical) or the mode(categorical and binary) of that column.
  By doing so we can keep and refine the dataset with out removing any data.
2. Unifying White spaces: 
  After finding all white spaces in the column names of data, I replaced them with a "-" making the names Kebab Case.
3. Normalizing:
4. Categorical Features:
## XGBoost Model

## Hyperparameter Tuninning

