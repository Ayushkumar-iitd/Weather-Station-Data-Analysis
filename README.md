# Weather-Station-Data-Analysis
Analyzed a file of 9000 data entries of a weather station using python pandas and matplotlib.
Open the Weather project folder on your VS code and then run the code. It will answer all questions asked in comments.

Code:
    import pandas as pd
    data=pd.read_csv("file.csv")
    #print(data)
    
    #Unique 'wind speed' values in data 
    print(data['Wind Speed_km/h'].unique())
    print(data['Wind Speed_km/h'].nunique())
    
    #No. of times when weather is exactly clear
    print(data.Weather.value_counts())
    print(data[data.Weather=='Clear'])
    
    #No. of times when wind speed was exactly 4km/hr
    print(data[data['Wind Speed_km/h']==4])
    
    #No. of Null values in data 
    print(data.isnull().sum())
    
    #Rename column 'Weather' to 'Weather Condition'
    print(data.rename(columns={'Weather':'Weather Condition'},inplace=True))
    
    #Mean value of Visibility
    print(data.Visibility_km.mean())
    
    #St. deviation of pressure
    print(data.Press_kPa.std())
    
    #Variance of Relative Humidity
    print(data['Rel Hum_%'].var())
    
    #Find all the readings when data contains 'Snow'
    print(data[data['Weather Condition'].str.contains('Snow')])
    
    #Instances when Wind speed >24 and visibility is 25
    print(data[(data['Wind Speed_km/h']>24) & (data['Visibility_km']==25)])
