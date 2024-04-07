# deep-learning-challenge

## Overview 
The goal of this machine learning model and neural network development is to create a binary classifier that can predict whether applicants will be successful if funded by AlphabetSoup. The .csv used in this model development and analysis contained data of more than 34,000 organizations that have received funding from AlphabetSoup. 

The columns in the csv are as follows: 
    EIN and NAME — Identification columns
    APPLICATION_TYPE — Alphabet Soup application type
    AFFILIATION — Affiliated sector of industry
    CLASSIFICATION — Government organization classification
    USE_CASE — Use case for funding
    ORGANIZATION — Organization type
    STATUS — Active status
    INCOME_AMT — Income classification
    SPECIAL_CONSIDERATIONS — Special considerations for application
    ASK_AMT — Funding amount requested
    IS_SUCCESSFUL — Was the money used effectively


## Preprocessing the Data
- First we needed to see which columns in the dataframe would actually be beneficial in developing this machine learning model. 
- The identificiation and name columns don't add any value to the machine learning model because it's a unique value for each organization in the data
so those columns were dropped.
- Then I looked at the APPLICATION_TYPE column and the CLASSIFICATION column to determine the value counts for binning occurrences together. 
-Once the cutoff values were determined, this changed the total number of columns in the dataframe

## Splitting and training the preprocessed data
- target variable ['IS_SUCCESSFUL'] column since this is what we want to predict with this model 
- feature variables are all of the other columns that can have an impact on the success of the organization
- For my model, I decided to leave all the other columns as feature variables except the name and identification columns that had already been dropped

## Compiling, Training, and Evaluating my model
- In the first development of the model, I used 80 neurons in the first layer and the input_dim = 43 and the "relu" as the activation function
- I used 30 neurons in the second layer
- When training the model, I used 100 epochs and the loss ended up being 56% and the predictive accuracy was 72.9%

## Optimizing the Model
- Tried three approaches to try to increase the predictive accuracy of the model

- First, in the preprocessing step , I decreased the cutoff value for the APPLICATION_TYPE and CLASSIFICATION column which increased the number of bins. This in turn increased the number of input_dimensions in the first layer increased from 43 to 45
- This increased the model's predictive accuracy to 73.0%

- Second, I increased the number of neurons in the dense layers to 100 and 50 along with the increased number of bins
- This left the model's predictive accuracy at 73.0%

- Third, I increased the number of training epochs from 100 to 150 with the increased number of neurons
- This brought the model's predictive accuracy back to 72.9% 

- Fourth, I decreased the number of training epochs from 100 to 80 and also decreased the number of neurons in the dense layers to 75 in the first layer and 20 in the second layer 
- This left the model's predictive accuracy at 72.9%


## Summary
- Overall, it looks like this model has a 73% predictive accuracy in predicting the success of organizations funded by AlphabetSoup. 
- To improve the model's accuracy, I can use Random Forest modeling as it will create multiple bootstrap samples from the original dataset to improve accuracy by reducing overfitting. 
- I can also review my list of features from the dataset to selectively pick the most informative features that will be more useful in predicting the target variable of the model
