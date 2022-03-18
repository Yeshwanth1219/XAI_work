# Fall 2021 XAI Work

# 1.Titanic Data Set
https://www.dropbox.com/s/1xi3sdaos7t88qp/Titanic%20Dataset.csv?dl=0

## Analyzing Model behavior over KFold:

**Random** ******Forest** ******Classifier: MEAN → 0.8148**
Selected Instance for SHAP analysis, (Baby (age less than a year) female): Survived = 1

        Pclass   Age    SibSp  Parch   Fare     Sex_female  Sex_male  Embarked_C 
        3        0.75     2     1      19.2583     1         0           1   
    
         Embarked_Q  Embarked_S     Survived
           0           0                1
| Test group | **Accuracy** | **SHAP Force Plot**                                                                                                                  |
| ---------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| Fold 1     | 0.756        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844708188_file.png) |
| Fold 2     | 0.82         | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844801001_file.png) |
| Fold 3     | 0.787        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844826477_file.png) |
| Fold 4     | 0.809        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844840129_file.png) |
| Fold 5     | 0.865        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844876406_file.png) |
| Fold 6     | 0.831        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844888642_file.png) |
| Fold 7     | 0.798        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844903004_file.png) |
| Fold 8     | 0.775        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844916076_file.png) |
| Fold 9     | 0.82         | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844929109_file.png) |
| Fold 10    | 0.854        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844945380_file.png) |

**S****upport** **Vector Machine: MEAN → 0.6814**

| Test group | **Accuracy** | **SHAP Force Plot**                                                                                                                  |
| ---------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| Fold 1     | 0.66         | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844786341_file.png) |
| Fold 2     | 0.674        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844808328_file.png) |
| Fold 3     | 0.663        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844833046_file.png) |
| Fold 4     | 0.674        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844868542_file.png) |
| Fold 5     | 0.663        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844882959_file.png) |
| Fold 6     | 0.719        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844895934_file.png) |
| Fold 7     | 0.652        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844910393_file.png) |
| Fold 8     | 0.742        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844923169_file.png) |
| Fold 9     | 0.73         | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844937917_file.png) |
| Fold 10    | 0.697        | ![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632844951463_file.png) |



![Plot of Accuracy vs Folds](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632236134680_image.png)


⬆️: Pushed prediction towards **Survived (1)**
⬇: Pushed prediction towards **Not Survived (0)**

| **Instance Criteria**                                       | **Random Forest**                          | **Support Vector Machine** | **Comments**                                                  |
| ----------------------------------------------------------- | ------------------------------------------ | -------------------------- | ------------------------------------------------------------- |
| **Female Baby**<br>(Age<5, female=1)<br>Actual o/p = 1      | Major Feature: **Age** ⬆️                  | Major Feature:  **Fare** ⬇ | **RF:** Predicted correctly<br>**SVM:** Predicted incorrectly |
| **Male Baby**<br>(Age<5, male=1)<br>Actual o/p = 1          | Major Feature: **Age** ⬆️                  | Major Feature: **Fare** ⬇  | **RF:** Predicted correctly<br>**SVM:** Predicted incorrectly |
| **Female Mid-age**<br>(Age==45, female=1)<br>Actual o/p = 0 | Major Feature: **PClass** ⬇                | Major Feature: **Fare** ⬇  | **RF:** Predicted correctly<br>**SVM:** Predicted correctly   |
| **Male Mid-age**<br>(Age==45, male=1)<br>Actual o/p = 0     | Major Feature: **Male** ⬇                  | Major Feature: **Fare** ⬆️ | **RF:** Predicted correctly<br>**SVM:** Predicted incorrectly |
| **Female old-age**<br>(Age>50, female=1)<br>Actual o/p = 1  | Major Feature: **Female** ⬆️               | Major Feature: **Fare** ⬆️ | **RF:** Predicted correctly<br>**SVM:** Predicted correctly   |
| **Male old-age**<br>(Age>50, male=1)<br>Actual o/p = 1      | Major Feature: **Fare**, **PClass** **⬆️** | Major Feature: **Fare** ⬇  | **RF:** Predicted correctly<br>**SVM:** Predicted incorrectly |



