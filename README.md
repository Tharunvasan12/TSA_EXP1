## Ex.No: 01A PLOT A TIME SERIES DATA
## Name:Tharunish vasan T
## Reg no:212224240274
## Date:26/10/26
## AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity /temperature.

## ALGORITHM:
Import the required packages like pandas and matplot


Read the dataset using the pandas


Calculate the mean for the respective column.



Plot the data according to need and can be altered monthly, or yearly.



Display the graph.
## PROGRAM:
```
import pandas as pd
import tkinter as tk
from tkinter import filedialog
root = tk.Tk()
root.withdraw()
root.attributes("-topmost", True)
file_path = filedialog.askopenfilename(
    title="Select AirPassengers.csv",
    filetypes=[("CSV files", "*.csv")]
)
root.destroy()
df = pd.read_csv(file_path)
print(df.head())


import matplotlib.pyplot as plt
df['Month'] = pd.to_datetime(df['Month'])
df = df.set_index('Month')
df_resampled = df['#Passengers'].resample('D').interpolate()
df_resampled.plot(color='black', figsize=(12, 5))
plt.title('Time Series Plot of Number of Passengers Each Day')
plt.xlabel('Day')
plt.ylabel('Number of Passengers')
plt.grid(True)
plt.show()
```

## OUTPUT:
<img width="437" height="177" alt="Ts-1" src="https://github.com/user-attachments/assets/ec2d240d-6ce8-47ae-9fd7-984b8a30f5d2" />
<img width="794" height="351" alt="ts-2" src="https://github.com/user-attachments/assets/12c4ea9d-4339-4d30-b406-517e2bb38092" />


## RESULT:
Thus we have created the python code for plotting the time series of given data.
