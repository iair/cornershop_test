This is the repository of the Corneshop test for the Data Scientist position

# Objetive definition

My goal will be to minimize late arrivals that are out of the predicted range, identified as that the predicted estimated time is less than the actual arrival time.

This approach differs from the classic one measured by metrics such as MSE or MAE but it is more useful in the business context of a delivery such as Cornershop. This implies that we will allow early arrivals at the estimated time, which for this POC will not be considered as an error or penalized (but they should be when it is too early in future versions)

Given this, we will use two metrics as main indicators:

% of orders that arrive on time or ahead of the prediction, which we will try to maximize

MAE of orders that arrive late with respect to the prediction, which we will try to minimize

# Resume of the final results

 Final model with XGBoost applied to data with null values and Gradient Boosting Regression with quantile parameter on 90% applied to data withouth null values

 * 87.4% of orders will arrive on time or before the estimation time
 * Late arrivals MAE : 19.3 minutes
 * General MAE : 1701 minutes
 * General MSE : 35.7 

This results were acomplish using using a XGboost Regression (using the scikit-learn interface of the XGBoost package) for the data with NA's and Graiden Boosting regression with quantile parameter 90 and Gridsearchcv for parameter optimization

# Description of the process

In this repository you will find the solution i made for this challenge which can be separate into 5 stages:

* Extract and transform the data on the get_data.ipynb file in the notebooks/exploratory folder where i added all the geo-location data using the geocipy library and made some usefull transform to the data in order to make a better EDA and modeling

* Exploratory analysis of the data using basic stadistics (mostly measures of central tendency) and graphical analysis in order to understand the data in the EDA.ipynb fiile in the notebooks/exploratory folder

* POC of the model in the poc_model.ipynb file in the notebooks/exploratory folder where i tested 3 regression models using different configurations of variables and parameters

* Final training of the model is in the training.ipynb file in the notebooks/prototypes folder where i made my model with the optimized parameters

* The trained models are in the models folders with the names : gbq_reg.pkl and xgb_reg.pkl

* Final predictions are in the prediction.ipynb file in the in the notebooks/prototypes folder where i made the predictions using my final trained model
