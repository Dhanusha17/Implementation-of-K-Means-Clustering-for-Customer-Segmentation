# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.
 
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program.
 
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:DHANUSHA K 
RegisterNumber:212223040034  
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
## Dataset
![326072454-40dd2c9b-450f-496f-a5ff-7c57ad8dd730](https://github.com/Dhanusha17/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/151549957/87a6db38-b3ba-4607-bd8c-cb8b2e43027e)
##  Dataset information:
![326072684-0f1c75a3-365b-4160-8b96-1a2f82706d4d](https://github.com/Dhanusha17/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/151549957/9a9f4c7b-cebb-44d0-9d21-543bca0ac56f)

## Elbow method graph (wcss vs each iteration):
![326072756-9139f4a7-3479-4c4d-a700-495c6b560c05](https://github.com/Dhanusha17/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/151549957/8cf354f7-abe3-4000-b0a0-575a7237089b)

## Cluster represnting customer segments-graph:
![326072880-303c8219-01fc-4949-846f-6b2e16a0231e](https://github.com/Dhanusha17/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/151549957/115bc4a1-564c-49b5-bad1-fb2e838233f5)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
