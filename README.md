# Predicting AirBnb Prices in San Diego using Machine Learning
This repository encompasses the data preprocessing pipeline for analyzing Airbnb listings in San Diego. Leveraging various machine learning algorithms, we aim to derive insights and facilitate informed pricing decisions for hosts.

## Background on Project:

Over the past decade, Airbnb has revolutionized the vacation rental industry, providing both guests and hosts with a seamless platform for accommodation. This has offered vacation-goers a chance to embrace urban living during their holidays and enabled hosts to monetize their properties, with the average US host earning over $14,000 USD annually. While Airbnb continues to lead the vacation rental market, it faces increasing competition from travel websites such as hotels.com and Expedia.

Identifying a common challenge faced by Airbnb hosts in determining optimal pricing for their properties, we focus on analyzing Airbnb housing prices in San Diego. Our goal is to provide actionable insights to hosts for effectively pricing their listings.

<img width="851" alt="image" src="https://github.com/ishmam24/AirBnb_SanDiego/assets/33576600/8955f7f6-b894-434a-8060-784a7e4551d8">

Our approach involves preprocessing the data and selecting relevant instances to build our model. Subsequently, we explore the processed data using various machine learning models, including:
- Linear Regression
- Neural Networks
- XGBoost
- Random Forest
- Support Vector Regression (SVR)

## Data Preprocessing:

As with any machine learning project, data collection and cleaning are fundamental. We obtained our data from Data.world, comprising approximately 13k listings from August 2019. Each listing included 74 features such as price, bedrooms, bathrooms, and location.

In the data cleaning phase, we initially removed non-essential columns such as NLP-related columns (Description, Summary, notes, listing URL) and host details columns (Host Name, Host About, Host Id). Additionally, we dropped redundant location columns, retaining only latitude and longitude.

Addressing missing values, we employed appropriate techniques: boolean values of missing data were set to False, missing values in numerical columns were imputed using a KNN imputer, and missing data in categorical columns were kept as a separate category and one-hot encoded.

To handle outliers, we excluded listings meeting specific criteria, such as homes with zero bookings, nightly prices exceeding 3000, and applied winsorization by capping values at the 95th percentile.

Finally, we normalized the data to ensure all features were on a similar scale, essential for unbiased learning algorithms.

## Model Training
We trained each model and evaluated their performance by comparing Root Mean Squared Error (RMSE) between training and test datasets. The results demonstrated consistent performance across models with variances within 10%.

<img width="634" alt="image" src="https://github.com/ishmam24/AirBnb_SanDiego/assets/33576600/c2c29e93-a53e-4867-acb0-8caec2a87458">

<img width="786" alt="image" src="https://github.com/ishmam24/AirBnb_SanDiego/assets/33576600/ad4746de-d2d0-4d8f-a529-a349f4e1e6b2">

## Results
Our project underscored the significance of data preprocessing in model performance. We observed that a substantial portion of our efforts revolved around optimizing data processing, handling outliers, and selecting relevant features. Recognizing data cleaning and model training as iterative processes, we aim to refine our data preprocessing pipeline to enhance model predictions further.

Moving forward, we intend to expand our dataset to include multiple cities beyond San Diego and encompass data from various months in 2019. This expansion will enable us to refine our models and improve predictions of Airbnb home prices for San Diego in 2019.

