# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on electricity production data.
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
data=pd.read_csv("/content/electricityproduction.csv",parse_dates=['Month'],index_col='Month')
data.head()
data['shifted_value']=passengers['#production'].shift(1)
data['difference_value']=passengers['#production']-passengers['shifted_value']
data.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')


data=pd.DataFrame(data)
result=seasonal_decompose(passengers['#production'],model='additive',period=1)
seasonal=result.seasonal
data['Seasonal_value']=passengers['#production']-seasonal
data.dropna(inplace=True)
print(data)
data.plot(kind='line')



data.dropna(inplace=True)
x=data.index # Use .index to access the dates
y=data['#production']
data_log=np.log(data['#production'])
X=data.index # Use .index to access the dates
Y=data_log
import matplotlib.pyplot as plt
plt.plot(x,y)
plt.xlabel('Original Data')
plt.plot(X,Y)
plt.xlabel('Log- Transformed data')



### OUTPUT:


REGULAR DIFFERENCING:


<img width="498" alt="image" src="https://ithub.com/user-attachments/assets/296f8873-2b7f-4e46-af1b-944a078b02ef">


SEASONAL ADJUSTMENT:


<img width="498" alt="image" src="https://ithub.com/user-attachments/assets/463b29a6-f302-4c15-9c8e-bc6481c87886">



LOG TRANSFORMATION:


<img width="494" alt="image" src="https://github.com/user-attachments/assets/d557649e-c274-47c2-b90e-f6b435769668">




### RESULT:
Thus wthe python code for the conversion of non stationary to stationary data on electricity production
data.
