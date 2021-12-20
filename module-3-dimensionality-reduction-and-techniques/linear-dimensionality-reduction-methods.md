# Linear Dimensionality Reduction Methods

### Learning Objectives

* Linear Dimensionality Reduction Methods
* Principal Component Analysis (PCA)
* Independent Component Analysis (ICA)

### Linear Dimensionality Reduction Methods

The most common and well known dimensionality reduction methods are the ones that apply linear transformations, like:

1. **PCA (Principal Component Analysis) :** Popularly used for **** dimensionality reduction in continuous data, PCA rotates and projects data along the direction of increasing variance. The features with the maximum variance are the principal components.
2. **Factor Analysis :** a technique that is used to reduce a large **** number of variables into fewer numbers of factors. The values of observed data are expressed as functions of a number of possible causes in order to find which are the most important. The observations are assumed to be caused by a linear transformation of lower dimensional latent factors and added Gaussian noise.
3. **LDA (Linear Discriminant Analysis) :** projects data in a way **** that the class separability is maximised. Examples from same class are put closely together by the projection. Examples from different classes are placed far apart by the projection.
4. **ICA (Independent Component Analysis) :** transforms the **** dataset into columns of independent components. Blind Source Separation and the "cocktail party problem" are other names for it.

Some other linear dimensionality reduction methods include canonical correlations analysis, maximum autocorrelation factors, undercomplete independent component analysis, distance metric learning, and more.

This shows the immense scope of expanding your learning even further than this content.

Didn’t understand the basic definitions completely?

No worries, we’ll elaborate on some of the popularly used Linear Dimensionality Reduction methods now.

### Introduction to Principal Component Analysis (PCA)

Principal Component Analysis(PCA) is one of the most popular linear dimension reduction. Sometimes, it is used alone and sometimes as a starting solution for other dimension reduction methods.

PCA is a projection based method that is often used to reduce the dimensionality of large data sets, by transforming a large set of variables into a smaller one that still contains most of the information in the large set.

Reducing the number of variables of a data set naturally comes at the expense of accuracy, but the trick in dimensionality reduction is to trade a little accuracy for simplicity. Because smaller data sets are easier to explore and visualize and make analyzing data much easier and faster for machine learning algorithms without extraneous variables to process.

So to sum up, the idea of PCA is simple — reduce the number of variables of a data set, while preserving as much information as possible.

Some real-world applications of PCA are image processing, movie recommendation system, optimizing the power allocation in various communication channels.

### PCA Intuition

Suppose, you wish to diﬀerentiate between diﬀerent food items based on their nutritional content. Which variable will be a good choice to diﬀerentiate food items?

If you choose a variable which varies a lot from one food item to another, let’s say Sodium level, you will be able to isolate them properly. Your job will be much harder if the chosen variable is almost same in food items let’s say Vitamin E.

What if data doesn't have a variable which segregates food items properly? We can create an artificial variable through a linear combination of original variables like

artVar1 = 2 X orgVar1 - 3 X orgVar2 + 5 X orgVar3

This is what essentially PCA does, it finds best linear combinations of the original variables so that the variance or spread along the new variable is maximum.

### When should you use PCA?

1. Do you want to reduce the number of variables, but aren’t able to identify variables to completely remove from consideration?
2. Do you want to ensure your variables are independent of one another?
3. Are you comfortable making your independent variables less interpretable?

If you answered “yes” to all three questions, then PCA is a good method to use. If you answered “no” to question 3, you **should not** use PCA.

Some more particular use cases for PCA include:

* When having latent features driving the patterns in data.
* For Dimensionality reduction.
* To visualize high-dimensional data.
* To reduce the noise.
* As a preprocessing step to improve the performance of other algorithms.

### How does PCA work?

Here’s a brief non-technical summary of PCA’s working:

* We are going to calculate a matrix that summarizes how our variables all relate to one another.
* We’ll then break this matrix down into two separate components: direction and magnitude. We can then understand the “directions” of our data and its “magnitude” (or how “important” each direction is).

![](<../.gitbook/assets/image (40).png>)

* The figure displays the two main directions in this data: the “red direction” and the “green direction.”
* In this case, the “red direction” is the more important one. Can you understand why? (Hint: What would fitting a line of best fit to this data look like?)
* We will transform our original data to align with these important directions (which are combinations of our original variables). The figure below has the same exact data as above, but transformed so that the x-and y-axes are now the “red direction” and “green direction.” What would the line of best fit look like here?
* The red and green directions we’re talking about are the **principal** **components**, hence the name!

![](<../.gitbook/assets/image (17).png>)

