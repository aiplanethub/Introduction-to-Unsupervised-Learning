# Clustering Algorithms: Hierarchical Clustering

### Learning Objectives

* Hierarchical Clustering & Dendrogram
* Divisive and Agglomerative methods
* Linkages in Clustering
* Steps to perform Hierarchical Clustering (Agglomerative)
* Choosing the Number of Clusters in Hierarchical Clustering

### Hierarchical Clustering & Dendrogram

{% embed url="https://youtu.be/ijUMKMC4f9I" %}

### Hierarchical Clustering

Hierarchical clustering involves creating clusters that have a predetermined ordering from top to bottom. For example, all files and folders on the hard disk are organized in a hierarchy. There are two types of hierarchical clustering, Divisive and Agglomerative.

![](broken-reference)

### Divisive method

Divisive hierarchical clustering or top-down clustering method works by starting with 1 cluster containing the entire data set and then partitioning the cluster to two least similar clusters.

We proceed recursively on each cluster until there is one cluster for each observation.

There is evidence that divisive algorithms produce more accurate hierarchies than agglomerative algorithms in some circumstances but is conceptually more complex.

### Agglomerative method

Agglomerative clustering or bottom-up clustering method starts with each observation as its own cluster.

Then, compute the similarity (e.g., distance) between each of the clusters and join the two most similar clusters.

Finally, repeat steps 2 and 3 until there is only a single cluster left.

### Linkages in Clustering

Before any clustering is performed, it is required to determine the proximity matrix containing the distance between each point using a distance function. Then, the matrix is updated to display the distance between each cluster.

**In simple words, we need to define what “close” means.**

The distance itself or the measurement unit can be Euclidean or Manhattan distance.

There are a variety of possible metrics to set how the distance between each cluster is measured, but we will list the 4 most popular here: single-linkage, complete-linkage, average-linkage, and centroid-linkage.

### Single-Linkage

Single-linkage (nearest neighbour) is the shortest distance between a pair of observations in two clusters. For example, the distance between clusters “r” and “s” to the left is equal to the length of the arrow between their two closest points.

![](broken-reference)

It can sometimes produce clusters where observations in different clusters are closer together than to observations within their own clusters. These clusters can appear spread-out.

### Complete Linkage

Complete-linkage (farthest neighbour) is where distance is measured between the farthest pair of observations in two clusters. For example, the distance between clusters “r” and “s” to the left is equal to the length of the arrow between their two furthest points.

![](broken-reference)

This method usually produces tighter clusters than single-linkage, but these tight clusters can end up very close together. Along with average-linkage, it is one of the more popular distance metrics.

### Average Linkage

Average-linkage is where the distance between each pair of observations in each cluster are added up and divided by the number of pairs to get an average inter-cluster distance. For example, the distance between clusters “r” and “s” to the left is equal to the average length each arrow between connecting the points of one cluster to the other.

![](broken-reference)

Average-linkage and complete-linkage are the two most popular distance metrics in hierarchical clustering.

### Centroid-Linkage

Centroid-linkage is the distance between the centroids of two clusters.

As the centroids move with new observations, it is possible that the smaller clusters are more similar to the new larger cluster than to their individual clusters causing an inversion in the dendrogram. This problem doesn’t arise in the other linkage methods because the clusters being merged will always be more similar to themselves than to the new larger cluster.

![](broken-reference)

### Hierarchical Clustering

{% embed url="https://youtu.be/7xHsRkOdVwo" %}

### Steps to perform Hierarchical Clustering (Agglomerative)

* At the start, treat each data point as one cluster. Therefore, the number of clusters at the start will be K, while K is an integer representing the number of data points.

