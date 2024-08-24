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
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
passengers=pd.read_csv("/content/AirPassengers .csv",parse_dates=['Month'],index_col='Month')
passengers.head()
passengers['shifted_value']=passengers['#Passengers'].shift(1)
passengers['difference_value']=passengers['#Passengers']-passengers['shifted_value']
passengers.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')


passengers=pd.DataFrame(data)
result=seasonal_decompose(passengers['#Passengers'],model='additive',period=1)
seasonal=result.seasonal
passengers['Seasonal_value']=passengers['#Passengers']-seasonal
passengers.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')



passengers.dropna(inplace=True)
x=passengers.index # Use .index to access the dates
y=passengers['#Passengers']
data_log=np.log(data['#Passengers'])
X=passengers.index # Use .index to access the dates
Y=data_log
import matplotlib.pyplot as plt
plt.plot(x,y)
plt.xlabel('Original Data')
plt.plot(X,Y)
plt.xlabel('Log- Transformed data')



### OUTPUT:


REGULAR DIFFERENCING:


SEASONAL ADJUSTMENT:
<img width="498" alt="image" src="https://github.com/user-attachments/assets/463b29a6-f302-4c15-9c8e-bc6481c87886">



LOG TRANSFORMATION:
![Uploading image.png…]()



### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
