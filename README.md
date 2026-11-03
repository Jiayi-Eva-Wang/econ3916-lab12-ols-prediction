# econ3916-lab12-ols-prediction

# OLS as a Line of Best Fit: Estimation versus Prediction

## Objective

In this lab, I learned how to use OLS regression to estimate relationships between variables and predict house values. I also compared how well different models perform on training and test data.

## Methodology

- I used the California Housing dataset with 20,640 observations.
- I fitted the same OLS regression using three methods: the closed-form formula, statsmodels, and scikit-learn.
- I added up to 100 random noise variables to see how R-squared and adjusted R-squared changed.
- I split the data into 80% training and 20% testing before fitting the model.
- I calculated RMSE and R-squared for the training and test sets.
- I estimated the coefficient of AveRooms and its 95% confidence interval while controlling for median income.
- I wrote a function called `holdout_rmse()` to calculate test RMSE using different predictors.

## Key Findings

All three OLS methods gave the same intercept of 0.450856 and slope of 0.417938. This showed me that different methods can produce the same regression line.

R-squared increased from 0.4734 with no noise variables to 0.4758 with 100 noise variables. However, adjusted R-squared decreased to 0.4732. I learned that adding more variables does not always make a model better.

For the model with eight predictors, the training RMSE was 0.7197 and the test RMSE was 0.7456. The test error was slightly higher, which showed why it is important to evaluate a model on data it has not seen.

The coefficient of AveRooms was -0.0381, with a 95% confidence interval of [-0.0430, -0.0333]. This suggests a negative association with house value after controlling for median income, but it does not prove causation.

Using median income alone, I got a test RMSE of 0.8421. This was higher than the eight-feature model's test RMSE of 0.7456, a difference of about $9,650 in RMSE units converted to dollars.

## Conclusion

This lab helped me understand that estimation and prediction are two different goals of regression. A model can have statistically significant coefficients or a higher training R-squared without necessarily making better predictions. I learned that test RMSE is useful for comparing how well models predict new data.
