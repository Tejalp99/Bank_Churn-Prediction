# BANK CHURN PREDICTION

## BACKGROUND AND CONTEXT 

Businesses like banks that provide several services have to keep frequent check on a major problem of churn rate or rate of attrition.
Now what does the term CHURN RATE denote: it is the rate at which customers stop doing business with an entity. It is most commonly expressed as the percentage of service subscribers who discontinue their subscriptions within a given time period.
In other words it is important for banks to evaluate what kind of services influence a customer's choice to take up a particular service.
Companies from this sector usually have service branches that try to win over their lost customers, as it is always better to recover lost customers rather than spending resources on new recruited clients.


## AIM OF THE PROJECT:
1. To identify and visualize what factors affect/contribute to the customer churn.
2. To build a predictive model that performs
    a) Classification of the customer that are participating in the churn or not.
    b) Then building a machine learning model which is attach to the probability to the churn further helping to classify and        target that can prevent churn.

## CHURN ANALYSIS FRAMEWORK:
STEP 1: THE DATA (Loading data and Data Manupilating)

        What data should be considered when developing a churn model? 

        a. Demographic information about the client. Eg. country
        
        b. Subscription related information. Eg. active member
        
        c. Payment information. Eg. credit score, balance
        
        d. Product usage information. Eg. number of products or number of interaction 
           with the product
           
        e. Other customer information such as age, gender, salary

        
    What modification can be made in the dataset to make it easier to read?
    
    a. check for missing data
    
    b. deleting or neglecting redundant data

STEP 2: EXPLORATORY DATA ANALYSIS: example

    a. Pie chart depicting the proportion of customers retained and lost
    
    b. Checking for customers having credit score above 580
    
    c. Ploting bar charting to visualize how different features affect churn (0/1)
    
    d. Measuring correlation by plotting heatmap
    
       if value is 1: +ve correlation
       if value is 0: no correlation
       if value is -1: -ve correlation
       
    e. Inspecting for outliers: Outliers are values at the extremen ends of the dataset. 
    
       It can affect the accuracy, validity, and reliability of the data.
       
       Eg. In a regression model, outliers can result in a significant deviation from the 
       true line of best fit, leading to inaccurate predictions. and in most practical           cases an outlier decreases the value of a correlation coefficient and weakens the         regression relationship.

STEP 3: NORMALIZING AND STANDARDIZING DATA

    a. Feature scaling is a data preprocessing technique used to transform the values of         features or variables in a dataset to a similar scale. ML algorithms like linear 
       regression, logistic regression, neural network, PCA, etc that use gradient 
       descent as an optimization require data to be scaled.
    b. Normalization is a data preprocessing technique used to adjust the values of 
       features in a dataset to a common scale.
    c. Standardization is another scaling method where the values are centered around 
       the mean with a unit standard deviation.

STEP 4: Train-testy Split:

    Train-test Split is a technique used to evaluate the performance of a machine 
    learning algorithm 
    a. Train dataset: Used to fit the machine learning model
    b. Test dataset: Used to evaluate the fit machine learning model

STEP 5: MODEL SELECTION AND EVALUATION: 

    a. K-Nearest Neighbor (KNN): The KNN algorithm assumes that similar things exist in         close proximity. In other words, similar things are near to each other 
       Essentially, this is calculated by the distance between two points. The straight- 
       line distance (also called the Euclidean distance). KNN model is good at 
       predicting non-churned customers, as demonstrated by the high precision, recall 
       and f1 scores.
       
    b. Logistic Regression: Logistic Regression is used when the dependent 
       variable(target) is categorical. Example: to predict whether customer is churn or 
       not (0/1). It helps to remove highly correlated inputs. And we should consider 
       removing outliers in the training set because LR ill not give significant weight 
       during calculation

    c. Boosting: 
        1. Adaptive Boosting Algorithms: weights are reassigned to each instance, with              higher weights assigned to incorrectly classified instances.
        2. Gradient Boosting: each predictor tries to improve on its predecessor by 
           reducing the errors. But the idea behind Gradient Boosting is that instead of 
           fitting a predictor on the data at each iteration, it actually fits a new 
           predictor to the residual errors made by the previous predictor.

    d. Random Forest model (RF): Random forest is an ensemble technique that works on 
       decision trees. It uses the bootstrap aggregation (bagging) technique over 
       multiple decision trees. As the name bootstrap suggests, the decision tree is 
       trained on several data sets drawn from the original data set, with replacement 
       (reusing the same data samples multiple times). Multiple such decision trees are 
       trained, and the final outcome is based on the average of outcomes of individual 
       trees. 

