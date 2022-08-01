# Diabetes-Detection
The goal of this project was to detect Diabetes using XGBoost based on the information of more than 70,000 patients through the questionnaire that they filled out for the Organization for Disease Control and Prevention.
## Table of Contents
- [Project Description](https://github.com/mahvash-siavashpour/Diabetes-Detection#project-description)
- [Dataset](https://github.com/mahvash-siavashpour/Diabetes-Detection#dataset)
- [Preprocessing](https://github.com/mahvash-siavashpour/Diabetes-Detection#Preprocessing)
- [XGBoost Model](https://github.com/mahvash-siavashpour/Diabetes-Detection#XGBoost-Model)
- [Hyperparameter Tuninning](https://github.com/mahvash-siavashpour/Diabetes-Detection#Hyperparameter-Tuninning)
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
1. **NULL Values:** <br>
  First I found all null values and then replace them by either the mean(numerical) or the mode(categorical and binary) of that column.
  By doing so we can keep and refine the dataset with out removing any data.
2. **Unifying White Spaces:** <br>
  After finding all white spaces in the column names of data, I replaced them with a "-" making the names Kebab Case.
3. **Normalizing:** <br>
  Different feature have different ranges of values. Scaling them into a specific range helps a lot with in the training of the model.
5. **Categorical Features:** <br>
  Some features are categorical and for us to be able to use them in numerical formats I changed them into numerical vectors using one-hot-encoding.
## XGBoost Model
XGBoost is an open-source software library which provides a regularizing gradient boosting framework for C++, Java, Python, R, Julia, Perl, and Scala. It works on Linux, Windows, and macOS. From the project description, it aims to provide a "Scalable, Portable and Distributed Gradient Boosting Library".([Wikipedia](https://en.wikipedia.org/wiki/XGBoost)) <br>
In this phase of the project I created an XGBClassifier with the parameters specified bellow: <br>
```
model = XGBClassifier(
            tree_method='gpu_hist',
            Learning_rate=0.1,
            Max_depth=4,
            N_estimator=200,
            Subsample=0.5,
            Colsample_bytree=1,
            Random_seed=123,
            Eval_metric='auc',
            Verbosity=1)
```
And then trained the model. The results after the training are available in the notebook.
## Hyperparameter Tuninning
There are many parameters that can affect the model. In order to find the best parameters for our model we use GridSearchCV to do a cross-validation constructiong the model with different combinations of the parameters and then scoring them. The candidate lists of the parameters are shown bellow:
```
learning_rate_list = [0.02, 0.05, 0.1, 0.3] 
max_depth_list = [2, 3, 4] 
n_estimators_list = [100, 200, 300] 
colsample_bytree = [0.8, 1]
```
The results obtained and all the details are available in the notebook.
