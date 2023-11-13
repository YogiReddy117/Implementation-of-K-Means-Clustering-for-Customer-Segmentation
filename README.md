# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries,read the data set.find the number of null data.
2. Find the number of null data.
3. Import sklearn library.
4. Find y predict and plot the graph.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Palleri Yogi
RegisterNumber: 212220040108
*/

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range (1,11):
    kmeans=KMeans(n_clusters = i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow matter")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segmets")
```

## Output:
data.head():

![image](https://github.com/YogiReddy117/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123739437/1aba3124-2e10-4c44-8629-f38f1e185f92)

data.info():

![image](https://github.com/YogiReddy117/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123739437/cfb7579e-ad15-4caf-aa34-4e3450cff8e9)

data.isnull().sum():

![image](https://github.com/YogiReddy117/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123739437/520bd801-022f-4804-a0ce-8b7b429fd1b7)

Elbow method graph:

![image](https://github.com/YogiReddy117/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123739437/f60738d0-520b-477a-8faa-b8551c660e2d)

KMeans clusters:

![image](https://github.com/YogiReddy117/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123739437/42052fb0-ed9c-41b0-b4fa-b922344c1966)

Array value of Y:

![image](https://github.com/YogiReddy117/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123739437/41a48a4f-6b6f-4aec-b119-6379d42ca5d7)

Customers Segments graph:

![image](https://github.com/YogiReddy117/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123739437/8490b492-42cd-495b-b0c5-302d5396a315)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
