# Implementation of Random Forest Algorithm for Weather Prediction
## AIM:
To write a program to predict daily temperature , PM2.5 pollution level and Energy based on environmental sensor data using Random Forest Algorithm.

## Problem Statement and Dataset



## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries, load the mall customer dataset, and check for missing values and dataset information.
2. Apply the K-Means clustering algorithm with different cluster values to calculate WCSS and use the Elbow Method to find the optimal number of clusters.
3. Train the K-Means model with 5 clusters, predict customer groups, and store the cluster labels in the dataset.
4. Separate the customers based on clusters and visualize the customer segments using a scatter plot of Annual Income vs Spending Score.

## Program:
```
/*
Program to implement the Random Forest Algorithm to predict daily temperature , PM2.5 pollution level and Energy based on environmental sensor data.
Developed by: Sajin Praneeth S R
RegisterNumber:  212224060229
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers (1).csv")
data.head()
data.info()
data.isnull()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss= [] 
for i in range(1,11):
kmeans=KMeans(n_clusters = i,init = "k-means++")
kmeans.fit(data.iloc[:,3:])
wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
1/4
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="black",label="clu
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="cyan",label="clust
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="yellow",label="cl
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="clust
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="green",label="clu
plt.legend()
plt.title("Customer Segments")
*/
```

## Output:
<img width="693" height="243" alt="Screenshot 2026-05-16 151141" src="https://github.com/user-attachments/assets/9368208c-bfee-4376-81ab-58c1b5af47cb" />

<img width="764" height="1079" alt="Screenshot 2026-05-16 160610" src="https://github.com/user-attachments/assets/c4faeacd-4eb9-4d99-9ded-a744e9902507" />
<img width="715" height="258" alt="WhatsApp Image 2026-05-16 at 4 13 09 PM" src="https://github.com/user-attachments/assets/c0b2e32f-bfed-45b4-b643-3fa03d588afe" />
<img width="551" height="322" alt="Screenshot 2026-05-16 161117" src="https://github.com/user-attachments/assets/4d00a8de-086f-4ee2-82d5-c0ddd662999d" />



## Result:
