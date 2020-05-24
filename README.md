# AlphabetSoupChallenge

## Background 
The challenge is to import, analyze, clean, and pre-process a dataset, then design and train a binary classification model to make a prediction of whether the applicant for funding will be sucessful if funded.  

## 1) Pre-processing the data
- I decided to drop the EIN column and use Name as the identifier
- Name and Classification Data were binned to reduce noise
- All categorical values were encoded 

## 2) Choosing the model 
As the objective was to predict if the organization will be successful, target y is "IS_SUCCESSFUL" column. 

After splitting and scaling the dataset, the training dataset has 80 columns and over 25000 rows, so my first model had two layers to handle the larger amount of data, with a smaller number of nodes (10 and 8 respectively). 

Even though the first model already achieved an accuracy of 75.27% accuracy, I tried to see if the performance can be further optimzed.  

## 3) Optimizing the model

The table below showed the accuracy with each optimization attempt

|Optimization| HOW|Accuracy Score|
|------------|------|------------|
|Original|---|75.27|
|Optimization 1| Binning "ASK_AMT"|75.48|
|Optimization 2|Increase neurons in 1st layer to 20|75.66|
|Optimization 3|Increase neurons in 2nd layer to 12|75.13|
|Optimization 4|Change activation to Leaky Relu|75.19|

The best optimized performance was binning the Ask_Amt with increased neurons in the first layer.  

## Alternative Model

As an alternative, I would use Random Forest Classifier.  The original dataset was already in a tabular format, and is large enough to handle data being split into subset data for training.  It is able to train and predict such a large data set in a more efficient manner.  

In comparision, I also implemented the Random Forest Classifier on the same set of pre-processed data.  The accuracy score is 75.37%, so it is over 75% target prediction, and only marginally lower than the best performing optimized neural network model (75.66%), and yet much more efficient.  


