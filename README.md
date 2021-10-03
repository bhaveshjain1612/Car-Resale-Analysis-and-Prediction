# Car Resale Analysis and Prediction
<!--
Dashboard Link
  https://dataplatform.cloud.ibm.com/dashboards/7951e9c0-c358-4277-936f-3cae45ae4ec4/view/7234aa393e833ef770e7c4e407992c0674642359e7bb865287d37b490b657797f36f47c5c87d4f5fd8470732a5e4430a9f
-->
## Contents
 1. [Overview](#overview) 
 2. [Problem Introduction](#problem-introduction) 
 3. [Methodology](#methodology) 
 4. [Data Collection and Cleaning](#data-collection-and-cleaning)
 5. [Data Analysis](#data-analysis) 
 6. [Data Visualisation](#data-visualisation) 
 7. [Dashbaording](#dashboarding) 
 8. [Predictive Modelling](#predictive-modelling) 
 9. [Result](#result)
 10. [References](#references)
 
## Overview
The Project revolves around working with unclean data of automobile resale in India to draw meaningful insights and create a resale value predictor.<br>
The domains worked with over here are :- <br> 
 - **Data Wrangling** to clean the raw data.
 - **Data Analysis** to draw insights from the cleaned data.
 - **Machine Learning** to create the prediction model.
 
## Problem Introduction
### What?
>The problem is to create a prediction model and analysis dashboard.<br>
### Who? 
>The primary target auadience are the second and third hand car dealers working individually or are new entrants in the market.<br>
### Why?
>The new entrants and smaller dealers often do not have access to market data or high end mechanics. I aim to simplify their decision making on what car to buy for resale and waht price by looking at the market composition and predicted price.

## Methodology
<details>
<summary>Step 1 - Data Cleaning</summary>
The Unclean raw data is cleaned and exported as new sheet to be used later<br>
The notebook used for the same - <a href='https://github.com/bhaveshjain1612/Car-Resale-Analysis-and-Prediction/blob/main/Data%20Collection.ipynb'>Data Collection Notebook</a>
</details>
<details>
<summary>Step 2 - Data Analysis</summary>
Looking at the composition of the data nd various statistical measure for the same.<br>
The notebook used for the same - <a href='https://github.com/bhaveshjain1612/Car-Resale-Analysis-and-Prediction/blob/main/Data%20Analytics.ipynb'>Data Analytics Notebook</a>
</details>
<details>
<summary>Step 3 - Data Visualisation</summary>
Finding patterns and relationships between various variables using plots and charts<br>
</details>
<details>
<summary>Step 4 - Dashboarding</summary>
Creation of an interactive dashboard using IBM cognos to provide insights and visualisations on the go.<br>
Link to the Dashboard - <a href='https://dataplatform.cloud.ibm.com/dashboards/7951e9c0-c358-4277-936f-3cae45ae4ec4/view/7234aa393e833ef770e7c4e407992c0674642359e7bb865287d37b490b657797f36f47c5c87d4f5fd8470732a5e4430a9f'>Dashboard</a>
</details>
<details>
<summary>Step 5 - Predictive Modelling</summary>
Using machine learning to create a resale price prediction model<br>
</details>

## Data Collection and Cleaning
**Notebook Link** - <a href='https://github.com/bhaveshjain1612/Car-Resale-Analysis-and-Prediction/blob/main/Data%20Collection.ipynb'>Data Collection Notebook</a><br>
### Collection
**Dataset Link** - <a href='https://www.kaggle.com/saisaathvik/used-cars-dataset-from-cardekhocom?select=Cardekho_Extract.csv'>Car Resale Prices</a><br>
The data was taken from Kaggle as a ```.csv``` which was imported to the _IBM Watson Studio Project_.<br>
The file selected is _Caradekho__Extract.csv_.
### Cleaning
The data was in a rather unclean staet with lots unwanted features and null values.<br>
First the percentage of null values was seen for each feature.<br>
The _new-price_ column was 50% missing so i went ahead and dropped it completely. For the rest of the null values, simply tjose observations were droppped.
Given below is a feature wise process of waht was done to clean the data:- <br>
#### Source. Name
> This column is basically the source from where this data was taken thus making it irrelevant to our final outcome. This column was dropped
#### web-scraper-order
> This column is basically the order in which the scraper scraped web data thus making it irrelevant to our final outcome. This column was dropped
#### web-scraper-start-url
> This column is basically the start url from where the scraper scraped web data thus making it irrelevant to our final outcome. This column was dropped
#### full_name
> This column contains the full name of the car. To help us in the future for visualisation and prediction, the full name was converted to uppercase and split into 3 columns, _maker_ , _model_ and _variant_.<br>
_maker_ column is the name of car maker.<br>
_model_ column contains the car model.<br>
_variant_ column contains the car variant.<br>
This was done ```.str.upper()``` (upper casing) and ```.str.split(" ", n = 2, expand = True)``` (string splitting)<br>
The cars with no variant were given the model as variant parameter.
