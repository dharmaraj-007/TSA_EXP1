# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.

# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.

# PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("train.csv")
df['date'] = pd.to_datetime(df['date'])
df.set_index('date', inplace=True)
df['num_sold'].fillna(0, inplace=True)
daily_sales = df['num_sold'].resample('D').sum()
plt.figure(figsize=(12, 6))
plt.plot(daily_sales.index, daily_sales, label='Total Units Sold', color='blue')
plt.title('Total Products Sold Over Time')
plt.xlabel('Date')
plt.ylabel('Number of Products Sold')
plt.grid(True)
plt.legend()
plt.show()
```

# OUTPUT:
![image](https://github.com/user-attachments/assets/b789c961-379e-49ea-854d-35c1ae1a01bc)

# RESULT:
Thus we have created the python code for plotting the time series of given data.
