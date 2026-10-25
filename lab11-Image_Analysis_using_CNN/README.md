# Lab11 – Image Analysis with Convolutional Neural Networks

> **Status:** the notebook contains only the environment setup (TensorFlow, Keras, `tensorflow_datasets`); the exercises were not completed.

## Theoretical Background

**Convolutional Layers**

* A convolutional layer slides small learnable filters (kernels) over the image; each filter detects a local pattern such as an edge or a texture.
* Weights are shared across positions, so CNNs need far fewer parameters than dense networks and are translation-invariant.
* Key parameters: number of filters, kernel size, `strides` and `padding` (`"same"` keeps the spatial size).

**Pooling Layers**

* Max or average pooling downsamples feature maps, reducing computation and making the network more robust to small shifts.

**Typical CNN Architecture**

* Stacks of `Conv2D` + pooling blocks, with the number of filters growing as the spatial size shrinks.
* The final feature maps are flattened (or globally pooled) and passed to `Dense` layers with a softmax output for classification.

**Transfer Learning**

* Pretrained models (e.g. from `keras.applications`) can be reused as feature extractors: freeze the base, train a new classification head, then optionally fine-tune the top layers with a small learning rate.
* Image datasets are loaded with `tensorflow_datasets` and preprocessed (resizing, normalization) in a `tf.data` pipeline.

---
