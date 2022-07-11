# Credit_Risk_Analysis

##**Overview**

This analysis was to establish a supervised machine learning model trained and tested on credit risk data through a variety of methods to establish credit risk based on a number of factors. 
It was incredibly important that data be both scaled and portioned to testing and learning portions properly as credit risk analysis has significanly more non-risk applicants than risky applicants. Without this results would be innaccruate for the risky applicants the algorithm would be designed to detect.
The primary libraries used to do so were imbalanced-learn and scikit-learn. 
Through these the data was under, oversampled, or combination sampled as well as being scaled to attempt to tailor the most accurate and precise results.
Classifers were addtionally used to reduce bias in sampling and clustering of data. These machine learning algorithms were designed to predict if potential lenders would be a credit risks, and what factors makes for the most risky lender.


##**Results**

The following are results of all machine learning models tested:

- Naive Random Oversampling
  - This was achieved with imblearn's RandomOverSampler model, to increase the number of high risk applicants studied to train the model by randomly selecting and duplicating the minority class until both are balanced. The balanced number in both classes after resampling can be see below:
![Random_oversamp_numbers](https://user-images.githubusercontent.com/100040705/178183191-60f72895-bd90-4f15-85c3-ff014d72b1a7.png)

  - To statistically calculate the accuracy of this form of data manipulation a confusion matrix and a classification report was produced. This shows a very low precision for predicting high risk applicants, which is what we need the model to exceed at. Recall was also low, meaning the model did not accurately predict all high risk applicants. This indicates naive random oversampling is not the best technique to use for the goals and purposes of that algorithm. Additionally, the accuracy score is .63 meaning only approximately 63% of our data is represented by this model, well below what I would consider acceptable. Results are as shown below:

![Random_oversamp_results](https://user-images.githubusercontent.com/100040705/178184565-bc9ae052-75a2-481f-9f4b-a2349bb3a009.png)

- SMOTE Oversampling
  - This was achieved with imblearn's SMOTE library, short for synthetic minority oversampling technique, where the minority class is also increased in size but through new instances being interpolated.
 
 ![SMOTE_numbers](https://user-images.githubusercontent.com/100040705/178183965-2eff0a4f-5537-474b-8886-a4a81bff4c49.png)

  - This again had a low precision for predicting high risk applicants as shown by the results below. This model would therefore not be the best model to choose as it does not accurately accomplish the task at hand, flagging high risk credit applicants.Recall was also low, meaning the model did not accurately predict all high risk applicants. Additionally, the accuracy score is .66 meaning only approximately 66% of our data is represented by this model, well below what I would consider acceptable.
  
![SMOTE_results](https://user-images.githubusercontent.com/100040705/178184573-8efefd0e-a87e-4f01-b3f8-d8513e60404e.png)

  - Undersampling with ClusterCentroids
    - This was accomplished with imblearn's ClusterCentroids library, which identifies clusters of the majority class and generates synthetic data points in order to downsize the majority class to that of the minority. As shown below the size of both classes were downsized to only 246 rather than increased as seen in the previous examples.
    
![CC_numbers](https://user-images.githubusercontent.com/100040705/178184584-8f672cfd-405f-4c00-9ec7-479c6ec4289f.png)

  - Once again, the precision and recall for correctly detecting and flagging high risk applicants is very low, indicating this is also not the best model to be used for reasons previously stated. Results are as shown below:
  

![CC_results](https://user-images.githubusercontent.com/100040705/178184865-0515a2ea-7f01-4cb6-ba63-d85e1473977c.png)

- Combination (Over and Under) Sampling
  - Combination sampling was achieved with SMOTEEN from iblearn, this combines SMOTE with Edited Nearest Neighbors to oversample the minority and then clean the data through undersampling. The undersampling is achieved by removing oversampled data points that has neightbors belonging to different classes. 

![SMOTEEN_numbers](https://user-images.githubusercontent.com/100040705/178185345-c6dd193f-1e5d-40ec-94a5-0c1e3bae1351.png)

  - This model did not show improvement from the previous with a 0.01 for precision as shown in the classification report for high risk applicants, meaning the model does not accurately predict high risk applicants. Recall was also low, meaning the model did not accurately predict all high risk applicants. Again, this would not be the best model for the purposes of the algorithm. The recall is higher for this model, but not enough in relation to the extremely low precision to balance out in this use case. 

![SMOTEEN_results](https://user-images.githubusercontent.com/100040705/178185348-afc36be1-bc1d-4a09-acbe-06e943761f52.png)

- Balanced Random Forest Classifier
  - This algorithm from sklearn was used to attempt to combine weak learner algorithm decision trees into a combined model that could accurately make predictions for the use case. Here data was scaled and fit to the model, with the number of estimators, or trees that will be created set to 100. This number was chosen to balance precision of the model with run time needed to complete it. 


![BRFM_numbers](https://user-images.githubusercontent.com/100040705/178185991-d6fb345a-64d9-4eaf-9dff-6a4a4b50fcad.png)

  - This model showed improvements over the previous, with only 4 predicted to be low risk, that actually ended up being high risk, making the accuracy for high risk applicants 90% as shown by the classification report below. However, the recall is low for the model, meaning it will not find all possible positives for high risk applicants. As the company would want to find all possible high risk applicants, this model may not be the best for their needs, though it shows improvements over others. The accuracy score was 0.68, meaning 68% of our data was represented in the model, which though also an improvement over some previous models, is not high enough for me to comfortably adopt the algorithm as accurate or usable in a business circumstance.

![BRFM_results](https://user-images.githubusercontent.com/100040705/178186594-b2a40a3e-565f-4cdc-b5a9-1197b7793945.png)

  - For this model, features were ranked by importance as well, giving insights as to what factors affect high risk classification the most. This could be used to reduce the number of features used in models, potentially improving both run time and accuracy. The top of the resulting most important features are as shown below, sorted by most to least importance (full list may be view in credit_risk_ensemble.ipynb):

![BRFM_feat_import](https://user-images.githubusercontent.com/100040705/178186889-648e1562-ab44-408b-a5e6-e2dd69d7d746.png)








