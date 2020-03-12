## Predicting movies revenues with the OLS model

*This project was completed as part of my cursus at Ironhack (a 9-week intensive coding bootcamp).*

The objective of this project was to **predict movie revenues from an IMDB dataset with linear regression**, and was *my very first attempt to create a machine learning model*.

This project has a lot of flaws (absence of distinct train and test sets, no standardization of parameters despite their great difference in scales, etc.), but is still **a good introduction to some of the basic principles of OLS models**. *If I have some time soon, I might try to improve it using the concepts that we learned later in the course.*

#### WHAT IS THE DATASET?

- The dataset is consists in IMDB-scrapped data, and was downloaded from [this Kaggle page](https://www.kaggle.com/danielgrijalvas/movies).
- Number of movies: 6,813
- Date range: 1986 - 2017

#### DATA CLEANING

**Three main types of transformations** were applied to the data:

***Adjust Budget and Gross***
- Smoothing Budget and Gross amounts with inflation
- Drop Budget and Gross outliers
- Remove rows for which Gross/Budget ratio > 25
- Remove rows that are outside Gross whiskers or Budget whiskers

***Assess Director and Star popularity***
- Add Director and Star movie count over the period
- Add Director maximum gross generated over the period
- Add the number of Star nominations over the 5 years preceding the movie (scrapped from Oscars and Golden Globes websites)

***Categorize Production companies***
- Tier 1 if they generated the top 20% of market revenue, etc. until Tier 5.

#### MODELING APPROACH

OLS (*Ordinary Least Squares*) model, followed by assumptions checks

#### MODEL RESULTS

**The results of the modelling phase are not satisfying**: predicting movie revenues seems to be a bit more complex than applying a linear regression model.

- **Final R-Squared**: 59.1%
- The model didn't pass **OLS assumptions tests**:
    - The ***Harvey Collier test*** shows that the model is not linear.
    - The ***Anderson Darling Test*** shows that residuals are not normally distributed.
    - The ***Het Breusch Pagan Test*** shows that there is a high variance in residuals (heteroskedasticity).