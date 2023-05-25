# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset

2.check for null values

3.Import kmeans and fit it to the dataset

4.Plot the graph using elbow method

5.Print the predicted array

6.Plot the customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Neha.MA
RegisterNumber:  212220040100
*/

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[] #within cluster sum of square
for i in range(1,11):
  kmeans = KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
  plt.plot(range(1,11),wcss)
plt.xlabel("No of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
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
plt.title("customer segments")
```

## Output:

## Datahead

![image](https://github.com/neha074/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113016903/510ba1f3-df4b-4f92-81a6-93952d1db15f)

## Info

![image](https://github.com/neha074/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113016903/ead3d8f3-48ee-4915-8b1b-4e7f08126124)


## Total Rows

![image](https://github.com/neha074/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113016903/6db3c7a1-f9a2-4576-8463-fa9eae083b80)

## Plot for Elbow Method

![image](https://github.com/neha074/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113016903/0f83bfa8-b6ed-49a3-8248-1addc818c837)

## K-Means Clustering

![image](https://github.com/neha074/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113016903/8c1af17f-b773-42c3-bc89-f280fcba3dfb)

## y_Pred

![image](https://github.com/neha074/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113016903/7265c909-80b3-4835-83a7-2787be129538)


## Plot for customer Segements

![image](https://github.com/neha074/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113016903/3e8fcb3b-03f2-4475-afd3-256a516b8e72)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
