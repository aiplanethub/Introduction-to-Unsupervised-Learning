# Non - Linear Dimensionality Reduction Methods

### Learning Objectives

* Non-linear Dimensionality Reduction Methods
* Kernel PCA
* t-distributed Stochastic Neighbor Embedding (tSNE)
* Self-Organizing Map (SOM)

### Non-linear Dimensionality Reduction Methods

Non-linear transformation methods also known as **manifold** **learning methods **are used when the data doesn’t lie on a linear** **subspace. It is based on the **manifold hypothesis** which says that **in a high dimensional structure, most relevant** **information is concentrated in small number of low dimensional manifolds**.

If a linear subspace is a flat sheet of paper, then a rolled up sheet of paper is a simple example of a nonlinear manifold. Informally, this is called a Swiss roll, a canonical problem in the field of non-linear dimensionality reduction.

Some popular manifold learning methods are:

1. **Multi-dimensional scaling (MDS) : **A technique used for** **analyzing similarity or dissimilarity of data as distances in a geometric spaces. Projects data to a lower dimension such that data points that are close to each other (in terms if Euclidean distance) in the higher dimension are close in the lower dimension as well.
2. **Isometric Feature Mapping (Isomap) : **Projects data to a lower** **dimension while preserving the geodesic distance (rather than Euclidean distance as in MDS). Geodesic distance is the shortest distance between two points on a curve.
3. **Locally Linear Embedding (LLE) : **Recovers global non-linear** **structure from linear fits. Each local patch of the manifold can be written as a linear, weighted sum of its neighbours given enough data.
4. **Hessian Eigenmapping (HLLE) : **Projects data to a lower** **dimension while preserving the local neighbourhood like LLE but uses the Hessian operator (a mathematical operator you don’t need to worry about right now) to better achieve this result and hence the name.
5. **Spectral Embedding (Laplacian Eigenmaps) : **Uses spectral** **techniques to perform dimensionality reduction by mapping nearby inputs to nearby outputs. It preserves locality rather than local linearity
6. **t-distributed Stochastic Neighbor Embedding (t-SNE) : **Computes the probability that pairs of data points in the high-dimensional space are related and then chooses a low-dimensional embedding which produce a similar distribution.

Kernel PCA, Isomap and many more..

Didn’t understand the basic definitions completely?

No worries, we’ll elaborate on some of the popularly used Non-Linear Dimensionality Reduction methods now.

### Kernel PCA

We’ve read about PCA till now. PCA is a linear method. That is it can only be applied to datasets which are linearly separable. It does an excellent job for datasets, which are linearly separable. But, many real-world data are not linearly separable. So if we use it to non-linear datasets, we might get a result which may not be the optimal dimensionality reduction.

Kernel PCA uses a kernel function to project dataset into a higher dimensional feature space, where it is linearly separable. It is similar to the idea of Support Vector Machines.

There are various kernel methods like linear, polynomial, and gaussian.

### The “magic” of high dimensions

* Given some problem, how do we know what classes of functions are capable of solving that problem?
* VC (Vapnik-Chervonenkis) theory tells us that often mappings which take us into a higher dimensional space than the dimension of the input space provide us with greater classification power.
* Problem: These classes are linearly inseparable in the input space. (in 2 dimensions)

