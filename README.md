# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: V. HARINI
RegisterNumber:  212225040113
*/

# Import libraries
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# ------------------------------
# Step 1: Load dataset from CSV
# ------------------------------
df = pd.read_csv("Mall_Customers.csv")

# Display first 5 rows
print(df.head())

# ------------------------------
# Step 2: Select features for clustering
# ------------------------------
X = df[['Annual Income (k$)', 'Spending Score (1-100)']]

# ------------------------------
# Step 3: Apply K-Means
# ------------------------------
kmeans = KMeans(n_clusters=3, init='k-means++', random_state=42)

# Fit and predict clusters
df['Cluster'] = kmeans.fit_predict(X)

# ------------------------------
# Step 4: Visualize clusters
# ------------------------------
plt.figure(figsize=(8,6))

for i in range(3):
    plt.scatter(
        X[df['Cluster'] == i]['Annual Income (k$)'],
        X[df['Cluster'] == i]['Spending Score (1-100)'],
        label=f'Cluster {i+1}'
    )

# Plot centroids
plt.scatter(
    kmeans.cluster_centers_[:,0],
    kmeans.cluster_centers_[:,1],
    s=200,
    c='yellow',
    marker='X',
    label='Centroids'
)

plt.title('Customer Segmentation (K-Means)')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.show()

# ------------------------------
# Step 5: Show dataset with clusters
# ------------------------------
print(df)
```

## Output:

<img width="719" height="147" alt="image" src="https://github.com/user-attachments/assets/fa533b1e-cfc0-4786-b223-b2e0fb0292b5" />

<img width="986" height="663" alt="image" src="https://github.com/user-attachments/assets/c0752de9-71c5-4670-95de-f73663b1d1f1" />

<img width="918" height="580" alt="Screenshot 2026-05-23 231907" src="https://github.com/user-attachments/assets/4c121f88-4fb2-42b2-98a9-b0cdfb0ef4f8" />






## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
