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

  - To statistically calculate the accuracy of this form of data manipulation a confusion matrix and a classification report was produced. This shows a very low precision for predicting high risk applicants, which is what we need the model to exceed at. This indicates naive random oversampling is not the best technique to use for the goals and purposes of that algorithm. Results are as shown below:
  
![Random_oversamp_results](https://user-images.githubusercontent.com/100040705/178183603-760cb963-8f3c-495a-986e-f71dc9ec6adf.png)

- SMOTE Oversampling
  - This was achieved with imblearn's SMOTE library, short for synthetic minority oversampling technique, where the minority class is also increased in size but through new instances being interpolated.
 
 ![SMOTE_numbers](https://user-images.githubusercontent.com/100040705/178183965-2eff0a4f-5537-474b-8886-a4a81bff4c49.png)

  - This again had a low precision for predicting high risk applicants as shown by the results below. This model would therefore not be the best model to choose as it does not accurately accomplish the task at hand, flagging high risk credit applicants.
  
  ![SMOTE_results](https://user-images.githubusercontent.com/100040705/178184054-32c4ac6d-2a9f-4098-aa6a-b4fa4c1a7dc1.png)