![](https://lh3.googleusercontent.com/woPaAF4-z1gkDdxm53oYHF1BlB84gTBIvOiCgQ9pu2wZDpHLkrwmCpjLCpsvk60hdwX9TVLZv\_uFvOFfUG9ABIsUnSrit2odho6n0LcN59YcXtF51PEqQEBF\_2mEJrygZxoSCzQUmVM)

* Form a cluster by joining the two closest data points resulting in K-1 clusters.
* Form more clusters by joining the two closest clusters resulting in K-2 clusters.
* Repeat the above three steps until one big cluster is formed.

![](https://lh3.googleusercontent.com/SxgjMyXCHMx-JAduq3\_ij\_nMkkdDyizYg\_TuQCzm28G1x7JHANoLgfSXXXZY0dPb\_ozn3AHTyAxgzi-4QCcUysiu5Sw70tfARNsJzzgFTJgYeQI4bhFZLVsKf8dePMTBIhtqcf\_Dl2Q)

* Once single cluster is formed, dendrograms are used to divide into multiple clusters depending upon the problem.

### Choosing the Number of Clusters in Hierarchical Clustering

* To get the number of clusters for hierarchical clustering, we make use of an awesome concept called a Dendrogram.
* A dendrogram is a tree-like diagram that records the sequences of merges or splits.
* Taking an example of the following data points:

![](https://lh6.googleusercontent.com/-Mca\_4oFjs8FaCZjnNQHJXkCFjPxwuhm0xunmJUAu7xcoO7W\_vV\_V5V\_SUkv9TBAysUl8se4v6OXhcNr4X3dxwyk\_6Vou\_d4sgJCzhSR9nZrHMMVqcYjkutWszecbfRtSfOlUqGWVRc)

* The dendrograms for our data points will look something like below.

![](https://lh3.googleusercontent.com/3X0nyWKUMpA1y17XatyqLOv-7LNj8NAtTtXUZLOe4-D0GJy7fzJZsRFQ0IvxlS40VJfbkEOb-93xc6l1n3o2XsTnBsTwamV2kEtWSBM-TkDvgtXnev5yHp3aRl0Se1cpvu2U5msbIhA)

* We can clearly visualize the steps of hierarchical clustering.
* More the distance of the vertical lines in the dendrogram, more the distance between those clusters.
* Once one big cluster is formed, the longest vertical distance without any horizontal line passing through it is selected and a horizontal line is drawn through it. **The number of vertical lines this newly** **created horizontal line passes is equal to number of clusters**.** **Take a look at the following plot:

![](https://lh5.googleusercontent.com/IfsFRSklLszl0-diYTZIcsJzwhCQ0GpSa1CDu\_F0jQZillcNplOoo7wchYO94eURNJ3GyhxuWU14os4cqjQ2mpB3BC-ECoRDPbqqS6qY7ewvydFh-p35gJE3uK3G-UwROZUwFWVxFuA)

* Here, the no. of clusters = 2 since the red line is passing through 2 points
* Basically the horizontal line is a threshold, which defines the minimum distance required to be a separate cluster. If we draw a line further down, the threshold required to be a new cluster will be decreased and more clusters will be formed as can be seen in the image below:

![](https://lh3.googleusercontent.com/0P9IHCtHUWo5ZcFnuPdGFYGcpUWNCw4-v\_895xA6NNoziQIpu4Ruvj1S-un541DR2-2g-OUWZImwb\_dcfoF5RiFNsV2QKkAe06nPPHxXb6MDc1fRjk6mp3g78bEbMNsNulc8gAsPrQw)

* The horizontal line passes through four vertical lines resulting in four clusters: cluster of points 6,7,8 and 10, cluster of points 3,2,4 and points 9 and 5 will be treated as single point clusters.

### Notebooks

Introduction to Hierarchical Clustering: [https://dphi.tech/notebooks/1323/gunnika/introduction-to-hierarchical-clustering](https://dphi.tech/notebooks/1323/gunnika/introduction-to-hierarchical-clustering)

Types of Hierarchical Clustering Algorithms: [https://dphi.tech/notebooks/1324/gunnika/types-of-hierarc](https://dphi.tech/notebooks/1324/gunnika/types-of-hierarchical-clustering)[hical-clustering](https://dphi.tech/notebooks/1324/gunnika/types-of-hierarchical-clustering)
