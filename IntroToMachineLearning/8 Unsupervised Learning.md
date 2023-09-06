# 8 Unsupervised Learning
22:12:1409:04
Status:  #MachineLearning
Tags: 

---
- What is **dimensionality reduction**?
	- Sometimes we want to decrease the number of dimensions to better represent and visualize the data
	- We can reduce dimensionality through **feature extraction** and **feature selection**
- What is **the curse of dimensionality**?
	- Increasing the number of features is not always optimal
	- The more features we have the more problems with performance we may expect
	- Performance of models decreases with increase of number of dimensions
	- The more dimensions the sparser is the representation of them
- What is **feature extraction** in dimensionality reduction?
	- Finding new features by *mapping* (applying some function) over existing features.
- What is **feature selection** in dimensionality reduction?
	- Choosing a subset of *original* features
- What is **Principal Component Analysis** - **PCA**
	- We try to find the point of view which gives the best representation
	- Find the axis that shows the greatest variation and project all points into this axis
	- PCS finds global, not vocal variance 
	![[8 Unsupervised Learning PCA.png|500]]
- How to compute Principal Component Analysis?
	- Through the use of eigenvalues and eigenvectors
- What are the drawbacks of PCA?
	- It does not retain non-linear variance
	- It only retains global variance
- What is **t-Stochastic Neighbour Embedding (t-SNE)**?
	- We downgrade the number of dimensions while trying to retain the relations between neighbours
	- It is a nonlinear dimensionality reduction method
	- It retains local variance
	- It cannot transform the data
	- it is a machine learning algorithm that generates slightly different results each time on the same data set, focusing on retaining the structure of neighbour points.
- What is **multi-dimensional scaling (MDS)**?
	- Dimensionality reduction method which preserves distance between neighbours better than t-SNE
	- It is not stochastic
	- It can lead to rotations, but it does not matter as it preserves the structure
---
- What is **clustering**?
	- Unsupervised learning technique, where the task is to find patterns in the data by grouping data in clusters
- What are applications of clustering?
	- User segmentation / identification 
	- Community identification (in social media)
	- Identifying different types of tissue in medical imaging
	- Parsing in language processing
- How can we calculate the *Distance metrics*?
	- Euclidean Distance
	- Manhattan Distance
	- Minkowski Distance - a generalization of Manhattan (m=2) and Euclidean(m=1) distance for higher values of m (which means higher distance weights). ![[8 Unsupervised Learning Minkowski Distance.png]]
	- Chebyshev Distance ($L\infty$ metric) (Minkowski Distance with m ⇾ $\infty$)
	- Mahalanobis or Statistical Distance (standardized Euclidean distance)
- What are the *metrics for clustering*?
	- Within Cluster Sum of Squared errors (WSS) - measured from the centre of the cluster
	- Silhouette Value - a measure of how similar an object is to its own cluster (cohesion) compared to other clusters (separation). It ranges from -1 to 1.
- What is **Elbow Method**?
	- A method of determining the value $k$ of the number of clusters, where we run the clustering algorithm for some numbers of $k$ and select the value of $k$ with diminishing returns of the clustering metrics
	- ![[8 Unsupervised Learning Elbow method.png]]
- What is **K-Means Clustering**
	- There is an assumption that all the clusters have a comparable number of points
	- We assign centroids at random and then at each step me move them to the mean centre of the points in the cluster
	- ![[8 Unsupervised Learning K-means clustering.png]]
- What are assumptions of K-Means clustering?
	- Cluster centres are inside the cluster
	- It only works when the clusters are defined as the centers from the centroid.
- What is a **Voronoi Diagram**?
	- A partition of a plane by the distance to the closest point (centroid)
	- ![[8 Unsupervised Learning voronoi diagram.png|200]]
---
- What is **DBSCAN clustering**?
	- Make clusters based on intensity of data points
	- It assumes that there are outliers not belonging to any group
	- Basic concepts of DBSCAN:
		- Core point - points which have at least minPts points within $\epsilon$ distance
		- Direct reachability: when a point is within $\epsilon$ distance from a core point
		- Reachability
		- Outliers and noise: any point not reachable from a core point
		- Density connection
		- Cluster
- What are DBSCAN hyperparameters?
	- Distance threshold $\epsilon$
	- Minimum number of Points minPts
- What are the advantages of DBSCAN
- ![[8 Unsupervised Learning DBSCAN.png]]

---
# References