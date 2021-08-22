# Credit_Risk_Analysis
# 17 challenge

## Overview of Credit Risk Analysis:

I have been working with Jill to build skills in data preparation, statistical reasoning, and machine learning having to do with credit risk. This is because in 2019, 
more than 19 million Americans had at least one unsecured personal loan.  Personal lending is growing fast, even more than credit card, 
auto, mortgage, and student loans. FinTech firms are looking for better methods than traditional loan processes. I have decided 
to use the latest machine learning techniques, so I can continuously analyze large amounts of data and predict trends to optimize lending having to
so with lower over-all credit card risk.

As good loans easily outnumber risky loans credit risk is an inherently unbalanced classification problem. Therefore, I employed different techniques 
to train and evaluate models with unbalanced classes. I used imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I oversample the data using the RandomOverSampler 
and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, I used a combinatorial approach of over- and undersampling 
using the SMOTEENN algorithm. Finally, I compared the two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, 
to predict credit risk. 





## Results: Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of 
all six machine learning models. Use screenshots of your outputs to support your results.

* The first method used to calculate the balanced accuracy, precision and recall was the Naive Randond Oversampling method 

![Credit_Risk_Analysis](./cm_1_Naive.png)

* The second method used to calculate the balanced accuracy, precision and recall was the SMOTE Oversampling method 

![Credit_Risk_Analysis](./cm2_SMOTE.png)

* The first method used to calculate the balanced accuracy, precision and recall was the Undersampling method 
![Credit_Risk_Analysis](./cm3_under.png)

* The second method used to calculate the balanced accuracy, precision and recall was the Combination (Over and Under) Sampling method 
![Credit_Risk_Analysis](./cm4_combo.png)

* The second method used to calculate the balanced accuracy, precision and recall was the Ensemble Balanced Forest Classifier method 
![Credit_Risk_Analysis](./cm5_brf.png)

* The second method used to calculate the balanced accuracy, precision and recall was the Easy Ensemble AdaBoost method 
![Credit_Risk_Analysis](./cm6_eec.png)





*******************************************************************
# Amazon Vine Analysis
### 16 AWS, RDS and posgres/pgadmin

## Overview of the analysis:
Amazon has two types of reviews; 

First are those which are 'non-vine' reviews, where people simply take the time to write reviews independantly with
no paid incentive. 
 
Second are written by members of the paid Amazon Vine program. The Amazon Vine program is a 
service that allows manufacturers and publishers to receive reviews for their products. Companies (like SellBy whom we have
been working for during this module) pay a small fee to Amazon and provide products to Amazon Vine members, 
who are then required to publish a review.

We are tasked with identifying if the vine reviews are in anyway biased.

## Results of our Video Game analysis of the reviews: 

- How many total Vine reviews were there for the Video Game listing?

![Amazon_Vine_Analysis](./count_vineY.png)

- How many total non-Vine reviews were there for the Video Game listing?

![Amazon_Vine_Analysis](./count_vineN.png)

- How many Vine reviews were 5 stars that had had percent of helpful votes/total votes > .50? 

![Amazon_Vine_Analysis](./countYgt50.png)

- How many non-Vine reviews were 5 stars that had had percent of helpful votes/total votes > .50? 

![Amazon_Vine_Analysis](./countNgt50.png)

- What percentage of Vine reviews were 5 stars? 
If you take the above count of 94 and then the 48 that were 5 stars as shown below, which gives a total of 51%:

![Amazon_Vine_Analysis](./vine_Y_df5.png)

- What percentage of non-Vine reviews were 5 stars?
if you take the count of 40,471 and then the 15663 shown below that were 5 stars, which gives a total of 39%:

![Amazon_Vine_Analysis](./vine_N_df5.png)


## Vine verses non-Vine reviews Summary: 

The data shows that the vine reviews tend to have a 51% 5 star review as compared to the 39% 5 star review from
the non-Vine reviews. But this analysis included a calculation that took: 

vine_percents_df=vine_total_votes_df.withColumn('percent', col("helpful_votes")/ col("total_votes"))
vine_percents_df=vine_percents_df.filter('percent>=0.5')

Therefore, the above calcs are more complex than what one may expect as it looked at 'helpful votes' and 'total votes'
factor.

When including those factors, the data indicates a 12% higher 5-star review for Vine verses non-Vine reviews which is a 
small but significant increase. More analysis should be performed to understand these differences.

## Additional Analysis that is recommded to better understand the reviews:

1. Analysis should be done on the lower tiered reiviews as well. If there is also the same percentage difference for Vine
verses non-Vine video game players on the lower 1-3 star reviews then the data may not be as biased. 

2. It also would be interesting to look at the 4 star reviews as that is also a very good rating.  Because the numbers 
above were very small when looking at the 5-star Vine reviews (94 and 48), and those folks may be better or more 'educated' 
at playing video games and some of the non-Vine reviewers may not be very good at video games, it may not
illustrate the entire picture very clearly.

3. Additionally, an analysis should be performed on the written reviews. By using the pySpark tools to look at the written reviews it could
reveal some more data as to why or why not the reviews are skewed to 5-stars for the Vine reviewers. This may point to, as mentioned before,
the Vine players may be more experienced at playing video games so may understand them better and thus, enjoy the experience better.





