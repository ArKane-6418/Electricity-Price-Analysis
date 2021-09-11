# Ontario-Electricity-Price-Analysis

## Project Intro/Objective
In Ontario, there is an organization called the IESO (Independent Electricity System Operator). Their main objective is to ensure there is enough electricity supplied at real-time to meet the electricity demand in Ontario, while also planning for future energy needs. In short, they make sure that lights stay on and that Ontario has enough electricity to keep running. Furthermore, they also calculate the price of electricity in Ontario known as HOEP (Hourly Ontario energy price), which is the price consumers pay. This report will focus on analyzing how different variables affect the price of electricity. The purpose of this project is to track the trend of electricity prices, so
that consumers can make a more informative decision on the best time to consume electricity. It should be noted that being able to predict spot electricity prices is not only
valuable for consumers but it is critical for the operational planning and trading of conventional and renewable energy by generation companies.

### Methods Used
* Inferential Statistics
* Linear Regression
* Data Visualization
* Predictive Modeling
* t-test
* Residual Sum of Squares
* Adjusted Coefficient of Determination
* Mallow's Cp Constant
* Akaike Information Criterion (AIC)

### Technologies
* R 


## Project Description

We got our data from the [Independent Electricity System Operator (IESO) public website](http://reports.ieso.ca/public/Demand/) and [yesenergy](https://www.yesenergy.com/). We looked at the data from 2019 to make predictions about the demand and most impactful predictor variables for electricity prices in 2020. Our model was developed using a multiple linear regression analysis. We used the following predictor variables to predict the outcome of our response variable (YHourly Ontario Electricity Price (HOEP) (measured in $/MW)):
* X<sub>1<\sub>: Hour (1-24)
* X<sub>2<\sub>: Ontario Demand (measured in MW)
* X<sub>3<\sub>: Weekend/Weekday (binary data, 0 for weekday, 1 for weekend)
* X<sub>4<\sub>: Holiday (binary data, 0 for non-holiday, 1 for holiday)
* X<sub>5<\sub>: Peak Type (binary data, 0 for off peak, 1 for on peak)
* X<sub>6<\sub>: Temperature (measured in Fahrenheit)

We ensured our data set followed the four Gauss-Markov assumptions:
1. Linearity of the relation between the response variable
2. Independence of errors
3. Constant variance of errors (homoscedasticity)
4. Normality of the errors

After verifying the assumptions, we generated relevant matrices for calculating the optimal beta (coefficient) vector, the correlation matrix, and a pairs plot. From there, we discovered that Demand^2 and Temperature^2 were relevant predictor variables, thus giving us a polynomial regression. Then, we began our model selection process. Starting with all our variables, we first normalized all of our data. Then we performed backwards elimination to eliminate statistically insignificant variables, which we determined by looking at the corresponding p-values and checking if they were < 0.001. We continued this process until we were left with 4 predictor variables: HOEP, Demand, Peak Type, and Temperature. For each of our models, we calculated the residual sum of squares, adjusted R^2, Mallow C<sub>p</sub> Constant. and AIC to evaluate them. Finally, we plotted a residual plot against our fitted values from the best model to determine if there was a pattern.

Our final model is as follows:
* Y = -4.245e<sup>-1</sup> - 1.705e<sup>-1</sup>Hour + 4.499e<sup>-3</sup>Demand - 2.496e<sup>0</sup>*Peak - 1.713e<sup>-1</sup>Temperature

The full report and analysis can be found [here](https://drive.google.com/file/d/1vhCSdP1bPPCIfStqZpIzu_8WU8I7gYBL/view?usp=sharing).

## Getting Started

1. Clone this repo (for help see this [tutorial](https://help.github.com/articles/cloning-a-repository/)).
2. Raw Data is being kept [here](https://github.com/ArKane-6418/Electricity-Price-Analysis/blob/main/data/Data_Removed_87.csv) within this repo.
    
3. Data processing/transformation scripts are being kept [here](https://github.com/ArKane-6418/Electricity-Price-Analysis/blob/main/R-Code/Analysis%20Final%20Project.Rmd).

