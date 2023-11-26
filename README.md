# House-price-exercise
Practicing Data Preparation and Feature Engineering


Data Cleansing and Feature Engineering:

1. Understanding the data
  There are total of 80 variables with 43 categorical variables and 37 numerical variables.
<img width="196" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/82deaa14-5727-4a28-95f5-762710a5aa0b">

<img width="209" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/7ed6375a-8152-484d-91c4-17255f7358ae">

<img width="257" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/c2775f32-079a-4abf-815c-ba9f2039a3c3">

1.1  Understanding the data- “Sale Price”
   To check the value distribution of target column(“Sale Price”)
   
   <img width="428" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/885ec4f9-1123-4185-82c9-192c89ce8506">
   
   <img width="428" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/206beaa8-9b18-4f1d-8a77-b8aa4cd7ddad">

2. Identify and handle missing values- Target variable (Sale Price)

<img width="876" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/79ed461f-3b42-4d7f-858f-2f8e08ad6b38">

There are no missing value in ”Sale Price” column


4. Handling the outlier values of the target variable - “Sale Price”
Both distribution and Probability plot show that Sale Price is not normal distribution
The outlier of sale price should be dropped that make Sale Price to be normal distribution
Probability plot: assessing whether or not a data set follows a given distribution such as the normal

<img width="383" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/cd4b3a9c-3118-4e8d-8929-1f8f934b6c2c">

<img width="417" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/81491913-113c-4fc2-83f9-58373224b80b">


6. The transformation of the normal distribution of the sample
skew of Sale Price: 1.8828757597682129
Kurtosis of Sale Price: 6.536281860064529
We would like to adjust the skewness and kurtosis of the Data to make it normal distribution by using function f(x). 
Sale Price is left skewed; we would like to skew sale price to right through higher change in left and smaller change in right

<img width="383" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/4daafe79-1278-438b-a562-8c5f2d2772a4">

<img width="435" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/57bd6334-8d03-4a80-8b27-78b4fda62104">

8. The transformation of the normal distribution of the sampleNew distribution
The new distribution and probability show that the skewed version is almost close to normal distribution

<img width="390" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/d6de19a8-ab3d-467a-902e-cda6ccb267bc">

<img width="397" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/4d4a40d4-3122-4ed6-a14f-cacbf9a440d3">



10. Identify and handle missing values- Variables
There are total of 19 variables with missing values
That are 16 categorial variables and 3 continuous variables

Total number of continuous variables with missing values: 3
Total number of categorial variables with missing values: 16

<img width="97" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/df702692-b766-42e5-863a-edd2abdaa2de">

<img width="115" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/3e91f2e8-cae8-44ce-ad80-dc367a44fd07">

<img width="234" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/59aec275-91ab-401c-8933-6d76b9ebe61f">

7. Identify and handle missing values- Categorial variables
Before handling the missing values in categorial variables, we can look through all data in categorial variables
We can observe that all of these missing data are related to the house's equipment/function, so we assume that all of the missing data are related to the house's lack of functionality, so we need to fill in "None" for all missing values to indicate that there are no relevant equipment in the house

<img width="430" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/b39d4a36-84f5-4e22-ad24-e18052063e8d">

9. Identify and handle missing values- Categorial variables
10. 
  <img width="476" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/fcd267d0-4dc6-4b2a-b72a-c3d4e954bc64">

9.Identify and handle missing values- Continuous variables
“LotFrontage” : As “LotFrontage”  means Linear feet of street connected to property, so it is unlikely not to exist, so we assume that the missing values in “LotFrontage”  mean that people do not know or they forget to fill in. Therefore, we would like to fill with the median to avoid the effect of extreme data
But as for the “MasVnrArea” and “GarageYrBlt”, they are the detail that describe certain function related to the categorial variables, because they have the same number of missing value with “MasVnrType” and “GarageType”. And we have already assumed that if there are missing values in such columns, which means there are no such equipment in the house. So we will fill “0” in these two continuous columns

10. check if we still have null values

<img width="722" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/1c558c7d-903b-4d56-b289-a08a2ea79430">

