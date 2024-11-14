### Developed by: Koduru Sanath Kumar Reddy

### Register no: 212221240024

### Date: 
 
# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA


### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on electricity production data.
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
~~~
import pandas as pd
df = pd.read_csv('Electric_Production.csv')
print(df.head())

# Apply log transformation
df['Log_Production'] = np.log(df['IPG2211A2N'])
print(df.head())
df['Diff_Production'] = df['IPG2211A2N'].diff()
print(df.head())
df['DATE'] = pd.to_datetime(df['DATE']) # Parse the 'DATE' column as datetime objects
df.set_index('DATE', inplace=True) # Set the 'DATE' column as the index

# Seasonal decomposition, explicitly setting the period
decomposition = sm.tsa.seasonal_decompose(df['IPG2211A2N'].dropna(), model='additive', period=12) # Assuming monthly data, set period to 12
df['Seasonal_Component'] = decomposition.seasonal
print(df.head())

# Plot the components
plt.figure(figsize=(12, 8))
plt.subplot(3, 1, 1)
plt.plot(df['IPG2211A2N'], label='Original Series')
plt.legend()
plt.subplot(3, 1, 2)
plt.plot(df['Seasonal_Component'], label='Seasonal Component', color='orange')
plt.legend()
plt.subplot(3, 1, 3)
plt.plot(df['IPG2211A2N'] - df['Seasonal_Component'], label='Deseasonalized Series', color='green')
plt.legend()
plt.tight_layout()
plt.show()
~~~
### OUTPUT:


REGULAR DIFFERENCING:
<img width="646" alt="image" src="https://github.com/user-attachments/assets/d21db9ce-e649-4005-90ae-5053dcf0af40">




SEASONAL ADJUSTMENT:


<img width="646" alt="image" src="https://github.com/user-attachments/assets/f2475f50-ffc6-4416-a8db-722a8d85b345">




LOG TRANSFORMATION:


<img width="624" alt="image" src="https://github.com/user-attachments/assets/81d88f6f-aef9-4e32-821e-3650f3bf9f48">




### RESULT:
Thus wthe python code for the conversion of non stationary to stationary data on electricity production
data.
