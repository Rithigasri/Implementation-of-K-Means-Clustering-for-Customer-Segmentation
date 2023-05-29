# EXPERIMENT 08:IMPLEMENTATION OF K MEANS CLUSTERING FOR CUSTOMER SEGMENTATION

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## EQUIPMENT'S REQUIRED:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## ALGORITHM:
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program

## PROGRAM:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: RITHIGA SRI.B  
RegisterNumber:  212221230083
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
wcss=[] #Within-Cluster Sum of Square

for i in range(1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## OUTPUT:
1. data.head() function  
![image](https://github.com/Rithigasri/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427256/3189f719-7c9b-4333-a1d2-acfe3755b9da)

2. data.info()  
![image](https://github.com/Rithigasri/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427256/e672b71a-81b7-4a47-96fc-48a2519171d9)

3. data.isnull().sum() function    
![image](https://github.com/Rithigasri/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427256/968e2d88-4633-4475-9b9b-ca342e9a6cf1)

4. Elbow method Graph    
![image](https://github.com/Rithigasri/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427256/90620aad-b59d-4ed4-a315-c704e3b702c0)

5. KMeans clusters    
![image](https://github.com/Rithigasri/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427256/b64f7822-d7b2-44aa-b5a0-69b3e44be8b4)

6. Customer segments Graph    
![image](https://github.com/Rithigasri/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427256/48213896-3954-4a74-8992-eeb9d9a9b662)


## RESULT:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
