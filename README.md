# 📊Canada Supplement Sales Dashboard
### The project consists of two parts:
+ First Part Python Code
  + EDA, Preprocessing and Basic Vizualization done in Python.
+ Second Part Power Bi Dashboard
  + Second part (Dashboard) is created using Power Bi.
---------
### Overview
This dataset contains weekly sales data for a variety of health and wellness supplements from January 2020 to April 2025. The data includes products in categories like Protein, Vitamins, Omega, and Amino Acids, among others, and covers multiple e-commerce platforms such as Amazon, Walmart, and iHerb. The dataset also tracks sales in several locations including the USA, UK, and Canada but I only analysis and vizualise Supplement sales in Canada from 2020 to 2025.

I have done analysis with Python and visuzalition with Power Bi.

<b> Dataset source: https://www.kaggle.com/datasets/zahidmughal2343/supplement-sales-data/data </b>
### Objectives: 
+ Which platform has sold the most supplement product in Canada.
+ Which supplement product is sold the most.
+ Which supplement products are sold by Walmart the most.
+ Which supplement products are sold by Amazon the most.
+ Which supplement products are sold by iHerb the most.
+ Impact of promotions on Sales.
+ Time series analysis to find more patterns and trends.


### Power Bi Dashboard
![Power Bi Dashboard](https://github.com/user-attachments/assets/3798c0d7-3c5d-4caa-a08d-16ba7d79ad77)

### Python Code
--------------------

```
import pandas as pd
import numpy as np
import seaborn as sns
from bokeh.plotting import figure,show,output_notebook
from bokeh.palettes import Category10_3

output_notebook()
```

```
df = pd.read_csv('Supplement_sales.csv')
```
![image](https://github.com/user-attachments/assets/44aadf3f-88f2-48af-a227-7ff1b81a872c)

```
df.shape
```
(4384, 10)

```
df.info()
```

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 4384 entries, 0 to 4383
Data columns (total 10 columns):
 #   Column          Non-Null Count  Dtype  
---  ------          --------------  -----  
 0   Date            4384 non-null   object 
 1   Product Name    4384 non-null   object 
 2   Category        4384 non-null   object 
 3   Units Sold      4384 non-null   int64  
 4   Price           4384 non-null   float64
 5   Revenue         4384 non-null   float64
 6   Discount        4384 non-null   float64
 7   Units Returned  4384 non-null   int64  
 8   Location        4384 non-null   object 
 9   Platform        4384 non-null   object 
dtypes: float64(3), int64(2), object(5)
memory usage: 342.6+ KB
