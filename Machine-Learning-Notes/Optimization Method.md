# Optimization Definition

<!--
Optimization in neural networks is the process of adjusting the model's parameters—typically the weights and biases—to minimize the error between predicted outputs and actual targets. This is done by minimizing a loss function, which quantifies how far off the predictions are from the ground truth. -->

⚙️ What Is an Optimization Method?
An optimization method (or optimizer) is an algorithm that updates the parameters of the neural network during training to reduce the loss. It uses gradients computed via backpropagation to guide these updates.

# This is the job of the optimizer. The optimizer is an algorithm that adjusts the weights to minimize the loss.

Virtually all of the optimization algorithms used in deep learning belong to a family called stochastic gradient descent. They are iterative algorithms that train a network in steps. One step of training goes like this:

- Sample some training data and run it through the network to make predictions.
- Measure the loss between the predictions and the true values.
- Finally, adjust the weights in a direction that makes the loss smaller.

# Each iteration's sample of training data is called a minibatch (or often just "batch"), while a complete round of the training data is called an epoch. The number of epochs you train for is how many times the network will see each training example

🔑 Key Concepts:

- Loss Function: Measures prediction error (e.g., Mean Squared Error, Cross-Entropy).
- Gradient Descent: Core algorithm that moves parameters in the direction of steepest descent of the loss.
- Learning Rate: Controls the size of each update step.
- Momentum: Helps accelerate updates in consistent directions and dampens oscillations.
- Regularization: Techniques like L2 penalty to prevent overfitting.

🚀 Common Optimization Algorithms
| Optimizer | Description | Use Case Example |
| SGD | Stochastic Gradient Descent; updates weights using one or few samples | Simple image classification |
| Adam | Adaptive Moment Estimation; combines momentum and adaptive learning rates | NLP tasks, deep CNNs |
| RMSprop | Scales learning rate based on recent gradients | Recurrent Neural Networks |
| Adagrad | Adapts learning rate for each parameter based on past gradients | Sparse data problems |
| AdamW | Variant of Adam with better weight decay handling | Transformer-based models |

📚 Example Use Case: Image Classification with CNN
Scenario:
You’re training a Convolutional Neural Network (CNN) to classify handwritten digits (e.g., MNIST dataset).
Optimization Setup:

- Loss Function: Cross-Entropy Loss
- Optimizer: Adam
- Learning Rate: 0.001
- Epochs: 10–20
  Process:
- Forward pass computes predictions.
- Loss function evaluates prediction error.
- Backpropagation calculates gradients.
- Adam optimizer updates weights using gradients and internal moment estimates.
- Repeat for multiple epochs until loss converges.

🚀 Common Optimization Algorithms
| Optimizer | Description | Use Case Example |
| SGD | Stochastic Gradient Descent; updates weights using one or few samples | Simple image classification |
| Adam | Adaptive Moment Estimation; combines momentum and adaptive learning rates | NLP tasks, deep CNNs |
| RMSprop | Scales learning rate based on recent gradients | Recurrent Neural Networks |
| Adagrad | Adapts learning rate for each parameter based on past gradients | Sparse data problems |
| AdamW | Variant of Adam with better weight decay handling | Transformer-based models |