## Analysing Model behavior with Age group:

**Data insights:**

![Age group wise count](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1633452317505_image.png)



**Children (0-14** **y****ears):**

![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1633451448532_image.png)


**Youth (15-24 years):**

![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1633452945630_image.png)


**Adult (25-64 years):**

![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1633454902335_image.png)


**Senior (64 and over):**

![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1633455006292_image.png)


In senior citizens, we have **only one survival** and the records are not sufficient for the analysis.


## Analysing Model behavior with Gender:

Data Insights: 

![Count of Male and Female](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1633455269934_image.png)


**For Female:**

![Force Plot](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1633455341954_image.png)

![Summary Plot](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1633455928052_image.png)


Here, **PClass** is the significant feature for driving the prediction.

**For Male:**

![Force Plot](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1633455447112_image.png)

![Summary Plot](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1633455901691_image.png)


Here, **Age** is the significant feature for driving the prediction.

References
[Song, T., Huang, J., Tan, Y., & Yu, Y. (2019). Using](https://www.dropbox.com/s/8jgojho0n1jjana/Song%20et%20al_2019.pdf?dl=0) [0.](https://www.dropbox.com/s/8jgojho0n1jjana/Song%20et%20al_2019.pdf?dl=0)[user-and marketer-generated content for box office revenue prediction: Differences between microblogging and third-party platforms.](https://www.dropbox.com/s/8jgojho0n1jjana/Song%20et%20al_2019.pdf?dl=0) [*Information Systems Research*](https://www.dropbox.com/s/8jgojho0n1jjana/Song%20et%20al_2019.pdf?dl=0)[,](https://www.dropbox.com/s/8jgojho0n1jjana/Song%20et%20al_2019.pdf?dl=0) [*30*](https://www.dropbox.com/s/8jgojho0n1jjana/Song%20et%20al_2019.pdf?dl=0)[(1), 191-203.](https://www.dropbox.com/s/8jgojho0n1jjana/Song%20et%20al_2019.pdf?dl=0)

[Kokkodis, M. (2021). Dynamic, Multidimensional, and Skillset-Specific Reputation Systems for Online Work.](https://www.dropbox.com/s/0u3guq0e9ogpgek/Kokkodis%202021.pdf?dl=0) [*Information Systems Research*](https://www.dropbox.com/s/0u3guq0e9ogpgek/Kokkodis%202021.pdf?dl=0)[.](https://www.dropbox.com/s/0u3guq0e9ogpgek/Kokkodis%202021.pdf?dl=0)

[Yang X, Zhang Z, Zhang Z, Mo Y, Li L, Li Y (2016) Automatic construction and global optimization of a multi-sentiment lexicon. Comput. Intelligence Neurosci. 2016(5):1–8.](https://www.dropbox.com/s/j22jc7na7xwqucv/Yang%20et%20al_2016.pdf?dl=0)

## Accuracy Distribution
- **Table 1. Confusion Matrix**
    - For the whole population and the gender groups 

**Random Forest Classifier (Accuracy = 80.97%):**

|                                 | **Y =1 (Truly survive)** | **Y=0**                  |
| ------------------------------- | ------------------------ | ------------------------ |
| **L=1  (Predicted to survive)** | True positive (TP) = 73  | False positive (FP) = 16 |
| **L=0**                         | False negative (FN) = 30 | True negative (TN) = 149 |

![Confusion Matrix for Random Forest Classifier](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1631476318349_image.png)


**False Positive Rate:** 

    FP/FP+TN = 16/16+149 = 0.0969

**False Negative Rate:**

    FN/FN+TP = 30/30+73 = 0.2912

**True Positive Rate:** 

    TP/TP+FN = 73/73+30 = 0.7087

**True Negative Rate:**

    TN/TN+FP = 149/149+16 = 0.903
----------

**Support Vector Machine (Accuracy = 65.67%):**

|                                 | **Y =1 (Truly survive)** | **Y=0**                  |
| ------------------------------- | ------------------------ | ------------------------ |
| **L=1  (Predicted to survive)** | True positive (TP) = 26  | False positive (FP) = 15 |
| **L=0**                         | False negative (FN) = 77 | True negative (TN) = 150 |

![](https://paper-attachments.dropbox.com/s_362ECDA4D1CAEB058B2D840705C63E278A9583001F44FA85A24AB9F813DCA1AF_1632230661520_image.png)


**False Positive Rate:** 

    FP/FP+TN = 15/15+150 = 0.0909

**False Negative Rate:**

    FN/FN+TP = 77/77+26 = 0.7475

**True Positive Rate:** 

    TP/TP+FN = 26/26+77 = 0.2524

**True Negative Rate:**

    TN/TN+FP = 150/150+15 = 0.9090
| **Category**        | **Random Forest Classifier** | **Support Vector Machine** | **% Change** |
| ------------------- | ---------------------------- | -------------------------- | ------------ |
| False Positive Rate | 0.0969                       | 0.0909                     | -6.19%       |
| False Negative Rate | 0.2912                       | 0.7475                     | 156.69%      |
| True Positive Rate  | 0.7087                       | 0.2524                     | -64.38%      |
| True Negative Rate  | 0.903                        | 0.9090                     | 0.66%        |

----------
# 2.Credit Card Company's Customer Churning EDA and Prediction
https://www.dropbox.com/s/zysemoaq8hkpui9/BankChurners%20Dataset.xls?dl=0

## Context

A manager at the bank is disturbed with more and more customers leaving their credit card services. They would really appreciate if one could predict for them who is gonna get churned so they can proactively go to the customer to provide them better services and turn customers' decisions in the opposite direction
Now, this dataset consists of 10,000 customers mentioning their age, salary, marital status, credit card limit, credit card category, etc. There are nearly 18 features.
We have only 16.07% of customers who have churned.` 

**Data Dictionary**

| Variable                 | Description                                                                                                                         |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| CLIENTNUM                | Client number. Unique identifier for the customer holding the account                                                               |
| Attrition_Flag           | Internal event (customer activity) variable - if the account is closed then 1 else 0                                                |
| Customer_Age             | Demographic variable - Customer's Age in Years                                                                                      |
| Gender                   | Demographic variable - M=Male, F=Female                                                                                             |
| Dependent_count          | Demographic variable - Number of dependents                                                                                         |
| Education_Level          | Demographic variable - Educational Qualification of the account holder (example: high school, college graduate, etc.)               |
| Marital_Status           | Demographic variable - Married, Single, Divorced, Unknown                                                                           |
| Income_Category          | Demographic variable - Annual Income Category of the account holder (< $40K, $40K - 60K, $60K - $80K, $80K-$120K, > $120K, Unknown) |
| Card_Category            | Product Variable - Type of Card (Blue, Silver, Gold, Platinum)                                                                      |
| Months_on_book           | Period of relationship with bank                                                                                                    |
| Total_Relationship_Count | Total no. of products held by the customer                                                                                          |
| Months_Inactive_12_mon   | No. of months inactive in the last 12 months                                                                                        |
| Contacts_Count_12_mon    | No. of Contacts in the last 12 months                                                                                               |
| Credit_Limit             | Credit Limit on the Credit Card                                                                                                     |
| Total_Revolving_Bal      | Total Revolving Balance on the Credit Card                                                                                          |
| Avg_Open_To_Buy          | Open to Buy Credit Line (Average of last 12 months)                                                                                 |
| Total_Amt_Chng_Q4_Q1     | Change in Transaction Amount (Q4 over Q1)                                                                                           |
| Total_Trans_Amt          | Total Transaction Amount (Last 12 months)                                                                                           |
| Total_Trans_Ct           | Total Transaction Count (Last 12 months)                                                                                            |
| Total_Ct_Chng_Q4_Q1      | Change in Transaction Count (Q4 over Q1)<br>B21                                                                                     |
| Avg_Utilization_Ratio    | Average Card Utilization Ratio                                                                                                      |


**Exploratory Data Analysis (EDA)**

- **Datatype of the feature****s** **in Data set**


    CLIENTNUM                     int64
    Attrition_Flag               object
    Customer_Age                  int64
    Gender                       object
    Dependent_count               int64
    Education_Level              object
    Marital_Status               object
    Income_Category              object
    Card_Category                object
    Months_on_book                int64
    Total_Relationship_Count      int64
    Months_Inactive_12_mon        int64
    Contacts_Count_12_mon         int64
    Credit_Limit                float64
    Total_Revolving_Bal           int64
    Avg_Open_To_Buy             float64
    Total_Amt_Chng_Q4_Q1        float64
    Total_Trans_Amt               int64
    Total_Trans_Ct                int64
    Total_Ct_Chng_Q4_Q1         float64
    Avg_Utilization_Ratio       float64

There are 10,127 cases and 21 features in the data set. We do not have nulls but on the other hand we do have 'Unknown' string in `Education_Level`, `Marital_Status` and `Income_Category` features respectively.
We have 14 numerical features (5 - `float64`, 10 - `int64`) and 6 `object`. Since this dataset is relatively small and we do have the features names, we can make some assumptions (that would be verified): for example `Gender`, `Marital_Status`, `Card_Category` `Education_Level` and `Income_Category` are expected to be [nominal categorical features](https://towardsdatascience.com/understanding-feature-engineering-part-2-categorical-data-f54324193e63) 

Before manipulating the data for our classification model, let us 'play' a bit with the data to get grasp of what we have, and will try to get views between our target `Attrition_Flag` and other categorical features, then, We will try to see if there is any dependencies between the categorical features.


- **Correlation plot between all the features**
![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635264893468_download.png)


 
 Drop 'Avg_Open_To_Buy' column as it can be represented by Credit Limit

![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635269680128_file.png)


We can see that there is strong relationship between below:

1. **Months_Inactive_12_mon <--> Attrition_Flag**
2. **Contacts_Count_12_mon <--> Attrition_Flag**
3. Months_on_book <--> Customer_Age
4. Income_Category <--> Gender
5. Credit_Limit <--> Gender
6. Avg_Open_To_Buy <--> Gender
7. Credit_Limit <--> Income_Category
8. Credit_Limit <--> Card_Category
9. Avg_Open_To_Buy <--> Income_Category
10. Avg_Open_To_Buy <--> Card_Category
11. Avg_Open_To_Buy <--> Credit_Limit
12. Avg_Utilization_Ratio <--> Total_Revolving_Bal
13. Total_Trans_ct <--> Total_trans_Amt


**Frequency Distribution of** **Plot Features:** 


![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635269793569_file.png)

## Based On Demographics
- Relation Plots with Target variable


![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635270837467_file.png)
![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635270968520_file.png)


While the figures indeed show some disparity in numbers between churned and existing customers, the distribution of each category is very similar. 

![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635270980371_file.png)
![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635270918357_file.png)


The figures above shows that each category cannot be used alone as a factor to decide customer churn. A married female with higher income and education is a different demographic than a single female with medium income and education. As such, we will need to weigh in all these features to build our model.


## Model Training

Now we train different classifiers and try to obtain the most accurate model. We will utilize:

1. **Random Forest**
2. **Support Vector Machine**


    Records distribution across test and train datasets:
    0.8402535657686212
    0.8402957486136784

We have selected 70% data in as a training dataset and 30% as a testing dataset.

**1.Random Forest**
Here we are trying to see what optimum value of tree depth is suitable which would give us best accuracy by plotting graph of accuracy VS tree depth:


![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635279247190_file.png)


As we can see from the graph above the accuracy saturates after max_depth of **25****.**
So, tree depth of **25** is suitable for Random Forest classifier.


![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635279390647_file.png)




                  precision    recall  f1-score   support
    
               0       0.92      0.76      0.84       432
               1       0.96      0.99      0.97      2273
    
        accuracy                           0.95      2705
       macro avg       0.94      0.88      0.90      2705
    weighted avg       0.95      0.95      0.95      2705

**A****rea** **U****nder Curve plot:**
Here,
Y-Axis is  represents True Positive Rate
X-Axis is represents False Positive Rate

![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635279521948_file.png)



**2.Support Vector Machine**
Without using any sampling techniques, we were not getting correct results and our confusion matrix has zero False positive values


![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635279865292_file.png)
![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635279824943_file.png)

    Accuracy: 0.8402957486136784
    Precision: 0.8402957486136784
    Recall: 1.0
    F1 Score: 0.9132181599035758

 
Although accuracy is ~84% for SVM but from confusion matrix it is evident that attrited count is 9 in both actual and existing.
We see that churned customer takes only 16.1% of the data.
To balance the dataset, we will utilize Oversampling , Under sampling and SMOTE. SMOTE (Synthetic Minority Oversampling Technique) consists of synthesizing elements for the minority class, based on those that already exist.


![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635280205004_file.png)
![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635280215499_file.png)
![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635280225697_file.png)

    UNDERSSAMPLING 
    precision    recall  f1-score   support
    
               0       0.71      0.72      0.71       432
               1       0.71      0.70      0.71       432
    
        accuracy                           0.71       864
       macro avg       0.71      0.71      0.71       864
    weighted avg       0.71      0.71      0.71       864
    =====================================================================
    OVERSAMPLING
         precision    recall  f1-score   support
    
               0       0.74      0.73      0.74      2273
               1       0.74      0.75      0.74      2272
    
        accuracy                           0.74      4545
       macro avg       0.74      0.74      0.74      4545
    weighted avg       0.74      0.74      0.74      4545
    ===================================================================
    SMOTE
        precision    recall  f1-score   support
    
               0       0.75      0.74      0.74      2273
               1       0.74      0.75      0.74      2272
    
        accuracy                           0.74      4545
       macro avg       0.74      0.74      0.74      4545
    weighted avg       0.74      0.74      0.74      4545


**Comparing AUC ROC**


![](https://paper-attachments.dropbox.com/s_CED2FDF00122877205232FA0B486DABFA72934EFDE0EACFD4BD8B1F802985167_1635280596191_file.png)


We can clearly see Area Under Curve for that Random Forest is the greatest and is the reason we will choose random forest as our classifier.
Support Vector Machine has performed well after applying sampling techniques like under sampling, oversampling and SMOTE.


![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1635884706683_image.png)


**False Positive Rate:** 

    FP/FP+TN = 600/600+1673 = 0.2639

**False Negative Rate:**

    FN/FN+TP = 564/564+1708 = 0.2482

**True Positive Rate (Recall):** 

    TP/TP+FN = 1708/1708+564 = 0.7517

**True Negative Rate:**

    TN/TN+FP = 1673/1673+600 = 0.7360


|                                       | **Y =1 (Truly** **churned****)** | **Y=0**                   |
| ------------------------------------- | -------------------------------- | ------------------------- |
| **L=1  (Predicted to** **churn****)** | True positive (TP) = 1708        | False positive (FP) = 600 |
| **L=0**                               | False negative (FN) = 564        | True negative (TN) = 1673 |



**K-Fold with SMOTE data**

Accuracy Obtained : 0.95



## SHAPley Explanation:

Machine learning models SHAPley values importance comparison for Random Forest and Support Vector Machine →

| **Category**                                                                                              | **Random Forest**                                                                                                                     | **Support Vector Machine**                                                                                                            |
| --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| An individual who has **never been inactive** in the last 12 month period (Months_Inactive_12_mon)        | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637072855487_image.png) | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637072945445_image.png) |
| An individual who has been inactive for **6** months in the last 12 month period (Months_Inactive_12_mon) | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637072916004_image.png) | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637073117674_image.png) |
|                                                                                                           |                                                                                                                                       |                                                                                                                                       |
| An individual who has **0** dependents                                                                    | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637071502004_image.png) | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637071031262_image.png) |
| An individual who has **5** dependents                                                                    | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637038812774_image.png) | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637072760062_image.png) |
|                                                                                                           |                                                                                                                                       |                                                                                                                                       |
| An individual who has purchased 1 products from the bank (Total_Relationship_Count)                       | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637074521642_image.png) | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637072973075_image.png) |
| An individual who has purchased **6** products from the bank (Total_Relationship_Count)                   | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637074538974_image.png) | ![](https://paper-attachments.dropbox.com/s_6ACFB95305C4B5FA0C809AD616483D65527B0C4FFE54D72FC3C70960FF32AB2B_1637072957756_image.png) |



