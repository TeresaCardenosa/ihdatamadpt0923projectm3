
# Diamonds and Machine Learning | Project 3 - Ironhack

This repository is the project of module 3 of the Ironhack Data Analytics Part Time Bootcamp (February 2023).

The goal is to compete through Kaggle for predicting the price of diamonds based on their characteristics. To do this, we will use different machine learning models and practice with different machine learning workflows to obtain the best prediction. 

🚀 Let's go!

## Learnings and conclusions

1. **Machine learning is not for old people (computers)**. If you have a computer from prehistoric times, good luck on your way. You will need several prayers and many, many hours, especially for GridSearchCV. 

2.	**Organisation is key**. If I had had a single notebook it would have been impossible. For me it has been fundamental to differentiate between applied models and to have, above all, a notebook with all the transformations written down to be able to apply them later on diamonds_test. 

3.	**Feature engineering, that great unknown**. At the beginning I was afraid of how the decisions I made about the features could affect the model and I have learned that it is essential because it will depend on what changes you have applied and what model you are using. 

4.	**Scaler, yes but no**. In my case, most of the time there was no great difference in proportionality between the features, so applying the scaler or not did not make a big difference in the metrics.

![](https://github.com/TeresaCardenosa/ihdatamadpt0923projectm3/blob/main/giphy.gif)

## Dataset diamonds, diamonds_test y sample_submission 

First of all, to understand how the Kaggle competition works, we have the 00_data_review notebook. 

## 00_Data_Review

For the competition we use the diamonds dataset, saved in .csv format inside the /data folder. In the notebook we explore what the shape of this dataset is. A brief summary:

40455 rows x 11 columns
 
| Price	| 40455 non-null |	Int64 |
| Carat	| 40455 non-null |	Float64 |
| City	| 40455 non-null |	Object |
| Depth	| 40455 non-null |	Float64 |
| Table	| 40455 non-null |	Float64 |
| X	    | 40455 non-null |	Float64 |
| Y	    | 40455 non-null |	Float64 |
| Z	    | 40455 non-null |	Float64 |
| Cut	| 40455 non-null |	Object |
| Color	| 40455 non-null |	Object |
| Clarity | 40455 non-null | Object |

In the same notebook we also explore what is in diamonds_test: 13485 rows x 11 columns. It follows the same structure as the diamonds dataframe, without the Price column as it is the target. 

Finally, we also explored what a sample_submission to upload to Kaggle should look like: a two-column dataframe ('id', 'price') composed of a total of 13485 records.
## Data Preparation

Before describing the machine learning models, it is important to highlight the corresponding notebooks of 00_Data_Preparation and 00_Data_Featuring. 

## 00_Data_Preparation

In this notebook we perform a more in-depth analysis on the diamonds dataset, answering questions such as: 

- Does it have null values?
- Does it have 0 values? 
- What are the minimum, maximum and other characteristics of each of its numeric variables? 
- Are the numeric variables correlated with Price's target? 
- Can we reduce the dimensionality of categorical variables such as city, cut, colour and clarity?

## OO_Data_Features_Engineering

In the face of all the above answers, a more important question looms: how will the choice of features affect the final model? For this, I generated the notebook 00_Data_Features_Engineering. 

In it, I generate up to 09 different options for feature combinatorics: 

- Decision on whether or not to eliminate the Depth column that did not contribute anything about Price. 
- Decision on whether one hot encoding or label enconding. 
- Reducing or not the dimensionality of categorical variables. 
- Generate a new size column as a multiplication of the x, y, z columns. 
- Eliminate values of 0 or replace them with the corresponding mean. 
After deciding what to apply to each new dataframe, I make a copy of diamonds and save it in a new .csv inside the /data folder, simply modifying the corresponding number in the name. For example: diamonds_2 or diamonds_7.


## Application of models!

The rest of the notebook corresponds to the applications on the 09 dataframe of diamonds generated from different regression models in machine learning. The following models have been applied: 

1. Linear Regression (notebook 01_ML_Basic_LinearRegression) 
2. Random Forest Regressor (notebook 02_ML_RandomForestRegressor) 
3. Bagging Regressor (notebook 03_ML_BaggingRegressor) 
4. XGBoost (notebook 04_ML_XGBoost) 
5. Decision Tree Regressor (notebook 05_ML_DecisionTreeRegressor) 
6. Extra Trees Regressor (notebook 06_ML_ExtraTreesRegressor)
7. Gradient Boosting Regressor (notebook 06_ML_GradientBoostingRegressor) 

## How are notebooks with models structured? 

1. We generate 09 dataframe with the various .csv files in data.
2. We perform 09 train, test, Split. 
3.	We train the model with the 09 possibilities. 
4.	We compare the 09 RMSE metrics and note which dataframe has performed best and its metric. 
5.	In some cases, we continue with the RobustScaler or StandarScaler. We repeat the process and note which dataframe has performed best and its metric. 
6.	We note this conclusion at the top of the notebook as the winner and the RSME.
7.	On some occasions, we will try running GridSearchCV to get the best metrics.  
8.	If we decide to generate a new submission, we apply everything to the .csv of diamonds_test, save the new .csv inside the submission folder and note, after uploading it to Kaggle, the platform score.

![](https://github.com/TeresaCardenosa/ihdatamadpt0923projectm3/blob/main/ejemplo.JPG)