* While the visual example here is two-dimensional (and thus we have two “directions”), think about a case where our data has more dimensions.
* By identifying which “directions” are most “important,” we can compress or project our data into a smaller space by dropping the “directions” that are the “least important.”
* By projecting our data into a smaller space, we’re reducing the dimensionality of our feature space… but because we’ve transformed our data in these different “directions,” we’ve made sure to keep all original variables in our model!

![](<../.gitbook/assets/image (10).png>)

Note two things in the above graphic:

1. The two charts show the exact same data, but the right graph reflects the original data transformed so that our axes are now the principal components.
2. In both graphs, the principal components are perpendicular to one another. In fact, **every principal component will ALWAYS be** **orthogonal (a.k.a. oﬃcial math term for perpendicular) to every other principal component.**

If you wish to dive deeper into the working of PCA, you can watch the next video at 2X.

It involves some technical terms but all the terms are explained in detail and it’s a good practice to be familiar with the internal workings of the algorithm you are implementing.

If you don’t wish to go into the details as of now, feel free to skip it :)

### Step by Step PCA

{% embed url="https://youtu.be/FgakZw6K1QQ" %}

### Need of Standardization

The aim of this step is to standardize the range of the continuous initial variables so that each one of them contributes equally to the analysis.

More specifically, the reason why it is critical to perform standardization prior to PCA, is that the latter is quite sensitive regarding the variances of the initial variables. That is, if there are large differences between the ranges of initial variables, those variables with larger ranges will dominate over those with small ranges (For example, a variable that ranges between 0 and 100 will dominate over a variable that ranges between 0 and 1), which will lead to biased results. So, transforming the data to comparable scales can prevent this problem.

### Scikit-Learn PCA Implementation

![](https://lh5.googleusercontent.com/LVLmX-Pyayeul1l84cJTQ7sBOyP04TO8crwQOr3E5c4hO9UFdfr5kgXp06T9sF3BC9XFqh0SElTyLhKiQ9CF8lwfzYK7mM8kS3SuxmVIXgNMV06zeishM35F9WK9a-c-vs4vzUf5b5k)

### Shortcomings of PCA

* If the number of variables is large, it becomes hard to interpret the principal components.
* PCA is most suitable when variables have a linear relationship among them.
* Also, PCA is susceptible to big outliers.

### Conclusion

PCA is an old method and has been well researched. There are many extensions of basic PCA which address its shortcomings like robust PCA, kernel PCA, incremental PCA.

### Independent Component Analysis (ICA)

ICA is a method for dimensionality reduction similar to PCA in the sense that it takes a set of features and produces a diﬀerent set that is useful in some way.

But while PCA tries to maximize variance, ICA assumes that the features are mixtures of independent sources and it tries to isolate these independent sources that are mixed in the dataset.

The motivation behind ICA would be **to take the original set of** **features and try to identify those of them that contribute independently to the dataset, in other words, those with the least correlation to the other features.** So **it will isolate those most important components**. This problem is called **Blind Source Isolation.**

{% embed url="https://youtu.be/2WY7wCghSVI" %}

{% embed url="https://youtu.be/wIlrddNbXDo" %}

### ICA Implementation in Sci-kit learn

![](https://lh3.googleusercontent.com/nnmaBuZW7VyqU8fLdan5emgzqsvXfR6eYwsSlW62f38\_TPyockONvEfnZmYcAfxnjM7g9NtOyKOoL4uUvWWH-zXrkgCOCwHwD5eCKjygDZ\_YDtk6RzUjt-XbEYjSn-sMUi4D1PcPtEk)

### ICA Applications

One interesting application of ICA is the analysis of Electroencephalographic data (data from the brain). ICA is an important tool in neuroimaging, fMRI, and EEG analysis that helps in separating normal signals from abnormal ones.

The following is an example of the readings of 14 channels from an EEG scan that lasted 4.5 seconds and the independent components extracted from the dataset.

![](https://lh5.googleusercontent.com/gIuu3q8wfJEBQbdYZakmVpCkaqeGLfhnCk4047Ms4cZ5Hexx9RWbxZRr7id3hMlskmCD5DfUQf8qQrDjwMs-f-ZKmBH0bJ1s8dB5vFG5BPOMN10WNqg1S93h2I6CDYd1YGNGvxLYxbU)

### Drawbacks of ICA

ICA cannot uncover non-linear relationships of the dataset. ICA does not tell us anything about the order of independent components or how many of them are relevant.

### PCA vs ICA

* PCA removes correlations, but not higher order dependence
* ICA removes correlations and higher order dependence
* PCA: some components are more important than others (eigenvalues)
* ICA: all components are **equally important**
* PCA: vectors are orthogonal
* ICA vectors are **not orthogonal**

![](<../.gitbook/assets/image (35).png>)
