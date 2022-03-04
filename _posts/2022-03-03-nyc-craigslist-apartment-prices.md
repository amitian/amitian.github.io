---
layout: post
title: Predicting Craigslist NYC Apartment Rental Prices
---
### Abstract

The goal of this project was to examine how an NYC apartment's monthly rental price might be affected by its features (i.e. square footage, location, amenities) in order for tenants and landlords to gain a better understanding of the rental market. I used data scraped from Craigslist's NYC apartment rental postings to build a linear regression model that could predict apartment rental prices based on certain features.

### Design

This model could be used by tenants to find out if they are being undercharged or overcharged on their rent given the features of their apartment, or it could be used by landlords who are trying to determine a fair price to charge tenants. It could also be used by apartment-seekers who want to know how different features might influence the price of the rental and make decisions accordingly; for example, perhaps having an in-unit washer/dryer will become less of a priority for a potential renter once they learn that it correlates with a $400/month rental price increase.

### Data

The data was scraped in one day from Craigslist's NYC apartment rentals section by scraping all of the posts (which go back to around 30 days) from each borough. Although the data scraped initially included over 7,000 data points, after cleaning the data, 4,609 data points were used to develop the model, with the model itself using 3,679 data points in the training/validation sets and 911 data points in the test set.

The target was the apartment's monthly rental price. The features ultimately included in the model were: square footage, number of bedrooms, number of bathrooms, broker's fee, washer/dryer, parking, and borough (in addition to two interaction features).

### Algorithms

**Feature Engineering**

1. Imputing missing square foot values based on the median square footage by borough and number of bedrooms
2. Creating binary dummy variables for categorical values and dropping one from each to avoid falling into the dummy variable trap
3. Creating interaction terms BR-BA and MNH-SQFT to try to account for the interactions between 1) number of bedrooms and bathrooms and 2) square footage and being in Manhattan, respectively
4. Eliminating features that possessed little to no influence on the performance of the model (application fee, pets allowed)

**Model Evaluation and Selection**

The dataset was split into 80/20 training vs. testing data, and 5-fold cross-validation was used on the training data to generate R-squared scores, mean absolute error, and root mean squared error. The model was only exposed to the testing data at the end of the process.

The models evaluated were OLS regression, Linear Regression, Polynomial Regression, Ridge Regression, and Lasso Regression. Ridge Regression with an alpha of 20.729 was ultimately chosen for its slightly higher R-squared as well as its smaller margin of error (for both mean absolute error and root mean squared error).

**Training Scores using 5-fold CV:**

R-squared (mean of 5 scores): `0.526`

Mean Absolute Error (mean of 5 scores):`648.65`

Root Mean Squared Error (mean of 5 scores):`1027.45`

**Testing Scores:**

R-squared: `0.519`

Mean Absolute Error: `671.15`

Root Mean Squared Error: `1127.72`

### Tools

- Selenium and BeautifulSoup for web scraping
- Numpy and Pandas for data cleaning and manipulation
- Statsmodels and Scikit-learn for modeling
- Matplotlib and Seaborn for plotting and visualizations

### Communication

Ultimately, the linear regression model could only account for approximately 50% of the variance for the NYC monthly apartment rental prices scraped from Craigslist, suggesting that other factors must be taken into consideration when attempting to predict an apartment's rental price.

Estimated Coefficients of Features:
![download](https://user-images.githubusercontent.com/81931093/155893903-cdc56fed-038f-4df5-8a19-bc6be10712d0.png)

NYC Monthly Apartment Rental Price by Borough:
![download (1)](https://user-images.githubusercontent.com/81931093/155893927-d14f9952-4d4b-41cf-879b-501462fa2a5e.png)

See .pdf of Google Slides presentation for more graphs and info on GitHub: [https://github.com/amitian/NYC-craigslist-apt-prices](https://github.com/amitian/NYC-craigslist-apt-prices)
