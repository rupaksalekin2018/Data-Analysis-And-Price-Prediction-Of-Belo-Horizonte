# House Pricing Prediction in Belo Horizonte
#### Data Set Link: https://www.kaggle.com/datasets/guilherme26/house-pricing-in-belo-horizonte

## Intro
This dataset contains information on house prices in Belo Horizonte, Brazil, and was created by Guilherme26. The dataset includes information on various attributes of the houses such as number of rooms, area, and location, as well as the sale price.

## Content
The dataset consists of a single .csv file with the following columns:
-   **'area':** The total area of the house (in square meters)
    
-   **'rooms':** The number of rooms in the house
    
-   **'bathroom':** The number of bathrooms in the house
    
-   **'parking_spaces':** The number of parking spaces available
    
-   **'floor':** The floor of the house (if the house is part of a multi-story building)
    
-   **'animal':** Whether or not the house allows animals
    
-   **'furniture':** Whether or not the house is furnished
    
-   **'hoa':** The monthly homeowner's association fee (if applicable)
    
-   **'rent_amount':** The monthly rent amount for the house
    
-   **'property_tax':** The monthly property tax amount for the house
    
-   **'fire_insurance':** The monthly fire insurance amount for the house
    
-   **'total':** The total monthly cost of owning the house (including rent, taxes, insurance, and any other fees)

## Acknowledgements

This dataset was created by Guilherme26. Kaggle provides hosting and support for the dataset.

## Inspiration

This dataset can be used to build models to predict the sale price of houses in Belo Horizonte based on various attributes. Additionally, this dataset could be used to explore patterns and trends in the housing market, such as the impact of location, number of rooms, and other factors on house prices.

## Methodology

1.  At first we import the necessary libraries & load the dataset
    
2.  We checked the shape of the row and column.
    
3.  We checked the column names
    
4.  We checked the column data type
    
5.  We checked null value
    
6.  We checked target column (price) statistical description
    
7.  We checked for target column data distribution
    
8.  We plotted the correlation of numerical columns
    
9.  We found that distribution of target column is right skewed
    
10.  We transformed the distribution into normal data distribution
    
11.  We cleaned up of square-foot into single value
    
12.  We cleaned up of city into single city Belo Horizonte
    
13.  We found the NaN value of ADM-FEES
    
14.  We replaced ADM-FEES NaN values with the mean of respective Neighborhood using group by
    
15.  We dropped null ADM-FEES
    
16.  We replaced DF with Normally Distributed Dataframe
    
17.  We transformed Garages and Room Type From Object To Float
    
18.  We label encoded ( Categorical To Numerical ) of Neighborhood Column
    
19.  We removed City & Address As It only has Belo Horizonte data
    
20.  We splitted the Data into 80 & 20
    
21.  Applied Linear Regression, XGBoost & CatBoost
    
22.  Hyper Tuning Using Grid Search CV in XGBoost, Catboost & Linear Regression
    
23.  Removing Latitude & Longitude From Data Frame
    
24.  Training Linear Regression, XGBoost & Catboost, performance did not increase

## Results:
We initially kept the Longitude and Latitude column of the dataset. Then we trained various models with the data. Only hyper tuned XGBoost, Regular CatBoost Regression & hyper tuned CatBoost Regression performed well.

| Model      | R2 Score | Mean Absolute Percentage Error    |
| :---        |    :----:   |          ---: |
| Linear Regression      | 0.1998       | 0.6486   |
| XGBoost   | -0.2053        | 260596.1157     |
| Hypertuned XGBoost      | 0.7322     | 0.3952   |
| CatBoost  | 0.7213           |0.1325   |
| CatBoost Hypertuned  | 0.7020        | 0.3952     |

Now, we show the result for the model trained without longitude and latitude columns.

| Model      | R2 Score | Mean Absolute Percentage Error    |
| :---        |    :----:   |          ---: |
| Linear Regression      | 0.1852      | 0.6644   |
| XGBoost   |0.2816       | 0.4967     |
| Hypertuned XGBoost      | 0.6823     | 0.1397   |
| CatBoost  |0.6732         |0.1457   |
**From these two tables we can clearly say CatBoost Regression with Longitude and Latitude columns performed best.**
