# Predicting-Obesity-Levels-with-Machine-Learning
A Data Science Project Using UCI’s Lifestyle and Eating Habits Dataset.

## Overview 
This project explores how eating, habits, physical activity, and lifestyle choices influece obesity leves. Using the **UCI "Estimation of Obesity Levels Based on Eating Habits and Physical Condition** dataset, I will perform an exploratory data analysis (EDA), feature importance evaluation, and machine learning classification to identify the main factores that contribute to obesity.

## Objectives
1. **Indentify the main factores associated with obesity levels.**
2. **Develop a predictive model** capable of classifying individuals into obesity categories.
3. **Evaluate the influence of eating and exercise habits** using feature importance techniques.
4. **Visualize relationships** between lifestyle variables and obesity levels.

## Dataset
- **Source:** [UCI Irvine Machine Learning Repository](https://archive.ics.uci.edu/dataset/544/estimation+of+obesity+levels+based+on+eating+habits+and+physical+condition)
- **Instances:** 2111
- **Features:** 17

### Example Features:
| Variable | Description |
|-----------|--------------|
| Gender | Male / Female |
| Age | Age of the individual |
| Height / Weight | Physical condition |
| FCVC | Frequency of vegetable consumption |
| NCP | Number of main meals per day |
| CH2O | Daily water intake |
| FAF | Frequency of physical activity |
| TUE | Time using technology devices |
| CALC | Alcohol consumption |
| NObeyesdad | Obesity level (target variable) |


## Feature Importance 
### **RandomForest (Randomized Search)**
| Rank | Variable | Importancia |
|------|-----------|-------------|
| 1 | Weight | 0.3081 |
| 2 | Age | 0.0949 |
| 3 | FCVC | 0.0939 |
| 4 | Height | 0.0883 |
| 5 | Gender | 0.0552 |
| 6 | NCP | 0.0516 |
| 7 | TUE | 0.0475 |
| 8 | FAF | 0.0467 |
| 9 | CH2O | 0.0438 |
| 10 | CALC | 0.0342 |

**Weight, Age, FCVC and Height** were the most influential. 

### **XGBoost Classifier** 

| Rank | Variable | Importancia |
|------|-----------|-------------|
| 1 | Gender | 0.1537 |
| 2 | Weight | 0.1514 |
| 3 | FCVC | 0.1087 |
| 4 | family_history_with_overweight_yes | 0.0604 |
| 5 | family_history_with_overweight_no | 0.0535 |
| 6 | CALC | 0.0520 |
| 7 | Height | 0.0446 |
| 8 | CAEC | 0.0414 |
| 9 | CH2O | 0.0408 |
| 10 | FAVC_yes | 0.0406 |

The variables that stood ut were **Gender, Weigth, FCVC** as the most important features. As well with features related with **family history with overweight** and **eating habits**. 

### Model Evaluation
To evaluate the stability and generalization of both models, it was applied a Stratified K-Fodl with 5 partitions.
This guarantees that the class proportions remains balanced in each iteration.
| Model |  Accuracy (CV Mean ± SD) | Interpretation|
|-------|---------------------|---------|
| **Random Forest (Randomized Search)** | 0.9402 ±0.0114 | High performance and consistency between folds |
| **XGBoost Classifier** | 0.9396 ± 0.0061|Similar performance to RandomForest, with lower variance, but inferior in overall metrics | 

### Interpretation
- Both models have **high predictive capacity**, surpassing 93% accuracy.
- **Optimized RandomForest** was slightly superior, being the better option for interpretation and with training times.
- Both models stand out **Weight, Height and FCVC (Frequency of vegetable consumption) as important features.
- The last suggets that a **combination of physical and eating habits** offer a better predictive understanding to estimate the obesity levels. 
