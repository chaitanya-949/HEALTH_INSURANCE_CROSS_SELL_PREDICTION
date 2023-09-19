# HEALTH_INSURANCE_CROSS_SELL_PREDICTION
# Project Type - EDA/Classification
# problem statement
Our client is an Insurance company that has provided Health Insurance to its customers now they need your help in building a model to predict whether the policyholders (customers) from past year will also be interested in Vehicle Insurance provided by the company.

An insurance policy is an arrangement by which a company undertakes to provide a guarantee of compensation for specified loss, damage, illness, or death in return for the payment of a specified premium. A premium is a sum of money that the customer needs to pay regularly to an insurance company for this guarantee.

For example, you may pay a premium of Rs. 5000 each year for a health insurance cover of Rs. 200,000/- so that if, God forbid, you fall ill and need to be hospitalised in that year, the insurance provider company will bear the cost of hospitalisation etc. for upto Rs. 200,000. Now if you are wondering how can company bear such high hospitalisation cost when it charges a premium of only Rs. 5000/-, that is where the concept of probabilities comes in picture. For example, like you, there may be 100 customers who would be paying a premium of Rs. 5000 every year, but only a few of them (say 2-3) would get hospitalised that year and not everyone. This way everyone shares the risk of everyone else.

Just like medical insurance, there is vehicle insurance where every year customer needs to pay a premium of certain amount to insurance provider company so that in case of unfortunate accident by the vehicle, the insurance provider company will provide a compensation (called ‘sum assured’) to the customer.

Building a model to predict whether a customer would be interested in Vehicle Insurance is extremely helpful for the company because it can then accordingly plan its communication strategy to reach out to those customers and optimise its business model and revenue.

Now, in order to predict, whether the customer would be interested in Vehicle insurance, you have information about demographics (gender, age, region code type), Vehicles (Vehicle Age, Damage), Policy (Premium, sourcing channel) etc.


id : Unique ID for the customer

Gender : Gender of the customer

Age : Age of the customer

Driving_License 0 : Customer does not have DL, 1 : Customer already has DL

Region_Code : Unique code for the region of the customer

Previously_Insured : 1 : Customer already has Vehicle Insurance, 0 : Customer doesn't have Vehicle Insurance

Vehicle_Age : Age of the Vehicle

Vehicle_Damage :1 : Customer got his/her vehicle damaged in the past. 0 : Customer didn't get his/her vehicle damaged in the past.

Annual_Premium : The amount customer needs to pay as premium in the year

PolicySalesChannel : Anonymized Code for the channel of outreaching to the customer ie. Different Agents, Over Mail, Over Phone, In Person, etc.

Vintage : Number of Days, Customer has been associated with the company

Response : 1 : Customer is interested, 0 : Customer is not interested


# Feature Engineering & Data Pre-processing
- In this dataset, there exist 380840 rows and 11 columns after removing 269 duplicate values. there are no null values present in dataset
- for the categorical columns .i have directly mapped with numeric values
- The data is imbalanced so i used smote technique to balance

# machine learning model implementation
# Model: Logistic Regression
Confusion Matrix:
 [[40711 26035]
 [ 3929 62987]]
ROC AUC Score: 0.7756118839986358
Accuracy Score: 0.7758225972976612
              precision    recall  f1-score   support

           0       0.91      0.61      0.73     66746
           1       0.71      0.94      0.81     66916

    accuracy                           0.78    133662
   macro avg       0.81      0.78      0.77    133662
weighted avg       0.81      0.78      0.77    133662

# Model: Decision Tree
Confusion Matrix:
 [[57082  9664]
 [  770 66146]]
ROC AUC Score: 0.9218526667056626
Accuracy Score: 0.9219374242492256
              precision    recall  f1-score   support

           0       0.99      0.86      0.92     66746
           1       0.87      0.99      0.93     66916

    accuracy                           0.92    133662
   macro avg       0.93      0.92      0.92    133662
weighted avg       0.93      0.92      0.92    133662

# Model: XGB
Confusion Matrix:
 [[44867 21879]
 [ 4064 62852]]
ROC AUC Score: 0.805736108426334
Accuracy Score: 0.8059059418533315
              precision    recall  f1-score   support

           0       0.92      0.67      0.78     66746
           1       0.74      0.94      0.83     66916

    accuracy                           0.81    133662
   macro avg       0.83      0.81      0.80    133662
weighted avg       0.83      0.81      0.80    133662

# Model: KNN
Confusion Matrix:
 [[45370 21376]
 [ 3139 63777]]
ROC AUC Score: 0.816415774914623
Accuracy Score: 0.8165896066196825
              precision    recall  f1-score   support

           0       0.94      0.68      0.79     66746
           1       0.75      0.95      0.84     66916

    accuracy                           0.82    133662
   macro avg       0.84      0.82      0.81    133662
weighted avg       0.84      0.82      0.81    133662


# conclusion
Customers of age between 30 to 60 are more likely to buy insurance.

Customers with Driving License have higher chance of buying Insurance.

Customers with Vehicle_Damage are likely to buy insurance.

The variable such as Previously_insured,Annual_premium are more effecting the target variable.

By comparing accuracy Decision Tree classifier gave 92% accuracy.