STEP 6. ROC ( Receiver Operating Characteristics Curve) and AUC ( Receiver Operating 
        Characteristics Curve):
        ROC is a probability curve It is a probability curve that plots the TPR against          FPR at various threshold values and essentially separates the ‘signal’ from the 
       ‘noise’.

       AUC represents the degree or measure of separability. It tells how much the model 
       is capable of distinguishing between classes. Higher the AUC, the better the 
       model is at predicting 0 classes as 0 and 1 classes as 1. 


STEP 7. Hyperparameter Tuning:
        In machine learning, we need to differentiate between parameters and         
        hyperparameters. A learning algorithm learns or estimates model parameters for 
        the given data set, then continues updating these values as it continues to 
        learn. After learning is complete, these parameters become part of the model

        Hyperparameters, on the other hand, are specific to the algorithm itself, so we 
        can’t calculate their values from the data. We use hyperparameters to calculate 
        the model parameters. Different hyperparameter values produce different model 
        parameter values for a given data set.
    
## CLASSIFICATION ALGORITHM:
Classification algorithm uses labeled input data because it is a supervised learning technique and compromises input and output information. 

Therefore, classification is a type of pattern recognition in which classification algorithms are performed on training data to discover the same pattern in new datasets.

## FOUR TYPES OF CLASSIFICATION TASKS IN ML:
1. Binary Classification
2. Multi-class Classification
3. Multi-label Classification
4. Imbalanced Classification

The dataset used for this project, uses Binary Classification i.e. Churn forecast (churn or not)
churn == 1
notchurn == 0

## MODELS USED FOR THIS DATASET:
1. K-Nearest Neighbor (KNN)
2. Logistic Regression (LR)
3. AdaBoost
4. Gradient Boosting (GB)
5. RandomForest (RF)

Result: 
        

        
<img width="270" alt="Screenshot 2023-08-12 at 11 28 08 AM" src="https://github.com/Tejalp99/Bank_churn/assets/115590863/a1730dcd-5829-4b0a-8122-c9a8e6264b9b">



<img width="787" alt="Screenshot 2023-08-13 at 2 44 17 PM" src="https://github.com/Tejalp99/Bank_churn/assets/115590863/8ae2e527-5387-4a28-8dbe-eee72cb24ed8">


Based on the mean value and the standard deviation value, we can conclude that our ROC-AUC score does not deviate much, so we are not suffering from the overfitting issue.

Predicting Churn probability

'LOW' probability means low likelihood of churn

1. Using Random Forest Model:   
<img width="654" alt="Screenshot 2023-08-14 at 4 06 19 PM" src="https://github.com/Tejalp99/Bank_churn/assets/115590863/4bd62f9f-f581-4151-952c-56464c81f3e3">

2. Using Logistic Regression Model:
<img width="655" alt="Screenshot 2023-08-14 at 4 07 50 PM" src="https://github.com/Tejalp99/Bank_churn/assets/115590863/6164fe5f-e921-4dc5-a88c-b7b714608dae">

3. Using K-Nearest Neighbor Model:
<img width="616" alt="Screenshot 2023-08-14 at 4 08 49 PM" src="https://github.com/Tejalp99/Bank_churn/assets/115590863/26595fac-248a-4660-ae6b-1ca66af2d555">

4. Using Gradient Boosting Classifier:
<img width="621" alt="Screenshot 2023-08-14 at 4 10 06 PM" src="https://github.com/Tejalp99/Bank_churn/assets/115590863/60f15b5a-2aeb-4f43-8533-5e34453ea1ee">

5. Using Adaptive Boosting Model:
<img width="593" alt="Screenshot 2023-08-14 at 4 11 55 PM" src="https://github.com/Tejalp99/Bank_churn/assets/115590863/c326569a-8271-42f4-a8e9-f8ce3d300f2e">

6. Shap values (SHapley Additive exPlanations) is a game theoretic approach to explain the output of any machine learning model. In below plot we can see that why a particual customer's churning probability is less than baseline value and which features are causing them.
<img width="1010" alt="Screenshot 2023-08-14 at 4 24 46 PM" src="https://github.com/Tejalp99/Bank_churn/assets/115590863/dd768580-ade2-4728-8bbe-f5f6ebdd3341">




   


