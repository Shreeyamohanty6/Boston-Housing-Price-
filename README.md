# Boston-Housing-Price-
Boston Housing Price Prediction 

- You can downlod the data set provided as the housing.csv file.
- Change the path int his line of code.
  housing = pd.read_csv('C:/Users/shree/my_env/housing.csv', sep='\s+',header=None, names=column_names)
  
1.Dataset and its features 

The Boston Housing Dataset was provided in the assignment which has the following features:-

CRIM - per capita crime rate by town
ZN - proportion of residential land zoned for lots over 25,000 sq.ft.
INDUS - proportion of non-retail business acres per town.
CHAS - Charles River dummy variable (1 if tract bounds river; 0 otherwise)
NOX - nitric oxides concentration (parts per 10 million)
RM - average number of rooms per dwelling
AGE - proportion of owner-occupied units built prior to 1940
DIS - weighted distances to five Boston employment centers
RAD - index of accessibility to radial highways
TAX - full-value property-tax rate per $10,000
PTRATIO - pupil-teacher ratio by town
B - 1000(Bk - 0.63)^2 where Bk is the proportion of blacks by town
LSTAT - % lower status of the population
MEDV - Median value of owner-occupied homes in $1000's

The CSV file provided was not having column names so using pandas column names were added to the CSV file having the dataset.

column_names = ['CRIM', 'ZN', 'INDUS', 'CHAS', 'NOX', 'RM', 'AGE', 'DIS', 'RAD', 'TAX', 'PTRATIO', 'B', 'LSTAT', 'MEDV']

housing = pd.read_csv('C:/Users/shree/my_env/housing.csv', sep='\s+', header=None, names=column_names)

2. Data Preprocessing 

We plot graphs for all the features to get insights and visualize the features



Fig :- Graphs of some features

Train test data was splitted.
 
train_set, test_set = split_train_test(housing, 0.2)

.The correlation of various features with respect to the median value of the house was calculated to find the most important feature that is influencing to the median value of the house

            
 MEDV       1.000000
RM         0.671189
ZN         0.400447
B          0.340064
DIS        0.272786
CHAS       0.122868
CRIM      -0.395833
AGE       -0.407816
RAD       -0.408476
NOX       -0.448645
TAX       -0.483387
INDUS     -0.494745
PTRATIO   -0.526972
LSTAT     -0.740158

       Correlation coefficient of various features.


A graph was plotted between MEDV and the feature RM which has the highest correlation coefficient, to find out the type of relation that exist between them.
     

Fig :- MEDV vs RM

3. Model Training and Evaluation Results 

Linear Regression was used to evaluate the training set and we got an RMSE (Root Mean Squared Error) of 4.62317944753998

  
 

To experiment and minimise the error we tried our training dataset on another model i.e Decision Tree and we got an RMSE of 0.0. 

This indicate that the model is an overfit . So we tried an advanced version of Decision Tree i.e Random Forest which uses number of decision tree on the dataset. 

4. Interpretation of the Model’s Performance

We plot a graph between actual and predicted median values of the houses on the test set .




We are satisfied with the results and stop here.

Findings:-

-> Random Forest is an appropriate model for housing price prediction.
-> For the Boston Dataset Random Forest works fine with a RMSE of 3.6 and a MAPE(Mean Absolute Percentage Error) of 10.28%. 

Challenges:-

-> There doesn’t exist a strong correlation between the median values of the houses and the other features of the dataset.


