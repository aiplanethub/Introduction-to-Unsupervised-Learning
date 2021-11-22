# Dimensionality Reduction

### Learning Objectives

* Feature Importance and Feature Selection&#x20;
* Feature Extraction
* Curse of Dimensionality
* Dimensionality Reduction
* Benefits of Dimensionality Reduction
* Dimensionality Reduction Methods

### Problem & Solution

**Problem:**

Gone are the days when you had 5 variables to fit your linear regression: Modern datasets contain more variables/features to choose from. A dataset with 50 or more features -> more than 1 million observations.

**Solution: **Dimensionality Reduction using Feature Selection and** **Feature Extraction

### Feature Importance and Feature Selection

**Feature Importance **refers to techniques that assign a score to** **input features based on how useful they are at predicting a target variable.

**Feature Selection **is the process where you automatically or** **manually select features which contribute most to your target variable.

In short, Feature Importance Scores are used for performing Feature Selection

Suppose we’re working on the Iris Classification. We’ll first create a baseline model using Logistic Regression. Now, we want to try out Feature Selection and try to improve our model’s performance. On plotting feature importance scores, we obtain the below graph:

![](<../.gitbook/assets/image (41).png>)

* Feature Importance Scores tell us that Petal width and length are the the top 2 features. The rest have a much lower importance score.
* We’ll select these 2 features.
* We’ll transform our existing dataset to contain only these 2 features.
* We’ll train our model on this transformed dataset.
* Finally, we’ll compare the evaluation metrics of our initial Logistic Regression model with this new model.

### Feature Extraction

**Feature Extraction **is a feature reduction process. Unlike** **feature selection, which ranks the existing attributes according to their significance, feature extraction **actually** **transforms the features**.

The key difference between feature selection and extraction is that feature selection keeps a subset of the original features while feature extraction creates brand new ones.

Feature extraction is the name for methods that **select and** **/or combine variables into features**, effectively reducing** **the amount of data that must be processed, while still accurately and completely describing the original data set.

### Feature Extraction and Selection

![](<../.gitbook/assets/image (11).png>)

**Feature selection** — Selecting the most relevant attributes

**Feature extraction** — Combining attributes into a new reduced set of features

### Visualizing High-Dimensional Space

{% embed url="https://youtu.be/wvsE8jm1GzE" %}

### Curse of Dimensionality

You might already know a number of optimization methods and think what’s the need of reducing our data by feature selection or extraction if we can just optimize?

There’s something known as “_The curse of dimensionality_”. In machine learning,

“dimensionality” = number of features (i.e. input variables) in your dataset.

![](<../.gitbook/assets/image (18).png>)

When the number of features is very large relative to the number of observations(rows) in your dataset, certain algorithms struggle to train eﬀective models. This is called the **Curse of Dimensionality**.

### Curse of dimensionality analogy

Let's say you have a straight line 100 yards long and you dropped a penny somewhere on it. It wouldn't be too hard to find. You walk along the line and it takes two minutes.

Now let's say you have a square 100 yards on each side and you dropped a penny somewhere on it. It would be pretty hard, like searching across two football fields stuck together. It could take days.

Now a cube 100 yards across. That's like searching a 30-story building the size of a football stadium. Ugh.

**The difficulty of searching through the space gets a lot harder as you have more dimensions.**

### Curse of Dimensionality

The curse of dimensionality refers to all the problems that arise when working with data in the higher dimensions, that did not exist in the lower dimensions.

![](https://lh5.googleusercontent.com/XBlK9cMGAk1R6Vvd7XImnZnuHDjJuS1duTFjY44MJ83BRyeOEQ582dUDxmbFQIX0wxVWWzWZVuqH5HqOypKrhIQ8\_pG9RDSRpJkJsPw8Yc-ZmPm5isT9lFN2YNUgAw\_X9ZLNYnVTLEQ)

As the number of features increases, the model becomes more complex. The more the number of features, the more the chances of overfitting. A machine learning model that is trained on a large number of features, gets increasingly dependent on the data it was trained on and in turn overfitted, resulting in poor performance on real data, beating the purpose.

### Dimensionality Reduction

In machine learning we are having too many factors on which the final classification is done. These factors are basically, known as variables.

The higher the number of features, the harder it gets to visualize the training set and then work on it. Sometimes, most of these features are correlated, and hence redundant.

This is where dimensionality reduction algorithms come into play.

### Benefits of performing Dimensionality Reduction

* **Reduces Overfitting: **Less redundant data means less** **opportunity to make decisions based on noise(irrelevant data).
* **Improves Model Performance: **Less misleading data means our** **model’s performance improves.
* **Reduces Training Time: **Less data means that algorithms train** **faster.
* **Utilize Unlabelled Data: **Most of features extraction techniques** **are unsupervised. You can train your autoencoder or fit your PCA on unlabeled data. This can be helpful if you have a lot of unlabeled data and labeling is time-consuming and expensive.
* **Better Visualization: **Reducing the dimensions of data to 2D or** **3D may allow us to plot and visualize it precisely. You can then observe patterns more clearly.

### Dimensionality Reduction Methods

![](<../.gitbook/assets/image (23).png>)

The various methods used for dimensionality reduction include, but are not limited to:

1. Principal Component Analysis (PCA)
2. Independent Component Analysis (ICA)
3. Factor Analysis
4. Linear Discriminant Analysis (LDA)
5. Generalized Discriminant Analysis (GDA)

Dimensionality reduction may be both linear or non-linear, depending upon the method used. We will explore some of the dimensionality reduction methods in detail next.
