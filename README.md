# Bike Sharing
A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.


A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 


In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.


They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

- Which variables are significant in predicting the demand for shared bikes.
- How well those variables describe the bike demands


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors. 


**Business Goal:**

You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 


**Data Preparation:**

You can observe in the dataset that some of the variables like 'weathersit' and 'season' have values as 1, 2, 3, 4 which have specific labels associated with them (as can be seen in the data dictionary). These numeric values associated with the labels may indicate that there is some order to them - which is actually not the case (Check the data dictionary and think why). So, it is advisable to convert such feature values into categorical string values before proceeding with model building. Please refer the data dictionary to get a better understanding of all the independent variables.
 
You might notice the column 'yr' with two values 0 and 1 indicating the years 2018 and 2019 respectively. At the first instinct, you might think it is a good idea to drop this column as it only has two values so it might not be a value-add to the model. But in reality, since these bike-sharing systems are slowly gaining popularity, the demand for these bikes is increasing every year proving that the column 'yr' might be a good variable for prediction. So think twice before dropping it. 
 

**Model Building:**

In the dataset provided, you will notice that there are three columns named 'casual', 'registered', and 'cnt'. The variable 'casual' indicates the number casual users who have made a rental. The variable 'registered' on the other hand shows the total number of registered users who have made a booking on a given day. Finally, the 'cnt' variable indicates the total number of bike rentals, including both casual and registered. The model should be built taking this 'cnt' as the target variable.

> Dataset that is being used:
>> day.csv


**Model Evaluation:**

When you're done with model building and residual analysis and have made predictions on the test set, just make sure you use the following two lines of code to calculate the R-squared score on the test set.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions

**Significant Variables to predict demands for Shared Bikes:**
- yr: This is highly significant (p < 0.001) and positive, showing a large increase in rentals from 2018 to 2019.
- temp: Strong positive relationship (coef = 0.4507), meaning warmer temperatures increase bike rentals.
- windspeed: Negative impact on bike rentals (coef = -0.1422), meaning higher wind speeds reduce usage.
- season_Spring: Rentals significantly drop in spring (coef = -0.1152).
- season_Winter: Rentals slightly increase in winter (coef = 0.0423).
- mnth_Jul: Decrease in July bike rentals (coef = -0.0734).
- mnth_Sept: September shows a positive effect on bike rentals (coef = 0.0532).
- weathersit_Mist Cloud and Light Snow/Rain: Both have a negative impact, with Light Snow/Rain reducing rentals significantly (coef = -0.2801).

**Key Metrics:**
- R-squared: 0.829 – This means that about 82.9% of the variance in the target variable (cnt) is explained by the independent variables. It's a strong fit.
- Adjusted R-squared: 0.825 – This value accounts for the number of predictors and suggests that even after adjusting for them, the model explains 82.5% of the variance, indicating that the added variables contribute meaningfully.
- F-statistic: 241.4 with a p-value of 5.50e-184 – This implies that the model is statistically significant overall.

**VIF (Variance Inflation Factor):**
- VIFs are generally low (all under 5), which suggests that multicollinearity isn't a significant issue in your model.

**Residual Analysis:**
- Durbin-Watson: 1.973, very close to 2, indicating no strong autocorrelation in residuals.

**Error Metrics:**
- R² score: 0.8083 – This is similar to the OLS's R², confirming a good fit.
- Mean Squared Error (MSE): 0.00916 – A low error value suggests that the model is making accurate predictions.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- pandas - version 2.0.3
- numpy - version 1.24.3
- matplotlib - version 3.7.2
- seaborn - version 0.12.2
- sklearn - version 1.3.0
- statsmodels - version 0.14.0

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
Give credit here.
- This project was inspired by the Case Study which Upgrad offered
- This project was based on model building for shared bikes case study


## Contact
Created by [@AnkitSalian] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
