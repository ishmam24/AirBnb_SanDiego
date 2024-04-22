# Predicting AirBnb Prices in San Diego using Machine Learning
This repository contains the data pre-processing pipeline of the AIrBnb listings on San Diego. We use multiple Machine Learning algorithms to analyze the data and draw conclusions from our findings. 

## Background on Project:

AirBnb has gained popularity over the past decade and the vacation-rental company has allowed both guests and hosts to interact seemlessly and provide an excellant opportunity for vacation-goers to break out of staying in traditional hotels and get a more urban experience during their holidays. It has also allowed hosts to utilize their wonderful homes - with the typical US host earning over $14,000 USD a year. AirBnb has become the leader in the vacation rental industries and is now facing stern competitions from their competitors from travel websites such as hotels.com and Expedia. 

We identified a problem that AirBnb hosts face when deciding what price to set for their homes. These values are dependent on a variety of parameters: weekday, weekend, public holiday, increased demand due to special occasions etc. In this project, we take a look at the AirBnb housing prices of San Diego and provide actionable insights for hosts on pricing their listings

<img width="851" alt="image" src="https://github.com/ishmam24/AirBnb_SanDiego/assets/33576600/8955f7f6-b894-434a-8060-784a7e4551d8">

Our fundamental approach centered around preprocessing the data and finding the relevant instances to base our model on. Next, we explored the processed data against the following Machine Learning models:
- Linear Regression
- Neural Networks
- XGBoost
- Random Forest
- Support Vector Regression (SVR)

## Pre-processing the Data:

As with any machine learning project, the fundamental aspect of the project involves Data Collection and cleaning. We sourced our data from Data.world and included approximately 13k listings from August 2019. Each listing had 74 features which included price, bedrooms, bathrooms, location etc. In cleaning the data, we first dropped NLP columns such as Description, Summary, notes and listing URL. Next we dropped host details columns such as Host Name, Host About, Host Id etc. Additionally, we also dropped all location columns (such as city, state and zip code) except latitude and longitude. 

We also had data entries that had missing values. We addressed that by inputting missing values based using relevant approaches (Boolean values of missing data were inputed as False, Missing values in numerical columns were inputed using a KNN imputer - mainly on listing data). Missing Data in categorical columns was kept as a category that was then one-hot encoded.

The source data also had few outliers that were skewing the representation of the dataset. We dropped the following types of listings:
- Homes that were never booked (number_of_stays=0)
- Nightly price equal to price per stay and over 3000
- Applied winsorization - capping values at the 95th percentile to ensure robustness in data analysis.

Finally, we applied Normalization to the data to bring all features to a similar scale. This is crucial when features have different units or scales. Without normalization, features with larger scales can dominate and bias the learning algorithm towards them.

## Model Training
We trained each respective model and compared its Root Mean Squared Error between the training and test datasets. The results were quite similar - with each model's data being within 10% variance. 
****<img width="634" alt="image" src="https://github.com/ishmam24/AirBnb_SanDiego/assets/33576600/c2c29e93-a53e-4867-acb0-8caec2a87458">

<img width="786" alt="image" src="https://github.com/ishmam24/AirBnb_SanDiego/assets/33576600/ad4746de-d2d0-4d8f-a529-a349f4e1e6b2">

## Results
We learned very quickly that the data is primary and the model is secondary. A vast majority of our effor was centered around discussion on how to best process the relevant data, how to deal with outliers and how to drop irrelevant features. Data cleaning and Model training is an iterative process and we believe we can improve the results of our data by going back to the data processing and find ways to improve our data pre-processing pipeline. 

Additionally, we can include multiple cities in our data set. Currently, we only focused on a relatively small sample size from August 2019 for San Diego. Our next goal is to introduce data from other months in 2019 and draw up our models to improve our predictions of AirBnB home prices for San Diego in 2019. 

