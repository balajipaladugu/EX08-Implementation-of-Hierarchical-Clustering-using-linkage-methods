# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Compute the distance between every pair of data points,resulting in a distance matrix.
2.Assign each data point to its own individual cluster.
3.Using a linkage criterion,find the two closest cluster and merge them.
4.Visualize the hierarchical clustering as a dendrogram.

## Program:
```

Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: PALADUGU VENKATA BALAJI
RegisterNumber: 2305001024

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage,fcluster
from sklearn.preprocessing import StandardScaler
df = pd.read_csv("/content/Hclus_EX8.csv")
df.head()
x = df[['StudentID','Marks']].values
x
z=linkage(x,method='complete')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
max_cluster=2
clusters=fcluster(z,max_cluster,criterion='maxclust')
clusters
plt.figure(figsize=(5,2))
plt.scatter(x[:,0],x[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented(Hierarchical clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
z=linkage(x,method='single')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()

```

## Output:
![image](https://github.com/user-attachments/assets/0b846b48-95e9-4f4b-a0d3-4bef6841084a)
![image](https://github.com/user-attachments/assets/d300bc81-ea55-4a94-9624-149b52fc4656)
![image](https://github.com/user-attachments/assets/2a20b7a9-8435-4ae4-a11d-094d4e6e6349)
![image](https://github.com/user-attachments/assets/e40cb457-8516-41f9-9291-a28f84fa99fc)



## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
