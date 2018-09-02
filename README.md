# Crime Analysis Prediction

Linear Model to predict the crime rate of North Carolina. Detailed EDA done prior to building the model.

## Data Description

The dataset contains the data for crime rate in the state of North Carolina aggregated by county. <br/>
Data source: https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/crime_v2.csv

## Data Attributes

1. county - county identifier
2. year - 1987
3. crmrte - crimes committed per person
4. prbarr - 'probability' of arrest
5. prbconv - 'probability' of conviction
6. prbpris - 'probability' of prison sentence
7. avgsen - avg. sentence, days
8. polpc - police per capita
9. density - people per sq. mile
10. taxpc - tax revenue per capita
11. west - =1 if in western N.C.
12. central - =1 if in central N.C.
13. urban - =1 if in SMSA
14. pctmin80 - perc. minority, 1980
15. wcon - weekly wage, construction
16. wtuc - wkly wge, trns, util, commun
17. wtrd - wkly wge, whlesle, retail trade
18. wfir - wkly wge, fin, ins, real est
19. wser - wkly wge, service industry
20. wmfg - wkly wge, manufacturing
21. wfed - wkly wge, fed employees
22. wsta - wkly wge, state employees
23. wloc - wkly wge, local gov emps
24. mix - offense mix: face-to-face/other
25. pctymle - percent young male

## Objective

1. To perform **univariat**e and **bivariate exploratory analysis** of the dataset provided.
2. To develop a suitable **linear model with crmrte as the dependent variable** based on the EDA findings.
3. To explain the various aspects of the model used.

## Data Analysis & Data Cleaning

1. **The last row was getting read as 'object' data. It was found to be due to the special symbol at the last row, last column 0.074198931'**. Removed the special symbol from input csv file, to fix it.

2. It is to be noted that the **maximum value of probability features, prbarr & prbconv, are > 1** which is a data anomaly. prbpris & pctymle are found to be < 1.

3. There are 91 entries for all the 25 columns. Hence, there is **no missing value in the input dataset. Thus, no need to do data imputation** or to drop any feature.

4. The zeros for features, west, central and urban are expected, as the data is inherently boolean.

## Univariate Analysis

Univariate visualization   provides summary statistics for each field in the raw data set. It is conducted **to find out how much a single feature in the dataset** would be helpful to determine the target feature, here in this case, crime rate.

![uva](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/uva.PNG)

![uvaf1](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/uvaf1.PNG)

![uvaf2](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/uvaf2.PNG)

![uvaf3](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/uvaf3.PNG)


## Probability/ Cumulative Distribution Function (CDF)

![cdf1](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/cdf1.PNG)

![cdf2](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/cdf2.PNG)

## Bivariate Analysis

Bivariate visualization is performed to find the relationship between each variable in the dataset and the target variable of interest, i.e. crime rate. The plot of all features against crime rate is done as below.

![biv1](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/biv1.PNG)

![biv2](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/biv2.PNG)

## correlation among features for each location: 'west', 'central' & 'urban'

Lets try to find if there is any correlation among features for each location: 'west', 'central' & 'urban'.

Number of data points in category: west is 23
Number of data points in category: central is 34
Number of data points in category: urban is 8

**Location: west**

![fcp1](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcp1.PNG)

![fcp2](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcp2.PNG)

![fcp3](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcp3.PNG)

![fcp4](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcp4.PNG)

![fcp5](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcp5.PNG)

**Location: central**

![fcpc1](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcpc1.PNG)

![fcpc2](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcpc2.PNG)

![fcpc3](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcpc3.PNG)

![fcpc4](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcpc4.PNG)

![fcpc5](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcpc5.PNG)

**Location: urban**

![fcpu1](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcpu1.PNG)

![fcpu2](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcpu2.PNG)

![fcpu3](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcpu3.PNG)

![fcpu4](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcpu4.PNG)

![fcpu5](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/fcpu5.PNG)

## Linear Regression Fit of Strongly Correlated Features

We have a lot of features to analyse in the input dataset. So let's take the strongly correlated quantitative features from this dataset and analyse them one by one.

