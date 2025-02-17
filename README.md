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
###  Regular Differencing:
```
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
data=pd.read_csv("/content/AirPassengers.csv",parse_dates=['Month'],index_col='Month')
data.head()
passengers['shifted_value']=passengers['#Passengers'].shift(1)
passengers['difference_value']=passengers['#Passengers']-passengers['shifted_value']
passengers.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')
```
### Seasonal Adjustment
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
data=pd.read_csv("/content/AirPassengers.csv",parse_dates=['Month'],index_col='Month')
passengers=pd.DataFrame(data)
result=seasonal_decompose(passengers['#Passengers'],model='additive',period=1)
seasonal=result.seasonal
passengers['Seasonal_value']=passengers['#Passengers']-seasonal
passengers.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')
```
### Log Transformation:
```
import numpy as np
import pandas as pd
data= pd.read_csv('AirPassengers.csv')
data.head()
data.dropna(inplace=True)
x=data['Month']
y=data['#Passengers']
data_log=np.log(data['#Passengers'])
X=data['Month']
Y=data_log
import matplotlib.pyplot as plt
plt.plot(x,y)
plt.xlabel('Original Data')
plt.plot(X,Y)
plt.xlabel('Log- Transformed data')
```
### OUTPUT:
![time1](https://github.com/Vishwarathinam/TSA_EXP1B/assets/95266350/97089677-5407-4094-8490-77622071d216)


REGULAR DIFFERENCING:

![time2](https://github.com/Vishwarathinam/TSA_EXP1B/assets/95266350/6855ac4a-c7c8-4967-ab63-201ced757dd4)


SEASONAL ADJUSTMENT:

![time3](https://github.com/Vishwarathinam/TSA_EXP1B/assets/95266350/ffaec379-ff31-475c-a83c-8463475df1ce)


LOG TRANSFORMATION:

![time4](https://github.com/Vishwarathinam/TSA_EXP1B/assets/95266350/88900685-cdc9-4f8b-aa8e-4bbc8aa7bf0c)



### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
