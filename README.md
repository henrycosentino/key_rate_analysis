## Project Overview
- The purpose of this project was to create a machine learning model that utilizes macroeconomic variables as inputs to accurately predict 1-year and 10-year U.S. Treasury yields.
  
## Steps Involved:
- Extract data from the Bloomberg Terminal using the API and import it into Excel
- Load data from Excel into Python
- Clean data frames
- Impute monthly and quarterly macroeconomic data
  - Impute missing values using a compound and linear growth rate method to disaggregate data to a lower frequency.
- Impute daily macroeconomic data
  - The imputation method assumed a simple linear relationship and was primarily used to clean up one-off daily missing values.
- A period was defined
  - End: 2024-07-25.
  - Start: 2004-11-05.
  - The start date was constrained by data availability.
- Scaling the data
  - Scale the data using the standardization method provided by sklearn’s StandardScaler.
- Shifting the data and finding relationships
  - Shift the data by various intervals. Specifically, the target variables were shifted backward to align with previous data. Analyze the data through correlation matrices and plot the strongest correlations between target variables and predictors.
- Machine learning
  - Construct a loop for each target variable to train a model on a specific shifted dataset. For example, if the model is designed to predict interest rates one year from now, the data would be shifted by roughly 250 steps (the data is set to trading/business days). The loop iterates over a range of steps, trains a model for each step, and calculates key statistics for each model.
- Visualizing model accuracy
  - Visualize the statistics generated from each step to determine the time periods during which the model is most effective at predicting interest rates. Root Mean Square Error (RMSE) and Mean Absolute Error (MAE) values are used to demonstrate the predictive accuracy of each model.
