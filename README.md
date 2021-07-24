# Final_Project_10_UTA

# Project Overview

The aim of the project is to predict how seasonal changes and quarterly fiscal earnings affect the price of Apple Stock Market.

Multiple variables, such as date in months, years and different seasons of the year  will be analyzed to gauge their impact and predict potential price outcomes.

# Description of the communication protocols

X: Gabriel 
–Decide the technologies to be used for each step of the project & Create Dashboard
Circle: Remi 
– Database Integration
Square: Ope
– GitHub Repository & Presentation
Triangle: Iry
– Machine Learning Model

# Content

### Selected Topic
As it relates to human behavior, how do seasons and fiscal quarters compare in stock behavior, using AAPL stock?

### Why this topic?
This topic was chosen to demonstrate that all things are connected, from all things environmental, as it relates to human behavior, transferred into the stock market where humans often make decisions based on science, but even more so on emotions and gut feelings. This model is set to demonstrate this as we observe stock behavior of Apple, Inc.

### Data Source
The data utilized is from Kaggle.com, titled the “NYSE”.

Link: https://www.kaggle.com/varpit94/apple-stock-data-updated-till-22jun2021


### Questions we hope to answer
Do seasons, as in changes in the weather, trigger human behavior enough to show a trend in stock price highs?
Do fiscal quarters trigger a trend of stress in humans that affect human behavior and is reflected within the stock markets highs (or volume purchases?)
Do different months of the year trigger 

### Description of communication protocol
X: Gabriel 
–Decide the technologies to be used for each step of the project & Create Dashboard
Circle: Remi 
– Database Integration
Square: Ope
– GitHub Repository & Presentation
Triangle: Iry
– Machine Learning Model

# Dataset Overview

## Data Source

This dataset provides historical data of APPLE INC. stock (AAPL). The data is available at a daily level. Currency is USD.

The weblink: https://www.kaggle.com/varpit94/apple-stock-data-updated-till-22jun2021

This dataset contains:
Data 
High: Price from the first transaction of a trading day
Low:Minimum price in a  trading day
Close: Price from the last transcation of a trading day
Adj Close: Closing price adjusted to reflect the value after accounting for any corporate actions
Volume: Number of units traded in a day

## Data Quality
In the Kaggle webpage, this dataset is rated with a score of 10.0 for Data Usability.


#  Segment I

## Overview

As mentioned, we are using Apple, Inc's data set that consists of daily stock prices from 1980 - 2020. This data set is being analyzed by changes in open, close, high, and low prices on a daily base. Each of these changes are to be analyzed in their own separate databases where they will be analyzed against seasons and quarters. The following information will explain our plan from raw data to machine learning model in effort to predict what seasons and quarters produce the most gains and losses of a stock. The following will be covered in this section:

- Database Mockup
- Machine Learning Mockup

## Machine Learning

In this section, we will be answering the following questions:
1. Which model did you choose and why?
2. How are you training your model?
3. What is the model's accuracy?
4. How does this model work?

- Which model did you choose and why?
We have chosen the Random Forest Model. It contains a “Rank the Importance of Features” that allows us to see which features have the most impact on the decision. This is part of Ensemble Learning.
Other reasons for choosing random forest algorithms include:
    - Are robust against overfitting 
    - Can be used to rank the importance of input variables in a natural way, which will be very important to our end result of identifying what is the greatest factor of identifying major influencers of stock rises and falls
    - Can handle thousands of input variables without variable deletion
    - Are robust to outliers and nonlinear data

- How are you training your model?
    Features: the variables used to make a prediction.
        - Our features are seasons and fiscal quarters.

    Target: the predicted outcome
        - Our target is the stock price based on Gains/Losses (based on high, low, open, and close – all in separate models from each other)
        
The photo below represents the four separate databases that we will run through the Random Forest Model individually:

!()Photo here of all ML files on the drive

Throughout the remaining explanation of the machine model, we will be referring to the results of running our model with the AAPL_Mock_ML_Open.csv file. This same process will be applied with each of the database files separately. 

In regard to the features, there are separate columns identifying the seasons and identifying the different quarters based on the stock pricing dates. 
!()Photo here showing Open.csv database in dataframe



We then used get_dummies to perform binary encoding on both columns, removing the Gain/Loss_"" column to, instead, be utilized as the target. 
!()Photo here showing binary encoding applied
!()Photo here showing drop of Gain/Loss_Open and defining the target set

Following these methods, we proceed through training as follows:
- Splitting data into Train and Test sets
- Creating a StandardScaler instance
- Scaling the data
- Creating a random forest classifier
- Fitting the model
- Making predictions using the testing data
- Calculating the confusion matrix, whcih provided te following:
    !()Snapshot here of the resulting confusion matrix



- What is the model's accuracy?
    Currently, our model's accuracy is: 0.91, or 91%

- How does this model work?
One of the main reasons this model was selected was because of the feature importance capability. This model was able to 