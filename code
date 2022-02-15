# covid19_vaccines_analysis
#future skills prime project (COVID 19 VACCINE ANALYSIS)
#READING DATASET
import numpy as np
import pandas as pds
import matplotlib.pyplot as plt
import seaborn as sns
xdf = pds.read_csv("country_vaccinations.csv")
xdf.head()

   #EXPLORING THE DATA

xdf.describe()
    #analyse vaccines taken by the country 
pds.to_datetime(xdf.date)
xdf.country.value_counts()
  #vaccines available in the dataset
xdf.vaccines.value_counts()
df = xdf[["vaccines", "country"]]
df.head() 

#see how many countries are taking each of the vaccines mentioned in this data
dict_vac = {}
for i in df.vaccines.unique():
  dict_vac[i] = [df["country"][j] for j in df[df["vaccines"]==i].index]

vaccines = {}
for key, value in dict_vac.items():
  vaccines[key] = set(value)
for i, j in vaccines.items():
  print(f"{i}:>>{j}") 
  
  #visualize this data to have a look at what combination of vaccines every country is using 
  
import plotly.express as px
import plotly.offline as py

vaccine_map = px.choropleth(xdf, locations = 'iso_code', color = 'vaccines')
vaccine_map.update_layout(height=300, margin={"r":0,"t":0,"l":0,"b":0})
vaccine_map.show()
