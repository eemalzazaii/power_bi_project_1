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
![image](https://github.com/user-attachments/assets/433e1a62-961c-4c5f-a8f7-383e40515d8c)
![image](https://github.com/user-attachments/assets/caaed6be-b4ae-48ca-af40-4d723ea4041d)
![image](https://github.com/user-attachments/assets/fd0a48b7-d8dc-42a7-84d4-f7898921184a)
![image](https://github.com/user-attachments/assets/b46732a8-d6cf-4ba5-89be-78a0824a5d9b)

### Preprocessing
```
is_null = df.isnull().sum()
print('Null value:',is_null)
is_duplacted = df.duplicated().sum()
print("Duplicated value",is_duplacted)

```
![image](https://github.com/user-attachments/assets/accd31b9-ec53-45cb-b0ff-fbecc542dde9)

```
sns.heatmap(df.isnull())
```

![image](https://github.com/user-attachments/assets/e9175c6f-dfa0-446e-9ae9-1c2144b8fa5d)

```
df = df.rename(columns={'Date':'Date','Product Name':'Product_name','Category':'Category','Units Sold':'Units_sold','Revenue':'Revenue','Disocunt':'Discount','Units Returned':'Units_returned',
                        'Location':'Location','Platform':'Platform'})
Canada_sup_sale = df.loc[df['Location'] == 'Canada']
chart1 = figure(title = 'Sales per company',x_axis_label= 'Company',y_axis_label = 'Units Sold',x_range = platforms,height=400, 
           width=300)
chart2 = figure(title = 'Most Popular Supplements in Canada (By Sales)',x_axis_label = 'Supplements',y_axis_label = 'Units Sold',x_range = product1, width = 1400, height= 600)
chart1.vbar(x = platforms, top = units_sold, color = Category10_3 ,width=0.2)
print('iHerb has the highest supplement sales in Canada')
chart2.vbar(x = product1, top = units_sold, width = 0.5)
show(chart2)
```

### The data is now preprocessed and ready to be exported to Power Bi for building Dashboard

