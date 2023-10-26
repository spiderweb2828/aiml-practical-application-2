# aiml-practical-application-2

Link to Jupyter Notebook can be found at https://github.com/spiderweb2828/aiml-practical-application-2/blob/main/prompt_II.ipynb

## Data Clean up: In order to find the required data clean up, lets find the unique values of each column by executing the command data.apply(lambda col: col.unique()) on the dataframe "data"

Models considered: Sequential Feature Selector (SFS) and Ridge Regression and Transformed Target Ridge Regression

Data Clean Up & Preparation:
* Removed the rows with missing values
* Removed the rows with "nan" in columns
* Since title_status and condition columns have a value called "salvage, to differentiate, replaced "salvage" with "condition_salvage" in condition column
* Using StandardScaler library, scaled the data to normalize the data in columns "price", "odometer"
* Since regression works with numeric values, converted categorical values to numeric values using OneHotEncoder library

Model 1: Sequential Feature Selector (SFS) with Linear Regression
----------------------------------
* Used Sequential Feature Selector (SFS) with Linear Regression to find the best features that can be used to predict the price of the car
Observations: condition with status fair and like_new along with year has significant impact on price of the car.

Model 2: Ridge Regression
----------------------------------
* Used Ridge Regression to find the best features that can be used to predict the price of the car
* Ran the model with different alpha values to find the best alpha value

Observations: price of the car is sensitive to title_status, condition and odometer .

[ridge-coefs.csv](results%2Fridge-coefs.csv)

Model 3: Transformed Target Ridge Regression
----------------------------------
* Used Transformed Target Ridge Regression to cross-check the best features that can be used to predict the price of the car

![permutation-importance.png](results%2Fpermutation-importance.png)

Results: Title status, Condition along with Odometer has significant impact on price of the car.