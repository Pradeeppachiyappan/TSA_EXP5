# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date : 24-03-2024 

### AIM :
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM :
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
Name : Pradeep Raj P
Reg No : 212222240073
```
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Load the temperature data
data = pd.read_csv('AirPassengers.csv')

# Assuming your data contains two columns: 'date' and 'value'
data['date'] = pd.to_datetime(data['date'])

# Set the 'date' column as the index
data.set_index('date', inplace=True)

# Perform time series decomposition
result = seasonal_decompose(data, model='multiplicative',period=12)

# Plot the original time series
plt.figure(figsize=(12, 6))
plt.subplot(4, 1, 1)
plt.plot(data['value'], label='Original',color='red')
plt.title('Original Time Series')
plt.legend()

# Plot the trend component
plt.subplot(4, 1, 2)
plt.plot(result.trend, label='Trend', color='red')
plt.title('Trend Component')
plt.legend()

# Plot the seasonal component
plt.subplot(4, 1, 3)
plt.plot(result.seasonal, label='Seasonal', color='red')
plt.title('Seasonal Component')
plt.legend()

# Plot the residual component
plt.subplot(4, 1, 4)
plt.plot(result.resid, label='Residual', color='red')
plt.title('Residual Component')
plt.legend()

plt.tight_layout()
plt.show()
```
### OUTPUT:
![image](https://github.com/Pradeeppachiyappan/TSA_EXP5/assets/118707347/98e9bb82-5bbd-4ee9-bf44-2d343c4efc07)


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