![](https://lh5.googleusercontent.com/G\_rSK\_mQx5KKezuXDvlQFqQB8KruU5CgoUw5q4QMwyySUb7ZoPYVaRqXcuInSYe3gnY5fHlt9Xd4Y2FCnUL0mzobLL2ad5YY6MDE3TU9lyrWvQT1Y75\_-hizUyf86YOZRNmJSZA1D0E)

* Solution: High-Dimensional Mapping We can make the problem linearly separable by a simple mapping: (from 2 dim to 3 dim)

![](broken-reference)

### Kernel Trick

* High-dimensional mapping can seriously increase computation time.
* Can we get around this problem and still get the benefit of high Dimension?
* Yes! Using the Kernel Trick

Kernel trick is basically a method to project original data into higher dimension without sacrificing too much computational time. (Non-linear feature mapping).

Some popular kernels are:

* Gaussian
* Polynomial
* Hyperbolic Tangent

### Kernel PCA

Now coming to the main part, what is Kernel PCA?

Kernel PCA extends conventional principal component analysis (PCA) to a high dimensional feature space using the “kernel trick”.

With this, you can extract up to n (number of samples) nonlinear principal components without expensive computations.

### Kernel PCA Implementation

Below you can see a sample implementation of Kernel PCA. The kernel used here is linear but there are so many useful kernels you might want to try out.

![](broken-reference)

### t-distributed Stochastic Neighbor Embedding (tSNE)

t-Distributed Stochastic Neighbor Embedding (t-SNE) is a non-linear technique for dimensionality reduction that is particularly well suited for the **visualization of** **high-dimensional datasets**. It is extensively applied in image** **processing, NLP, genomic data and speech processing.

Until recently, it was actually the best state of the art / best dimensional technique. Now, it has been replaced by a better and faster technique called **UMAP**.

t-SNE basically decreases the multi-dimension to 2d or 3d dimensions such that it can be visualized by the human eyes. The data analysis work will be decreased as it can reveal various patterns in the data set in 2d or 3d.

### Visualizing 784 dimensions in 2d using t-SNE

![](broken-reference)

### t-SNE Detailed Explanation

{% embed url="https://youtu.be/NEaUSP4YerM" %}

### t-SNE Implementation in Python

t-SNE is present as a package in sklearn’s manifold library. A simple implementation of t-SNE will look something like below. We’ll dive into the details of the implementation in the notebook.

![](https://lh5.googleusercontent.com/c3cqA81--J-y9ptO1J87pDPbJbk1C3hWubpAg7uE00xxwD71sKWCOCFB0FDgABcukWQzbWUr4A1jMBr4ywxsK32-wpkBOUpFxcWJX-xuvf\_guDkXamIUXJ-mqqq7RaeK\_t8NtXmApDc)

### t-SNE Strengths

* **Works well for Non-Linear data: **It is able to interpret the complex relationship between features and represent similar data points in high dimension to close together in low dimension.
* **Preserves Local and Global Structure: **t-SNE is capable to preserve the local and global structure of the data. This means, points that are close to one another in the high-dimensional dataset, will tend to be close to one another in the low dimension.

### t-SNE Weakness

* **Dimensionality reduction for other purposes: **ex: BAD for feature selection/feature extraction because it is based on probability distribution -> only for visualization!
* **Curse of intrinsic dimensionality (sensitive to intrinsic dimension): **Intrinsic Dimension is the no. of variables are needed to generate a good approximation of the signal. Performs badly if high dimensional data actually have high intrinsic dimension.
* **Non-convexity of the t-SNE cost function: **several optimization parameters need to be chosen

### t-SNE Resources

Here’s an amazing article you can go through to understand t-SNE in detail: [https://towardsdatascience.com/what-why-and-how-of-t-sne-1f](https://towardsdatascience.com/what-why-and-how-of-t-sne-1f78d13e224d) [78d13e224d](https://towardsdatascience.com/what-why-and-how-of-t-sne-1f78d13e224d)

### Self-Organizing Map (SOM) or Self-Organizing Feature Map (SOFM)

A self-organizing map (SOM) is a type of artificial neural network (ANN) that is trained using unsupervised learning to produce a **low-dimensional (typically two-dimensional), discretized representation of the input space of the training samples**,** **called a **map**, and is therefore a method to do dimensionality reduction.

Self-organizing maps diﬀer from other artificial neural networks as they apply **competitive learning** as opposed to error-correction learning (such as backpropagation with gradient descent), and in the sense that they use a neighborhood function to preserve the topological properties of the input space.

SOM was introduced by Finnish professor Teuvo Kohonen in the 1980s is sometimes called a **Kohonen map**.

The video below gives a simple intuition about Self Organizing Maps, by connecting its working to a number of applications.

Feel free to skip the part ‘ Breaking Down the Weight Update Formula’, it gets a little mathematical there.

{% embed url="https://youtu.be/g8O6e9C_CfY" %}

### SOM Implementation in Python

While you can code SOM from scratch in Python, the package of choice for easily using self-organizing maps in Python is minisom: [https://github.com/JustGlowing/minisom](https://github.com/JustGlowing/minisom)

It is a minimalistic, Numpy based implementation of the Self-Organizing Maps and it is very user friendly. It can be installed using: `pip install minisom`

### Resources for understanding SOM in depth

* How SOM (Self Organizing Maps) algorithm works: [https://youtu.be/H9H6s-x-0YE](https://youtu.be/H9H6s-x-0YE)
* SOM Tutorial: [https://algobeans.com/2017/11/02/self-organizing-map/](https://algobeans.com/2017/11/02/self-organizing-map/)

### Notebook

Implementation of various linear and non-linear dimensionality reduction techniques:

[https://dphi.tech/notebooks/1326/gunnika/comparison-of-various-dimensionality-reduction-techniques-in-python](https://dphi.tech/notebooks/1326/gunnika/comparison-of-various-dimensionality-reduction-techniques-in-python)
