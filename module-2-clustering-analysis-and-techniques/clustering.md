# Clustering

### Learning Objectives

* A Use Case&#x20;
* What is Clustering?
* Applications of Clustering
* Overview of Clustering Techniques

### Clustering - A Use Case

Let’s assume we start a business to sell some services to people.

Business goes well and we have about 10,000 customers in our database within a few months. We want to keep our customers and also increase our revenue per customer. So we plan to oﬀer a deal to the customers in our database. We have two options:

* Oﬀer same deal to all customers
* Prepare customer-specific deals

![](<../.gitbook/assets/image (26).png>)

First option is straightforward.

“10% oﬀ on all services” deal would do the job. However, it is less eﬃcient and less profitable compared to customer-specific deals.

Furthermore, customer-specific deals are likely to be more appealing to customers.

* Some customers prefer a discount on a single item while others prefer a buy-one-get-one-free kind of deal.
* Some customers buy service A on the weekends while some others buy it on monday mornings.

We can list many more different options depending on business size and number of customers.

We decide to prepare customer-specific deals.

Next step is to decide what kind of deals to oﬀer. We cannot just create a diﬀerent deal for each customer. That is simply not manageable.

**A wise option could be detecting customers with similar interests or purchasing behavior and group them. **The** **criteria for grouping can be customer preferences, tastes, interests, customer-service combinations and so on.

It is extremely difficult to group customers manually. Then we ask machine learning for help. The task of grouping similar customers is called **clustering**.

### Clustering - Divide and Rule

A more formal definition from Wikipedia:

Cluster analysis or clustering is the task of grouping a set of objects in such a way that objects in the same group (called a cluster) are more similar (in some sense) to each other than to those in other groups (clusters).

**Objects in our use case are customers.**

### Clustering

Clustering can be considered the most important unsupervised learning problem.It deals with finding a structure in a collection of unlabelled data.

A loose definition of clustering could be “**the process of organizing objects** **into groups whose members are similar in some way**”. A cluster is therefore** **a collection of objects which are “similar” between them and are “dissimilar” to the objects belonging to other clusters.

PS. Clustering is just one type of Unsupervised Learning Algorithms. There exist many more.

![](<../.gitbook/assets/image (43).png>)

### Applications of Clustering

Clustering is used in almost all the fields.

* Clustering helps marketers improve their customer base and work on the target areas. It helps group people (according to different criteria such as willingness, purchasing power etc.) based on their similarity in many ways related to the product under consideration.
* Clustering helps in identification of groups of houses on the basis of their value, type and geographical locations.
* Clustering is used to study earthquake. Based on the areas hit by an earthquake in a region, clustering can help analyse the next probable location where earthquake can occur.

There are many more applications of clustering, such as document clustering and social network analysis. These applications are relevant in nearly every industry, making clustering a valuable skill for professionals working with data in any field.

