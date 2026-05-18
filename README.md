# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 15/5/26
### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
### Name: Navinkumar V
### Reg no: 212223230141
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('/content/gold_rate_history.csv')

decomposition = seasonal_decompose(data['Pure Gold (24 k)'], model='additive',period=12)

plt.subplot(411)
plt.plot(data['Pure Gold (24 k)'], label='gold rate')
plt.legend(loc='upper left')
plt.title('gold rate')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.xlim(0, 250)
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.xlim(0, 250)
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()

```
### OUTPUT:
<img width="524" height="137" alt="image" src="https://github.com/user-attachments/assets/11563fe1-217d-4aec-97af-faa61489dddb" />

<img width="519" height="131" alt="image" src="https://github.com/user-attachments/assets/25f0bd57-5c60-4b04-99ae-b62b976d41d8" />

<img width="517" height="130" alt="image" src="https://github.com/user-attachments/assets/87ced36d-298c-4855-9baf-b4e465ef488a" />

<img width="580" height="127" alt="image" src="https://github.com/user-attachments/assets/643de6a8-5e57-4db6-a2c5-87517f79746d" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
