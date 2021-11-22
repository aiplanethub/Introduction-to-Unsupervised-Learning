# Clustering Algorithms: K-Means

### Learning Objectives

* What is K-Means Clustering?
* How does it work?
* Choosing the number of clusters for K-means:
  * Elbow Method
  * Silhouette Method
* Pros and Cons of K-Means

### K-Means Clustering

K-means clustering is one of the simplest and popular unsupervised machine learning algorithms. You can also say it to be the most popular clustering algorithm.

It is intuitive, easy to implement and fast.

K = number of clusters/ groups you want the data to be divided into.

![](<../.gitbook/assets/image (36).png>)

### How does it work?

K-means is unsupervised model so the data is unlabelled. But the model mathematically allocates each data point to a cluster.

Here we have some 2-dimensional unlabelled data that looks like below. All the points are of the same colour(green) i.e they are not segregated into clusters at the moment.

![](<../.gitbook/assets/image (14).png>)

**STEP 0: Decide the number of clusters (K)**

Upon initializing the model, we must pre-decide on a number of clusters. Having to do this in advance is a drawback of the model.

Let’s choose k=2 (aka. 2 clusters) for this example.

**STEP 1: **Randomly create centroids or points that are supposed to** **be the centers of the clusters (represented by purple). Note that they don’t need to be at the centers initially, they can be placed anywhere.

![](<../.gitbook/assets/image (7).png>)

**STEP 2: **Each data point is allocated to the nearest centroid

![](<../.gitbook/assets/image (22).png>)

Initially, our clusters look like below (look at how the data is divided into red and yellow clusters):

![](<../.gitbook/assets/image (30).png>)

**STEP 3: **Centroids move to the location of the average of points in** **their cluster

![](<../.gitbook/assets/image (6).png>)

**STEP 4: **Repeat allocating each point to the nearest centroid.

![](<../.gitbook/assets/image (34).png>)

Which gives us clusters according to our second iteration.

![](<../.gitbook/assets/image (1).png>)

**STEP 5: **Repeat this process until clusters stop moving

That is, when 2 consecutive times you get the same clusters, there’s no need to repeat the steps.

Is that it?

Yes. Except that we can end up with some pretty poor results if the initial centroid locations are not optimal.

So we repeat this whole process multiple times, and accept the result with the least cumulative variation across clusters.

### Summary

