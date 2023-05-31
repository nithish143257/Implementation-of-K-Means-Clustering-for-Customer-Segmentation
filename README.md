# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm :
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program.
## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: NITHISH  KUMAR P
RegisterNumber:  212221040115
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
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
## Output:

## data.head()
![image](https://github.com/NaveenKumar-008/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135244/d8e62051-9409-4093-b9c2-031766ac66a2)

## data.info()
![image](https://github.com/NaveenKumar-008/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135244/543b2c5a-7ef0-4ea9-8cb6-3a0ec119293f)

## data.isnull().sum()
![image](https://github.com/NaveenKumar-008/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135244/ddd10959-0347-4678-9479-644ab7f57c5c)

## Elbow method Graph
![image](https://github.com/NaveenKumar-008/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135244/05bacfb1-cc08-487d-ae2e-e9427831a509)

## KMeans clusters
![image](https://github.com/NaveenKumar-008/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135244/f27d5c0a-7c1b-4847-974b-6901209aa229)

## Customer segments Graph
![image](https://github.com/NaveenKumar-008/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135244/2249e039-69e2-43f3-9e49-2f7557304260)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
