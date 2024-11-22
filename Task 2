# Import necessary libraries
import pandas as pd
import numpy as np
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans
from sklearn.metrics import silhouette_score
from sklearn.decomposition import PCA
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset (replace 'data.csv' with your dataset)
data = pd.read_csv('C:\data analytics task\Customers.csv')

# Display the first few rows of the dataset
print(data.head())

# --- STEP 1: Data Preprocessing ---

# Select relevant features for segmentation (customize based on your dataset)
# Example: ['CustomerID', 'Recency', 'Frequency', 'Monetary']
# Drop irrelevant columns (e.g., CustomerID for clustering)
features = data[['Family Size', 'Spending Score (1-100)', 'Age']]

# Check for missing values and handle them
print(features.isnull().sum())
features = features.dropna()

# Standardize the data
scaler = StandardScaler()
features_scaled = scaler.fit_transform(features)

# --- STEP 2: Determine Optimal Number of Clusters ---

# Use the Elbow Method
sse = []
k_range = range(1, 11)
for k in k_range:
    kmeans = KMeans(n_clusters=k, random_state=42)
    kmeans.fit(features_scaled)
    sse.append(kmeans.inertia_)

# Plot the Elbow Curve
plt.figure(figsize=(8, 5))
plt.plot(k_range, sse, marker='o')
plt.xlabel('Number of Clusters (k)')
plt.ylabel('Sum of Squared Errors (SSE)')
plt.title('Elbow Method for Optimal k')
plt.show()

# --- STEP 3: Apply K-Means Clustering ---

# Choose the optimal number of clusters (e.g., 4 based on the Elbow Method)
optimal_k = 4
kmeans = KMeans(n_clusters=optimal_k, random_state=42)
clusters = kmeans.fit_predict(features_scaled)

# Add cluster labels to the original dataset
data['Cluster'] = clusters

# --- STEP 4: Analyze Clusters ---

# Aggregate data by cluster to understand segment characteristics
cluster_analysis = data.groupby('Cluster').agg({
    'Family Size': ['mean', 'median'],
    'Spending Score (1-100)': ['mean', 'median'],
    'Age': ['mean', 'median', 'sum']
}).reset_index()

print(cluster_analysis)

# --- STEP 5: Visualize Clusters ---

# Reduce dimensions using PCA for visualization
pca = PCA(n_components=2)
pca_components = pca.fit_transform(features_scaled)

# Add PCA components and cluster labels to a new DataFrame
pca_df = pd.DataFrame(pca_components, columns=['PCA1', 'PCA2'])
pca_df['Cluster'] = clusters

# Plot the clusters
plt.figure(figsize=(10, 7))
sns.scatterplot(data=pca_df, x='PCA1', y='PCA2', hue='Cluster', palette='tab10', s=100)
plt.title('Customer Segments (PCA Visualization)')
plt.xlabel('PCA Component 1')
plt.ylabel('PCA Component 2')
plt.legend(title='Cluster')
plt.show()

# --- STEP 6: Save the Results ---

# Save the dataset with cluster labels
data.to_csv('segmented_customers.csv', index=False)
print("Segmented data saved as 'segmented_customers.csv'.")