![](https://lh5.googleusercontent.com/ISRnoE9iUqRRRYORSFeIg54tcJ49qn26GTOWRkuo9UvmEG6W\_dupz6k2rM045AKC5Ln43DtmFyK10VVVHBEdFmqu6lDUbwf6Pp5bcTmzyEzF9YMkDwuVizJIB6JqzB2pjoFZPwq6XIM)

{% embed url="https://youtu.be/IJt62uaZR-M" %}

### K-means Clustering

{% embed url="https://youtu.be/EItlUEPCIzM" %}

### Must Try!

This website will allow you to visualise K-Means clustering on your own. At one point, you’ll observe that the centroid has stopped moving and the clusters remain the same. That is when you know that the algorithm has converged and given you the final clusters.

I strongly suggest to spend some time with this tool: [https://www.naftaliharris.com/blog/visualizing-k-means-clustering/](https://www.naftaliharris.com/blog/visualizing-k-means-clustering/)

![](https://lh6.googleusercontent.com/UZZA1jPLjt7B7kpboQUJf-gBGM\_SnN1v99O1H3v8QhxZKNx29Yr2Ewdw4H74Zk1t1flZaTVUngR7CLdviDgbTmPV1ryUfArxfUJOJMSEB5\_OG0xymquJaMxJx5848dbCNXK9L-2ftxk)

### Choosing the number of clusters for K-means

One of the most challenging tasks in this clustering algorithm is to choose the right values of k.

If you are choosing the k values randomly, it might be correct or may be wrong. If you will choose the wrong value then it will directly aﬀect your model performance. So there are two methods by which you can select the right value of k.

1. Elbow Method.
2. Silhouette Method.

Now, Let’s understand both the concepts one by one in detail.

### Elbow Method

Elbow is one of the most well-known methods by which you can select the right value of k and boost your model performance. It is also a bit naive in its approach.

It is an empirical method to find out the best value of k. it picks up the range of values and takes the best among them. It calculates the sum of the square of the points and calculates the average distance.

Why is it called an ‘elbow’ method, you may ask? That is because the graph plotted in this case resembles an elbow. The value of k falling on the joint part is what we consider to be the optimum value.

![](https://lh5.googleusercontent.com/VWz9sXhcdy5y1UqokLc3uC59AyUXaWDf30Ga8Ge2dkvzpZJLxRvoZ5qjqY1fNiDP-5Q3x3Zf8-P-pKD44Sx4UGWKvAvXBdm7W78VMfSOyJApcApCo1AsbevmID1Roe-YsJ3aCzhWjFM)![](https://lh5.googleusercontent.com/e3iJmPxIHb9K0HMp9-KJ-eyx\_5G4vCzBX\_NE4zsBRyk1OwdzkqlaGHwtI30ikWppbTixRnWoyCGuJxFg--zOB-x5zrdQlXsS8b9lxORcWb19-yra6Y4LRtKPAWHlVVVMm4oUPGIfXrE)



Since the graph starts almost straightening out at 3, 3 is the optimum k value according to the elbow method.

### Problems with Elbow Method

Unfortunately, we do not always have such clearly clustered data. This means that the elbow may not be clear and sharp.

![](https://lh4.googleusercontent.com/ZMXFNImAav3SXBfqSuoS77YU5KsWc9zQ83DmIfHPeuG4MCUDy5mZP9wcaboqzJa5fEQ4gU7B-Hv1NndWrpvZciqqKilfq2h9AAwOXADuhjPJd2MH5uVUMKxp2v8UoOTf194WJylEsd4)

For Dataset A, the elbow is clear at k = 3. However, this choice is ambiguous for Dataset B. We could choose k to be either 3 or 4.

In such an ambiguous case, we may use the Silhouette Method.

### Silhouette Method

The silhouette method is somewhat different. Like the elbow method, it also picks up the range of the k values and draws the silhouette graph. It calculates the silhouette coefficient of every point.

A higher Silhouette Coefficient score relates to a model with better defined clusters.

For eg. in the 1st graph, you can see that cyan has a higher silhouette coefficient score. It is also the most segregated (better defined) than the other two clusters black and yellow.

Silhouette value measures how similar a point is to its own cluster (cohesion) compared to other clusters (separation).

* The range of the Silhouette value is between +1 and -1.
* A high value is desirable and indicates that the point is placed in the correct cluster.
* If many points have a negative Silhouette value, it may indicate that we have created too many or too few clusters.

We mentioned before that a high Silhouette Score is desirable. **The** **Silhouette Score reaches its global maximum at the optimal k. **This** **should ideally appear as a peak in the Silhouette Value-versus-k plot.

Here is one such plot:

![](https://lh3.googleusercontent.com/F7O0tT2kg9MloPXqte9HQ7dJIFiBYEf7VJTdwckLAQ9VjiF0vt\_Z2kjm90-XPlwOId1ZSL\_dtjSWSUis2IsKUIRuvfjhjJYF5dAnOlHM5ly-Co1\_b6wB9gk43-wxHFVlyDzdKWZpxN4)

There is a clear peak at k = 3. Hence, it is optimal.

### Note

The Elbow Method is more of a decision rule, while the Silhouette is a metric used for validation while clustering. Thus, it can be used in combination with the Elbow Method.

Therefore, the Elbow Method and the Silhouette Method are not alternatives to each other for finding the optimal K. Rather they are tools to be used together for a more confident decision.

### Implementation of Elbow and Silhouette methods

[https://medium.com/analytics-vidhya/how-to-determine-the-opti](https://medium.com/analytics-vidhya/how-to-determine-the-optimal-k-for-k-means-708505d204eb) [mal-k-for-k-means-708505d204eb](https://medium.com/analytics-vidhya/how-to-determine-the-optimal-k-for-k-means-708505d204eb)

This article explains in detail two methods that can be useful to find the mysterious k in k-Means. These methods are:

1. The Elbow Method
2. The Silhouette Method

### Pros and Cons of KMeans

Pros:

* Easy to interpret
* Relatively fast
* Scalable for large data sets
* Able to choose the positions of initial centroids in a smart way that speeds up the convergence
* Guarantees convergence

Cons:

* Number of clusters must be pre-determined. K-means algorithm is not able to guess how many clusters exist in the data. Determining number of clusters may well be a challenging task.
* Can only draw linear boundaries. If there is a non-linear structure separating groups in the data, k-means will not be a good choice.
* Slows down as the number of samples increases because at each step, k-means algorithm accesses all data points and calculates distances.
* Sensitive to outliers

### Notebook

Implementation of KMeans Clustering:

[https://dphi.tech/notebooks/1325/gunnika/implementing-kmeans-clustering-algorithm](https://dphi.tech/notebooks/1325/gunnika/implementing-kmeans-clustering-algorithm)
