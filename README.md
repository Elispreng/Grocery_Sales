# Grocery Sales: Updated Coding Dojo Project (June 2023) by Eli Spreng
  
 <img src="https://github.com/Elispreng/Grocery_Sales/blob/main/Images/Big%20Mart%20.png" width="300" height="200">

# Summary
This analysis explores the  sales of supermarket/grocery items in select stores belonging to the international chain Big Mart during 2013.
In this presentation there are exploratory/explanatory data visuals using Python, Seaborn and Tableau. This project also utilizes machine learning. feature importance, and coefficients using SHAP summary plots and LIME analytics. 

### Data:
[Big Market Sales Prediction](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/#About)

### Business problem:

In looking at grocery sales, interested parties want to know what will will increase sales. This project analyzes what factors have the greatest
impact on grocery outlet sales.

## Methods
- To perform this analysis the data was cleaned and then exploratory and explanatory visuals offer insights
- Machine learning using regression metrics provides another way to understand grocery sales. 
- Deeper Analysis includes SHAP summary and LIME metrics
- Tableau visuals offer another way to visualize the data. 


### **Data Dictionary:**

**Attribute** | **Type** | **Description**  
--- | --- | ---
Item_Identifier | float | individual item number
Item_Weight | float|  weight of item
Item_Fat_Content | object| description of fat (high or low fat content}             
Item_Visibility | float64 | visbility of item
Item_Type |object| item description
Item_MRP  |float64| suggested retail price
Outlet_Identifier |object| type of store
Outlet_Establishment_Year |int64| year store was established
Outlet_Size | object | size of store
Outlet_Location_Type |object| geographical location zone
Outlet_Type  |object| grocery of supermarket
Item_Outlet_Sales |float64| item sales


# Exploratory Data Analysis

#### Visual 1: Bar Graph Showing Outlet Year and Sales
![image](https://github.com/Elispreng/Grocery_Sales/blob/main/Images/Bar%20Plot%20for%20Sales%20and%20Year.png)
The graph addresses answers the question "What year has the highest item  sales?" The highest item sales were in 2004.

#### Visual 2: Bar Bar Graph Showing Outlet Year and MRP

![image](https://github.com/Elispreng/Grocery_Sales/blob/main/Images/Bar%20Plot%20for%20Item%20MRP%20and%20Year.png)


This bar graph answers the question "What  year has the highest MRP?" The highest MRP was in 2004.
#### Visual 3: Top Perfomers of Item Type by Store
![image](https://github.com/Elispreng/Grocery_Sales/blob/main/Images/Bar%20Plot%20for%20Item%20Type%20%20and%20Store%20Number.png)

#### Visual 4: Bar Graph  of Top Selling Store with Year (Tableau)
![image](https://github.com/Elispreng/Grocery_Sales/blob/main/Images/Best%20Performing%20Store%20with%20Year%20Tableau.png)

#### Visual 5 Bar Graph of Top Selling Item Type (Tableau)
![image](https://github.com/Elispreng/Grocery_Sales/blob/main/Images/Item%20Type.png)

# Machine Learning

## Machine learning and metrics
- Linear Regression Model
- Regression Tree Model
- Bagged Trees Model

### Linear Regression Metrics:

- Model Training R2: 0.6714424977432687
- Model Testing R2: 2.0994337117833997e-05

### Decision Tree Model Train Scores
 - MAE: 0.0 
 - MSE: 0.0
 - RMSE: 0.0 
 - R2: 1.0

### Decision Tree Model Test Scores
 - MAE: 992.59
 - MSE: 2103175.48
 - RMSE: 1450.23
 - R2: 0.2376974

### Bagged Trees Model Train Scores
 -  MAE: 316.56
 -  MSE: 240010.01
 -  RMSE: 489.91
 -  R2: 0.91

### Bagged Trees Model Test Scores
 - MAE: 785.63
 - MSE: 1279.28
 - RMSE: 1131.11
 - R2: 0.53


The Decision Tree model is the top performer between the  models utilized to attempt to predict item sales. However, the size of the errors in the model limit its usefulness. At best it could potentially account for around 60% of the item price based on the accompanying data.

## Recommendations:

From these metrics, the bagged tree model is the best model with the lowest error and highest R2. However, there is still some variance in this model. 

## Limitations & Next Steps

This project will include more graphics. Another limitation is the regression metrics still need tuning in the models. 
# Coefficents, SHAP, and LIME
#### Visual 1: Bar Graph Showing Top 15 Coefficients for Linear Regression
![alt text](https://github.com/Elispreng/Project_1/blob/main/Images/Top%2015%20with%20Linear%20Regression2.png)

#### Interpretation of Coefficients
- Item Type Seafood: Seafood sales affect sales more
- Outlet Type Supermarket: Supermarkets sell more than grocery.
- Item Type Starchy Foods: Starchy foods affect sales. 
- Item Type Breads: Breads sell more
- Outlet Locaion:  where the supermarket is  affects sales. 


#### Visual 2: Bar Graph Showing Top Features for Random Forest
![alt text](https://github.com/Elispreng/Project_1/blob/main/Images/Feature%20Importance%20for%20Random%20Forest.png)

#### Interpretation  of Top 5 Features for Random Forest
- Item MRP: suggest retail prices affects the sale
- Item visibility affects the sales
- Item weight affects the sales
- Outlet Year affects the sales: when the outlet was built. 
- Snack Foods affect the sales

#### Visual 3: Bar Graph Showing Top 15 with Shap
![alt text](https://github.com/Elispreng/Project_1/blob/main/Images/Shap%20Bar%20Plot.png)

### Feature Comparison
-The feature comparisons with Shap are  almost the same. The only difference is the fifth feature. In  Shap, it is Outlet type and and in the original random forest  and the fifth feature was snack foods. 

#### Visual 4: Shap Summary Dot Plot
![alt text](https://github.com/Elispreng/Project_1/blob/main/Images/Shap%20Summary%20Plot2.png)

Three most important features interpretation:
Item MRP: lower the MRP the more likely the model will predict a sales price.
Item Visibility: Higher value of Visibility leads to lower sales.
Item Weight: Higher value of Weight leads to lower sales.

### First Example:High Visibility
#### Interpretation of LIME
![alt text](https://github.com/Elispreng/Project_1/blob/main/Images/HighVizLIME.png)
The predicted sales value is 369.03
Orange signifies the positive impact and blue signifies the negative impact of that feature on the target. 
- Top 3 Positive impact on sales prediction 
  - item type of meat, supermarket type 2, location/tier 3 and frozen foods. 
- Top 3 Negative impact on sales prediction
  - Item MRP, Breakfast, Snack Foods 

### Interpretation of Force Plot
![alt text](https://github.com/Elispreng/Project_1/blob/main/Images/HighVizForcePlot.png)
- In this case, item type meat has  a positive impact on the prediction. Outlet size medium and supermarket type 2 also have positive impact on predicting sales. Two  features  have a negative impact on the prediction. These features Item MRP and  visibility. 


### Second Example High MRP 
#### Interpretation of LIME
#### The predicted sales value is 260.93
  - Orange signifies the positive impact and blue signifies the negative impact of that feature on the target.
 - Positive impact on sales prediction
    - Item MRP, Item Visibillity, and Supermarket type 2
 - Negative impact on sales prediction
     - Starchy Foods, Hard Drinks, and Baking Goods

![alt text](https://github.com/Elispreng/Project_1/blob/main/Images/LIME_HighMRP2.png)

#### Interpretation of Forceplot 
In this case, feature 'Item MRP' and 'Outlet Size small' have a positive impact on the prediction, while 'Item Weight' and 
'Item Visibility' have a negative impact on the prediction.
![alt text](https://github.com/Elispreng/Project_1/blob/main/Images/Force_Plot_High_MRP)

# Tableau Dashboard
[See the Dashboard](https://public.tableau.com/views/GrocerySales_16866134110060/BigMart?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link)

![alttext](https://github.com/Elispreng/Grocery_Sales/blob/main/Images/Dashboard.png)


### For further information


For any additional questions, please contact **doctor.eemail@gmail.com**

