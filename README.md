# Credit_Risk_Analysis
#### 17 Machine Learning Challenge

## Overview of Credit Risk Analysis:

I have been working with Jill to build skills in data preparation, statistical reasoning, and machine learning having to do with credit risk. This is because in 2019, 
more than 19 million Americans had at least one unsecured personal loan.  Personal lending is growing fast, even more than credit card, 
auto, mortgage, and student loans. FinTech firms are looking for better methods than traditional loan processes. I have decided 
to use the latest machine learning techniques, so I can continuously analyze large amounts of data and predict trends to optimize lending having to
so with lower over-all credit card risk.

As good loans easily outnumber risky loans credit risk is an inherently unbalanced classification problem. Therefore, I employed different techniques 
to train and evaluate models with unbalanced classes. I used imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I oversample the data using the RandomOverSampler 
and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, I used a combinatorial approach of over and under sampling 
using the SMOTEENN algorithm. Finally, I compared the two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, 
to predict credit risk. 

## Results of : 

* The first method used was the Naive Randond Oversampling method and this was the results:

The calculation of the balanced accuracy is reflecting the relatively high number of false postives, 
precision showed that the and recall  

![Credit_Risk_Analysis](./cm_1_Naive.png)

* The second method used was the SMOTE Oversampling method to calculate the balanced accuracy, precision and recall  

![Credit_Risk_Analysis](./cm2_SMOTE.png)

* The third method used was the Undersampling method  to calculate the balanced accuracy, precision and recall 

![Credit_Risk_Analysis](./cm3_under.png)

* The forth method used was was the Ensemble Balanced Forest Classifier method  the Combination (Over and Under) Sampling method to calculate the balanced accuracy, precision and recall 
 
![Credit_Risk_Analysis](./cm4_combo.png)

* The fifth method used to calculate the balanced accuracy, precision and recall 

![Credit_Risk_Analysis](./cm5_brf.png)

* The 6th method used was the Easy Ensemble AdaBoost method to calculate the balanced accuracy, precision and recall  

![Credit_Risk_Analysis](./cm6_eec.png)


## Final Results
There should be additional analalys on over fiitting as their was too much data in the 85 column.


