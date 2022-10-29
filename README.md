# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

## Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM
#### STEP 1
Read the given Data
#### STEP 2
Clean the Data Set using Data Cleaning Process
#### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
#### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
'''
Developed By: RAJESHKANNAN M
Register No: 212221230081
'''
import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#5.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#6.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#7.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#8.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
```

# OUTPUT

![1](https://user-images.githubusercontent.com/93901857/198822746-d17cc32c-23f7-4b2d-8041-1596b1590b76.jpg)
![2](https://user-images.githubusercontent.com/93901857/198822751-8b533602-6dce-47e1-af2b-5bfdedd25d46.jpg)
![3](https://user-images.githubusercontent.com/93901857/198822753-421dce3c-0fc9-499d-b4de-f8c6112addbf.jpg)
![4](https://user-images.githubusercontent.com/93901857/198822755-aa740b1a-e4e9-42bd-906b-fb102f75f9d8.jpg)
![5](https://user-images.githubusercontent.com/93901857/198822758-15ae3c4f-cf3c-4b47-85c5-eea3f98dffdd.jpg)
![6](https://user-images.githubusercontent.com/93901857/198822760-c1577026-a46e-4b33-bdc0-597823ece6fa.jpg)
![7](https://user-images.githubusercontent.com/93901857/198822763-2e3fdf76-b4dd-4a4a-b856-8b982974ca57.jpg)
![8](https://user-images.githubusercontent.com/93901857/198822764-c61808e1-6500-47d8-b4bf-72e9d9d7bdf7.jpg)
![9](https://user-images.githubusercontent.com/93901857/198822767-f909cf2c-adf9-45f2-8445-a4eb828b2f75.jpg)
![10](https://user-images.githubusercontent.com/93901857/198822771-1a52efc7-107a-4788-b2d1-304d851fdc5b.jpg)
![11](https://user-images.githubusercontent.com/93901857/198822772-037693ac-859a-49dc-a797-ed29ed63c57c.jpg)
![12](https://user-images.githubusercontent.com/93901857/198822794-abd97f63-7b0c-4bae-bd25-7ef39e500d44.jpg)
![13](https://user-images.githubusercontent.com/93901857/198822795-bf9d192d-5327-479b-b627-a24f55ba031e.jpg)

#### RESULT:
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.