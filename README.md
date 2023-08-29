# used_car_price_prediction
This repo contains ML model and analysis used for predicting the used cars price and the factors contributing to the same.
The goal is to determine the primary factors that contirbute to the cost of used car and therby learn what features customers find as value for them in a used car.

Link to Explore Notebook: https://github.com/seetharamanr86/used_car_price_prediction/blob/main/Practiical_Application_2.ipynb

Data Used: vehicles.csv (an inventory of used cars)

General findings:

Data Observation:

- There is a total of 18 columns and 426K rows
  
- Majority of columns has data type as 'object' and requires a change before analysis/prediction
  
- There is a overwhelming number of missing values, so we cannot drop the rows, rather, requires some sort of imputation to address

- 'Model' feature is more correlated to 'price' than any other

- There were many columns such as id, VIN, size, etc., were found not useful and that should be dropped

- There were inappropriate values in few columns, those are either exceeding thresholds or completely unreasonable (example: price, odometer)

Data Preparation:

- Had to drop minimal missing values from not impactful columns

- Used unique constant values to fill in missing values for categorical features, rather than dropping and losing row count

- Used target encoding technique to convert cataegorical features into numerical values

- Performed Principal Component Analysis (PCA)

Modeling:

- Used Linear Regression model

- Used Polynomical Features

Evaluation:

- Used Cross Validation technique

Deployment:

Initially, through correlation, we could say 'model' is strongly correlated to the 'price' and could be a primary factor for used car price.

Also, through RFE process, we could arrive at the following features as most impactful ones among all for price determination Those are year, model, odometer, tramission and state.

Evaluation & Outcomes

In the model building process, we did use Linear Regression model and Polynomial Features. We did determine mean squared error ( MSE: 414561029857077.6) but that was too high and unusual for the data used. We also determined mean squared error and R square using ploynomial features. They were MSE: 16742.92221878973, R**2: 0.9999999209792655.

We have determined the residuals in each approach and plotted it against the prices. The values in the graph were a bit abnormal.

For evaluation, we have used the Cross Validation technique. It produced mean square error of 2.27e-15. There are other techniques available as well.

Next Steps

Dataset required a lot of cleaning. It required techniques to impute the missing data. We did use target encoding with mean values. It doesn't appear to be the best approach. We need to try out different techniques to handle the missing values, as data preparation is the key for success.

Assumptions made to replace impossible values such as 0 price, 0 odometer were replaced with mean values and that could be impacting the results. Need to find another alternate technique.

One of the primary challenge was handling the categorical features. We had a many categorical features and especially few had several distinct values with no ordinal values. This has prevented using tehcniques such as one hot encoding but rather forced to use target encoding. One of the drawbacks was overfitting. We have to explore more to find a best technique to handle categorical features.
