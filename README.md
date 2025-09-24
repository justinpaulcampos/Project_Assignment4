# Project Assignment 4

### Number 1
####Initialize 
import pandas
``` python
import pandas as pd
```
read Excel
``` python
df = pd.read_excel('board2.xlsx')
```
#### a. Filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as Instrumentation and hometown Luzon
Create the dataframe for "Intru" table, using loc to limit rows on electronics score, track, and hometown, and with columns only containing the name, GEAS, and electronics.
``` python
Instru = df.loc[(df['Hometown'] == 'Luzon')&(df['Electronics']>70)&(df['Track'] == 'Instrumentation'),['Name','GEAS','Electronics']]
Instru
```
#### b. Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is constant as Mindanao and gender Female
Add an extra collumn for average of the four values of track, electronics, GEAS, and communication. 
``` python
df["Average"] = df[["Math", "Electronics", "GEAS", "Communication"]].mean(axis=1)
```
#Create an dataframe that uses loc to limit rows based on the Average and also limit the collumns to only have "Name","Track","Electronics","Average"
``` python
Mindy = df.loc[(df['Hometown'] == 'Mindanao')&(df["Average"]>=55),['Name','Track','Electronics','Average']]
Mindy
```

### Numbeer 2
import matplotlib
``` python
import matplotlib.pyplot as plt
```
size the plot
``` python
plt.figure(figsize = (15,4))
```
plot a bar graph from each of the track, gender, adn hometown with average being the y axis
``` python
plt.bar(df['Track'],df['Average'])
plt.bar(df['Gender'],df['Average'])
plt.bar(df['Hometown'],df['Average'])
```
