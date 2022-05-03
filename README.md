# Cryptocurrencies

## Purpose
Unsupervised learning is a type of algorithm that learns patterns from untagged data. We will be using it to process data, cluster, reduce dimensions, and reduce principal components using PCA to create an analysis on the cryptocurrency market. 

## Results

### Clustering Crytocurrencies Using K-Means

#### Elbow Curve

Using the following code, to map the elbow curve: 

``
inertia = []
k = list(range(1, 11))

for i in k:
    km = KMeans(n_clusters=i, random_state=0)
    km.fit(pcs_df)
    inertia.append(km.inertia_)

# Create an elbow curve to find the best value for K.
elbow_data = {'k' : k, 'inertia' : inertia}
elbow_df = pd.DataFrame(elbow_data)
elbow_df.hvplot.line(x='k', y='inertia', title='Elbow Curve', xticks=k)
``

![Elbow Curve](/Resource/Elbow_Curve.png)
![K Means](/Resource/K_Means.png)

From this, we can see that the best k value is 4. 

### Visualizing Cryptocurrencies Results

#### 3D-Scatter with Clusters

![3D Scatter](/Resource/3D_scatter.png)

#### Tradable Crypto Table

![Tradable Crypto](/Resource/tradable_crypto.png)

#### 2D-Scatter with Clusters

![2D Scatter](/Resource/2D_scatter.png)