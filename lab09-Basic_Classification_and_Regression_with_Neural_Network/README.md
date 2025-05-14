# Lab09 – Neural Networks: Image Classification & Regression

## Theoretical Background

**Dense Neural Networks for Classification**

* **Feed‑forward architecture:** flatten 2D images into 1D vectors, then pass through fully connected (Dense) layers with ReLU activations to learn hierarchical feature representations.
* **Output logits & Softmax:** final Dense layer produces one logit per class; applying softmax converts logits into probabilities summing to 1.
* **Loss and optimizer:** use sparse categorical cross‑entropy loss for integer labels and SGD (or Adam) optimizer; softmax with from\_logits=True handles numerical stability.
* **Evaluation metrics:** track accuracy on training, validation, and test sets to monitor generalization.

**Callbacks: TensorBoard & Early Stopping**

* **TensorBoard:** logs training/validation loss and metrics per epoch into timestamped run directories, enabling visual comparison of experiments.
* **EarlyStopping:** halts training when validation loss fails to improve by a minimum delta (e.g., 0.01) over a specified patience (e.g., 5 epochs), preventing overfitting and saving computation.

**Neural Networks for Regression**

* **Normalization layer:** standardizes input features to zero mean and unit variance, improving training stability.
* **Architecture:** stack multiple Dense layers with ReLU activations, ending in a single linear output neuron for continuous prediction.
* **Loss and metrics:** use Mean Squared Error (MSE) as loss and report Root Mean Squared Error (RMSE) to interpret performance in the target’s units.
* **Train/validation/test split:** manually split data into training, validation, and test sets to tune hyperparameters on validation data and evaluate final performance on an unseen test set.

---

## Conclusions

* **Image Classification (Fashion MNIST):**

  * Network converged within \~15–20 epochs before early stopping.
  * Achieved \~88–90% test accuracy, with clear separation between commonly confused categories (e.g., shirt vs. pullover).

* **Regression (California Housing):**

  * Early stopping typically triggered around epoch 30–40, avoiding overfitting.
  * Final test RMSE was on the order of 0.5–0.6 (in median house value units), demonstrating reasonable predictive power given feature set.

* **Callback benefits:**

  * TensorBoard provided interactive loss and metric curves for all runs, enabling rapid experiment comparison.
  * EarlyStopping reduced unnecessary epochs, saving training time and delivering the model at its best validation performance.

---
