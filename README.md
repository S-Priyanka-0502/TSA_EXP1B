# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
## Import the necessary Packages
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
## Load the dataset
```python
data=pd.read_csv('/content/petrol_price.csv')
```
## Plot the data without conversion
```python
plt.figure(figsize=(10,5))
X=data['date']
y=data['Tamil Nadu']
plt.xlabel('Date')
plt.ylabel('Petrol Price')
plt.plot(X,y)
```
## Regular Differencing
```python
data['diff']=data['Tamil Nadu'].diff()
plt.figure(figsize=(10,5))
x=data['date']
y=data['diff']
plt.xlabel('Date')
plt.ylabel('Petrol Price')
plt.plot(x,y)
```
## Seasonal Adjustment
```python
data3=data
data3['seasonal']=data3['Tamil Nadu']-data3['Tamil Nadu'].rolling(window=3).mean()
plt.figure(figsize=(10,5))
x=data3['date']
y=data3['seasonal']
plt.xlabel('Date')
plt.ylabel('Petrol Price')
plt.plot(x,y)
```
## Log Transformation
```python
data2=data
data2['log']=np.log(data2['Tamil Nadu']).dropna()
plt.figure(figsize=(10,5))
x=data2['date']
y=data2['log']
plt.xlabel('Date')
plt.ylabel('Petrol Price')
plt.plot(x,y)
```

### OUTPUT:

WITHOUT CONVERSION:
![image](https://github.com/user-attachments/assets/0f6cac38-abf1-4fc8-9a83-54c67e22ad16)

REGULAR DIFFERENCING:
![image](https://github.com/user-attachments/assets/63917bc4-d982-4f57-a77d-63d851314a75)

SEASONAL ADJUSTMENT:
![image](https://github.com/user-attachments/assets/2938f359-941b-4371-ba9f-512772bdb23a)

LOG TRANSFORMATION:
![image](https://github.com/user-attachments/assets/d3710f71-69ac-4f21-b89e-0e76c1823479)


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on petrol price
data.