<img width="722" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/37352a1e-71db-42cd-8d7d-51277007eda4">

11. Add some features
Having sold real estate myself, I know that square footage and condition are highly correlated with house prices
So I would like to add two features, they are total area and total quality of house respectively. 
Total area = Basement area + 1st floor area + 2nd floor
Total House Quality = Rates the overall material and finish of the house + Rates the overall condition of the house

<img width="778" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/668fda5c-f65c-405a-866e-fef1730a497f">


13. Label Encoding
Turning Categorical values to numeric variables by using the package from sklearn

<img width="485" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/13320503-8524-4692-b80c-f2a327e2a42d">


15. Handling outlier of numerical columns
As we can obverse in the picture, there are some outliers in various columns. 
The density shows clearly.

<img width="272" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/eb0d255e-71c9-437c-9ddc-adede53f56db">

<img width="380" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/57612b55-75ee-4abe-969b-a1739e20477a">

17. Check the skew of all numerical features
The skewness of all numerical features show that there are large number of outliers

<img width="162" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/ba035349-11f2-4317-844d-d98c8b8c3998">

<img width="191" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/5832ea5f-10ef-4d1f-99c3-e447c81bc19c">

19. Capping all the outliers
We would detect outliers with IQR
And then capping outliers of numerical features by using lower bound (Q1–1.5*IQR) and upper bound (Q3+1.5*IQR)

<img width="910" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/8c479d3a-5dfc-474a-af8c-cc1b7e2a0a6c">

21. Check the skew of all numerical features after capping
The skewness of all numerical features became smaller, which means that the outliers are deleted, and the data is more of a normal distribution
The scatter diagram shows the same deduction

<img width="447" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/de085c85-50e4-425e-b3c0-3c2cd7f791bd">

23. Handling outlier of categorical columns
As we can obverse in the bar plots , there are also some outliers in categorical columns.

<img width="604" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/da8147d8-267f-4aa8-bb5b-4e50df8b1464">

25. Feature Engineering – Numerical Feature Selection
We would use correlation to select the numerical features.
So, we use heatmap to visualize the correlation.

<img width="538" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/7867117b-7821-41cd-9fcf-7b14d962366f">

27. Feature Engineering – Numerical Feature Selection
Here is the detailed correlation to target variable(“Sale Price”)
So we can pick those features that have at least an absolute value of 0.2 or higher correlation with the Sale Price

<img width="305" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/07a3142f-bf29-4d7f-b30c-9020e3195aee">

<img width="230" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/96305270-a287-4d1a-b6c3-5f688b104692">

29. Feature Engineering – Categorical Feature Selection
As Correlation Analysis can only be used to select numerical features, and there are both categorical Feature and numerical features in our dataset, so it may be better to use another method to select the feature
So we can use Embedded Method to identify the importance of different feature, since tree-based algorithms are naturally supportive to analysis categorical feature. 
Therefore, we choose Random Forest to do the feature selection

<img width="586" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/ac3ebcb0-cbb6-4529-a324-5e3754ea4227">

31. Feature Engineering – Categorical Feature Selection
We would select the feature according to “feature_importances_” function. 
Importance shows that there are some features have no contributions to the model, we can therefore drop such features to avoid overfitting.

<img width="286" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/7532de62-dc5a-4a91-b112-0a371c92af9b">

33. Check Performance
We can try to fit the prepared data to models and see the accuracy. 
We would like to check the performance in various models, like Linear Regression, Ridge, Lasso regression, Random Forest Regressor, Gradient Boosting Regressor, support vector regression, Linear Support Vector Regression, Elastic net, Bayesian ridge regression, Kernel ridge regression(KRR)

<img width="493" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/9d0df0c0-64e4-4e2d-b33e-7a80a2773f8f">

As can be seen from the figure on the right, all models performed well. Almost all models had RMSE below 0.25, indicating that our data was well processed

<img width="475" alt="image" src="https://github.com/Jimmynpt/House-price-exercise/assets/83577706/6291be7c-7a7c-40dd-916c-6109ec4fe7f6">