![cf1](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/cf1.PNG)

![cf2](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/cf2.PNG)

## Box Plots

Let's do the box plot & violin plot for the boolean features 'west', 'central', 'urban' to find impact on crime rate, if any.

![bp](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/bp.PNG)

## Violin Plots

![vp](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/vp.PNG)

## Feature-Feature Correlation Analysis

Many times, more than one input could be dependent on each other. In Linear Regression, the requirement is that all the input variables are independent of each other.

When a feature is dependent on one or more of the other input features, it leads to a phenomenon known as multi-collinearity. **Multi-collinearity among features can be identified by doing Feature-Feature correlation analysis**.

![hm1](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/hm1.png)

![hm2](https://github.com/AdroitAnandAI/Crime-Analysis-Prediction/blob/master/images/hm2.png)

## Conclusions

### Data Analysis and Cleaning

It is found, that **some rows have to be dropped** before doing regression analysis. The **special character error in the input dataset is also fixed**.

### Univariate Analysis

1. The features **density, mix, police per capita, probability of conviction and tax revenue per capita seems to have similar distribution as crime rate**. But no definitive conclusion can be made from this observation. 

2. One **strange observation is in weekly wages of service industry (wser).** More than 95% of wages lies below 400, but the maximum wage is around 2250.

3. From the data, this is identified to be **county 185**. As the percentage of minorities in this county is high (nearly 65%) and wages in other sectors are comparatively less, the wages of service industry is mostly an error. We will remove **"county 185"** from the input data.

4. Though the maximum value of tax revenue per capita is 120, more than 50% of values lies below 40.

5. Though the maximum value of police per capita is 0.009, more than 60% of values lies below 0.001.

### Bivariate Analysis

1. Based on the above pairplot, it can be noted that **density is most positively correlated with crime rate. There is also some correlation with weekly wages under different domains but it needs further investigation, as they are not so pronounced.**

2. Strangely, the **weekly wage features and crime rate is found to be slightly positively correlated. This signifies unequal distribution of income** or probability high unemployment rate. One of the most important features that is not in the given data is unemployment rate.

### Correlation among features for each boolean feature

1. Some of the correlation lines are showing upward or downward trends more than before.

2. **Probability of conviction is found to have negative correlation with crime rate in both west and central, but not in urban areas**.

3. **Tax Per capita is found to have positive correlation with crime rate in both central and urban areas**.

4. **Percentage of minority is positively correlated with crime rate, both in west and in urban areas**.

5. Thus, a combination of density and urban (or west or central) can help aid crime rate prediction.

6. However, there seems to be **not much data for 'urban areas'** to arrive at a conclusion.

### Linear Fit of Top Correlated Features

1. The crime rate in urban areas is found to be significantly high. Thus, the feature 'urban' is an useful variable for prediction.

2. The crime rate in west is found to be less and central moderate. But as there is significant overlap, such variations may not to be very helpful for prediction.

### Feature-Feature Correlation Analysis

1. Many times, more than one input could be dependent on each other. It leads to a phenomenon known as **multi-collinearity, which can be identified by doing Feature-Feature correlation analysis.** In Linear Regression, the requirement is that all the input variables are independent of each other.

2. The **density and urban variable seems to be highly correlated**, which is obvious, because urban areas are densely populated.

3. **Some of the "wage features" are positively correlated**, as the wage increase/ decrease in one domain would certainly influence the other. For example, **wtrd & wfir are positively correlated to wfed & wloc. Also, wfir and wtrd have moderate correlation**.

4. Density and crime rate have a correlation of 0.73. But **density has high correlation with 'urban' feature. Hence, whether both features, density and urban, are useful to predict crime rate needs further investigation. We wll use linear regression to sort out this question**.

5. The feature, 'urban' has a correlation of 0.62 with crime rate, but whether the correlation is because 'urban' has very high correlation with 'density' is yet to be known.

6. Wage columns, wfed & wtrd are positively correlated to 'density' feature. This can be intuitively understood as the weekly wages would be higher in urban areas.

### The above observations from EDA would be carried forward to help Linear Regression (Part II).
