# Lab13 – Autoencoders and Denoising

> **Status:** the notebook contains the setup and data preparation only (MNIST loaded, scaled to [0, 1] and split into 55 000 train / 5 000 validation / 10 000 test images); the model exercises were not completed.

## Theoretical Background

**Autoencoders**

* An autoencoder learns to reproduce its input: the **encoder** compresses it into a low-dimensional latent representation (coding), and the **decoder** reconstructs the input from it.
* Because the coding layer is smaller than the input, the network has to learn the most important structure of the data – a form of nonlinear dimensionality reduction.
* Trained without labels, using a reconstruction loss (MSE or binary cross-entropy for pixel values in [0, 1]).

**Architectures**

* **Stacked (dense) autoencoder:** several `Dense` layers that shrink towards the coding layer and mirror back in the decoder.
* **Convolutional autoencoder:** `Conv2D` + pooling in the encoder and `Conv2DTranspose` / upsampling in the decoder – better suited for images.

**Denoising Autoencoders**

* Noise (Gaussian noise or `Dropout`) is added to the input during training, while the target stays the clean image.
* The network learns to remove the noise, which also forces it to learn more robust features.

**Uses**

* Visualization of the latent space, unsupervised pretraining, anomaly detection (high reconstruction error) and image denoising.

---
