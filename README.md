# Adult-Income
- *Author: Faris Assallami*

## Source of data 
-US Census Bureau

## Brief description of data 
-A persons age, hours worked per week, income and occupation

-The target is Income

-Each row represents a person

-There are 15 features

-There are 48842 rows

#  Business Problem

After exploring adult income data, I created a model that can help employees currently in the labor market increase their income.  Methods used are Data Visualizations and Machine Learning.

#  Loading Data

Loaded the csv file into Jupyter Notebook

# Data Cleaning

Removed irrelevant columns that dont add any insight to the data.  Removed duplicate rows.  Filled in missing data with most frequent value.  Corrected inconsistencies and spelling errors in the data.

# Exploratory Visuals

## Using Histogram Subplots to display numeric features.

![numeric adult income](https://user-images.githubusercontent.com/111199631/230174355-64a51846-7e94-417e-aeb5-2a04e1ab9044.png)

---------------------------------------------------------

## Using Count Plot to display occupations by income greater than 50K or less than/equal to 50K

![countplot occupation](https://user-images.githubusercontent.com/111199631/230174773-2f8ff3f7-5acd-41a6-b08c-41e303d4e35c.png)

We can see from the countplot above that Prof-Specialty and Exec-managerial positions were the top 2 highest paying positions for incomes greater than 50K.  Also we can see an inconsistent value which we will imputer later on after we train/split our data for machine learning that way we avoid data leakage.

--------------------------------------------------------

## Using a Count Plot to show the relationship between Marital status and Income

![marital countplot](https://user-images.githubusercontent.com/111199631/230175584-f2185551-437a-490c-84db-2844aff813ca.png)


We can see from the count plot above that the Married couples had the most income above 50K which is most likely because both couples are working.

---------------------------------------------------------

## Using a Bar Plot to show the relationship between average hours worked between men and women and the income category.

![averagehoursgender barplot](https://user-images.githubusercontent.com/111199631/230175913-9c01eab3-cd1f-46df-9861-a84d262eda9e.png)

According to the bar plot above, we can see that on average men worked more hours per week on than women and earned more in the Greater than 50K income category.  This indicates that more hours worked leads to more income regardless of gender.

----------------------------------------------------------
## Using a Bar Plot to show the relationship between Race income and Education Years.

![education income by race barplot](https://user-images.githubusercontent.com/111199631/230177174-da2bbc3e-7c13-47a7-bf96-bd19d2a31cf4.png)

We can see that the highest educated race the asian-pacific islander tended to have the highest income.

----------------------------------------------------------

## Machine learning

After training the processed data I ran two models.  After tuning both models with optimal parameters the classification reports are below for both models that had the best accuracy and their confusion matrix.

---Tuned Random Forest Model---

Train Classification Report 

              precision    recall  f1-score   support

       <=50K       0.89      0.96      0.92     21610
        >50K       0.85      0.63      0.72      7326

    accuracy                           0.88     28936
   

Test Classification Report 

              precision    recall  f1-score   support

       <=50K       0.86      0.95      0.90      7228
        >50K       0.77      0.55      0.65      2418

    accuracy                           0.85      9646
   
   
   ![rftunedadultincome_matrix](https://user-images.githubusercontent.com/111199631/230178350-633e8986-69ea-47a2-a96f-2cd6f9bc3c70.png)

  
---KNN Model---

Train Classification Report 

              precision    recall  f1-score   support

       <=50K       0.89      0.94      0.91     21610
        >50K       0.78      0.66      0.71      7326

    accuracy                           0.87     28936
   

Test Classification Report 

              precision    recall  f1-score   support

       <=50K       0.85      0.89      0.87      7228
        >50K       0.61      0.53      0.57      2418

    accuracy                           0.80      9646
    
   
![tunedKNN-adultincome-matrix](https://user-images.githubusercontent.com/111199631/230178817-d06b7042-ec25-422f-8a7f-11e7d7d2a2e9.png)


After running a GridSearchCV to opbtain opitmal parameters for the KNN model, the new accuracy of the Best KNN Model is the same at .8031 which is the same as the Un-Tuned KNN model.

-------------------------------------------------------

## Model Selection

The model I will select is the Tuned Random Forest model which had an accuracy of 85% which was higher than the best KNN model accuracy of 80.31%.  The Tuned Random Forest model also had the lowest type 1 & 2 errors out of all the models.

 
--------------------------------------------------------

## Recommendations

Recommendation to increase income is by increasing education to get into higher paying jobs and to work extra hours overtime when available to employee.
