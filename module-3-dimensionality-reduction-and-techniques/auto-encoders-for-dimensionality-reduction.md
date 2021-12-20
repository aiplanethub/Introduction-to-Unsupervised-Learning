# Auto-Encoders for Dimensionality Reduction

### Learning Objectives

* Introduction to Auto-encoders&#x20;
* Components of Auto-encoders
* Example of Image reconstruction with dimensionality reduction
* Applications of Auto-encoders

### Auto-encoders

Another popular dimensionality reduction method that gives spectacular results are auto-encoders, a type of artificial neural network that aims to copy their inputs to their outputs.

Its procedure starts compressing the original data into a shortcode ignoring noise. Then, the algorithm uncompresses that code to generate an image as close as possible to the original input.

### Components of Auto-encoders

An autoencoder is composed of two parts :

1. **Encoder:** compresses the input into a latent-space **** representation.
2. **Decoder:** reconstruct the input from the latent space **** representation.

![](<../.gitbook/assets/image (16).png>)

### Example of Image reconstruction with dimensionality reduction

![](<../.gitbook/assets/image (12).png>)

You might notice that the reconstructed images are a little blurry and not so detailed. But, they still retain the same structure.

### Applications of Auto-encoders

* Dimensionality Reduction
* Image Compression
* Image Denoising
* Feature Extraction
* Image generation
* Sequence to sequence prediction
* Recommendation system

### Autoencoder

{% embed url="https://youtu.be/Rdpbnd0pCiI" %}

### Additional Resources

Autoencoders involve the concept of Deep Learning. So make sure you’re familiar with it before starting with implementation of Autoencoders. We’ll not be diving into it at the moment.

Implementation of Autoencoders on MNIST Dataset: [https://pub.towardsai.net/autoencoders-for-dimensionality-redu](https://pub.towardsai.net/autoencoders-for-dimensionality-reduction-6fb6553f392f) [ction-6fb6553f392f](https://pub.towardsai.net/autoencoders-for-dimensionality-reduction-6fb6553f392f)