Here’s a detailed list of applications. Take your time to explore it: [https://en.wikipedia.org/wiki/Cluster\_analysis#Applications](https://en.wikipedia.org/wiki/Cluster\_analysis#Applications)

### Overview of Clustering Techniques

You can perform clustering using many different approaches—so many, in fact, that there are entire categories of clustering algorithms. Each of these categories has its own unique strengths and weaknesses. This means that certain clustering algorithms will result in more natural cluster assignments depending on the input data.

Selecting an appropriate clustering algorithm for your dataset is often difficult due to the number of choices available. Some important factors that affect this decision include:

* characteristics of the clusters,
* features of the dataset,
* number of outliers,
* number of data objects.

### Overview of Clustering Techniques

You’ll explore how these factors help determine which approach is most appropriate by looking at some popular categories/sub-categories of clustering algorithms:

* Partitional clustering
* Hierarchical clustering
* Density-based clustering

### Partitional Clustering

Partitional clustering divides data objects into non-overlapping groups. In other words, **no object can be a member of more** **than one cluster, and every cluster must have at least one object.**

These techniques **require the user to specify the number of** **clusters**, indicated by the variable** k**. Many partitional clustering** **algorithms work through an iterative process to assign subsets of data points into k clusters. Two examples of partitional clustering algorithms are **k-means** and **k-medoids**.

These algorithms are both **non-deterministic**, meaning they could produce different results from two separate runs even if the runs were based on the same input.

![](<../.gitbook/assets/image (46).png>)

Partitional clustering methods have several strengths:

* They work well when **clusters have a spherical shape**.
* They’re **scalable** with respect to algorithm complexity.

They also have several weaknesses:

* They’re **not well suited for clusters with complex shapes** **and different sizes**.
* They **break down** when used with **clusters of different** **densities**.

### Hierarchical Clustering

Hierarchical clustering determines cluster assignments by building a hierarchy. This is implemented by either a bottom-up or a top-down approach:

* **Agglomerative clustering **is the bottom-up approach. It** **merges the two points that are the most similar until all points have been merged into a single cluster.
* **Divisive clustering **is the top-down approach. It starts with** **all points as one cluster and splits the least similar clusters at each step until only single data points remain.

![](https://lh6.googleusercontent.com/H70oWjsZOtena3GuEBOD0kt6S1zW44s405V7wToc5mL7MjJ4D8vsIcHtGGeX9AFybBL1NJ8gXBRxlmMPYw-iliXO5MVDOgSk8K0u8aAZ69sxn6eispSjfSlDF5mq2uHeVFPycrzO80Q)

These methods produce a tree-based hierarchy of points called a **dendrogram**. Similar to partitional clustering, in hierarchical** **clustering the **number of clusters (k) is often predetermined** **by the user**. Clusters are assigned by cutting the dendrogram at** **a specified depth that results in k groups of smaller dendrograms.

Unlike many partitional clustering techniques, hierarchical clustering is a **deterministic process**, meaning cluster assignments won’t change when you run an algorithm twice on the same input data.

The strengths of hierarchical clustering methods include the following:

* They often **reveal the finer details about the relationships** between data objects.
* They provide an **interpretable dendrogram**.

The weaknesses of hierarchical clustering methods include the following:

* They’re **computationally expensive** with respect to algorithm complexity.
* They’re sensitive to **noise** and **outliers**.

### Density-Based Clustering

Density-based clustering determines cluster assignments **based** **on the density of data points in a region**. Clusters are assigned** **where there are high densities of data points separated by low-density regions.

Unlike the other clustering categories, this approach **doesn’t** **require the user to specify the number of clusters **. Instead,** **there is a **distance-based parameter that acts as a tunable** **threshold**. This threshold determines how close points must be** **to be considered a cluster member.

Examples of density-based clustering algorithms include Density-Based Spatial Clustering of Applications with Noise, or **DBSCAN**, and Ordering Points To Identify the Clustering** **Structure, or **OPTICS**.

![](https://lh3.googleusercontent.com/Inkn9aO06yR4qguhT5ByEaphrljGRThI6GvHiekDeJRbjUjXcsoigln7RULtARVukWr\_-ZpYKVJ0twGkWylUpbY0aVlEuM93gf4s6k3ZcrC7mX6YMV0S3ooLshkSyoXp5nzOiKUktGQ)

The strengths of density-based clustering methods include the following:

* They excel at identifying clusters of **nonspherical shapes**.
* They’re **resistant to outliers**.

The weaknesses of density-based clustering methods include the following:

* They aren’t well suited for clustering in **high-dimensional** **spaces**.
* They have trouble identifying clusters of **varying densities**.

### Types of Clustering Algorithms

![](https://lh6.googleusercontent.com/g6FiQi7nqmWkVRU47yXZy5\_5P943hzsbHnERVPuBlRqf23GcK7PEUMy-sItQqSXztOy1SvIykMbJXUYJBWAWNxQQhkrl5smi0Ix6JDFrTE2sVe1W\_znftQcmMidRSFHz-dqtIxqVVmA)

### Types of Clustering Algorithms - an alternative categorisation

![](https://lh4.googleusercontent.com/nyvw6fRkWTftPLPZsh9dlCSrOAYhCiuVLBtdkVfCwrhT5tXGr0H2JrSbGUWpErFNq9fJdb4S0dhIrdkCC8WIpk4Eb\_LBIHLAZ07GxvhOuTx0ATcOoxfXQwV0YmStTH7t5ChdN23UAZM)
