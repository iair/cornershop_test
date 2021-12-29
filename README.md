# Process and Results of the challenge

This is the repository of the Corneshop test for the Data Scientist position. In this repository you will find the solution i made for this challenge which can be separate into 5 stages:

* Extract and transform the data on the get_data.ipynb file in the notebooks/exploratory folder where i extract all the geo-location data that i will use using the geocipy library
* Exploratory analysis of the data using basic stadistics (mostly measures of central tendency) and graphical analysis in order to understand the data in the EDA.ipynb fiile in the notebooks/exploratory folder
* POC of the model in the poc_model.ipynb file in the notebooks/exploratory folder where i tested 3 regression models using different configurations of variables and parameters
* Final model in the training.ipynb file in the notebooks/prototypes folder where i made my model with the optimized parameters
* predictions in the prediction.ipynb file in the in the notebooks/prototypes folder where i made the predictions using my final trained model

The theorical result whas a model usign XGboost Regression that give us a MAE of 10.7 minutes and MSE of 204.9 minutes. It's important to notice that 75% of the error is less than 15 minutes


# Instructions

## Cornershop´s Data Science Test

Cornershop has operations in several cities and countries, delivering thousands of orders every day. In order to deliver these orders on time we depend on good estimations of how much time the shopper needs to complete the order.

In this technical test you will be creating a machine learning model to make these estimation. As we internally build our machine learning solutions using python, we ask you to do the same in this technical test. However you are free to use the libraries you are most comfortable with.

### Objective

The objective is to predict the `total_minutes` a order takes to complete, where the rows not containing a `total_minutes` value should be set aside as a part of the submission file, containing the `order_id` with the predicted values. 

As we are interested in seeing how you attacked the problem, we also ask you to include your code together with the submission file. The code needs to be well documented, explaining the decisions made. With these explanations, we will be looking at everything from how the data was processed, features used to the completed model and predictions. 


## Data

In this repository, we have included data representing the order, shopper and the store branch. 

### File description and data fields
***order_products.csv:***
- order_id: ID of the order
- product_id: ID of the product
- quantity: The quantity ordered of this product
- buy_unit: The unit of the product (KG/UN)

***orders.csv:***
- order_id: ID of the order
- lat: The latitude of the delivery location
- lng: The longitude of the delivery location
- promised_time: The delivery time promised to the user
- on_demand: If true, the order was promised to be delivered in less than X minutes
- shopper_id: ID representing the shopper completed the order.
- store_branch_id: ID of the store branch
- total_minutes: The total minutes it took to complete the order (label)

***shopper.csv***
- shopper_id: ID of the shopper
- seniority: The experience level of the shopper.
- found_rate: Percentage of products found by shopper historical.
- picking_speed: Historical picking speed, products pr minutes.
- accepted_rate: Percentage of orders historically accepted by shopper
- rating: client rating of shopper

***storebranch.csv:***
- store_branch_id: ID of the store branch
- store: ID representing the store
- lat: Latitude of the branch location
- lng: Longitude of the branch location

*All the data has been anonymized*
