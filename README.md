# Ex.No: 01A PLOT A TIME SERIES DATA
## Date: 21.04.2026 
## AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
## Software Required:
Google colab
## Dataset:
Stock Market Dataset
## ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
## PROGRAM:

```python
from matplotlib import pyplot as plt
import pandas as pd

df=pd.read_csv("/content/A.csv")

df.head()

df['Date'] = pd.to_datetime(df['Date'])

df.dtypes

df.set_index('Date', inplace=True)

df_resampled = df['Volume'].resample('D').interpolate()

df_resampled.plot(kind='line', label='stock market', color='red')

plt.figure(figsize=(10,5))
plt.plot(df['Date'], df['Volume'], linewidth=2)

plt.xlabel('Date')
plt.ylabel('Volume')
plt.title(' Stock Volume Over Time')

plt.xticks(rotation=45)
plt.grid(True)

plt.tight_layout()
plt.show()

```
## OUTPUT:

<img width="1357" height="632" alt="image" src="https://github.com/user-attachments/assets/94cf6980-4b25-4647-ab9e-4898d1245095" />

## RESULT:
Thus we have created the python code for plotting the time series of given data.
