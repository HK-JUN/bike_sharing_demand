# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### junhong PARK

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
When I tried to submit the result of prediction at the first time, I realized Kaggle only accept the positive value for prediction in this project. I investigate my result through DataFrame.describe() to catch is there any negative value. Fortunatelly, in my initial model didn't give any negative value so I just submit my prediction.
Also, I change datetime feature into datetime via pandas.to_datetime() to use it on further feature engineering.

### What was the top ranked model that performed?
Amongh the initial models, WeightedEnsemble_L3 was the best model achieving -52.8069 as score_val. RandomForestMSE_BAG_L2 and ExtraTreesMSE_BAG_L2 were followed with -53.284646 and -53.950967 score_val.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
First of all, I divide datetime feature into year, month, and day. After that I investigated correlation between the features and found out that atemp and temp has 0.984948 correlation with each other so I drop the atemp feature.

### How much better did your model preform after adding additional features and why do you think that is?
After adding additional features, I got 0.42359 on kaggle score which is way better than 1.32363. I think splitting datetime into separte features makes model easier to understand and utilize it.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
I got 0.42249 on kaggle score after hyper parameter tuning. It achieved slightly better than before but it didn't show impressive improvement.
I think I need to dig a little deeper into hyperparameter tuning. 

### If you were given more time with this dataset, where do you think you would spend more time?
If I spent more time on this project, I would like to study more about how to optimizing hyper parameter on each model. In hyper parameter tuning, it didn't show impressive improvement so I would like to 

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default|default|default|1.79989|
|add_features|default|default|default|0.42359|
|hpo|hyperparameter_RF|hyperparameter_XT|hyperparameter_KNN|0.42249|

### Create a line plot showing the top model score for the three (or more) training runs during the project.


![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.


![model_test_score.png](img/model_test_score.png)

## Summary
In this project, I tried to predict bike sharing demand based on given features through EDA and Autogluon TablurPredictor.
In each step, model shows improvement but on hyper parameter tuning, it doesn't show dramatic improvement.
I learned  how to visualize 
