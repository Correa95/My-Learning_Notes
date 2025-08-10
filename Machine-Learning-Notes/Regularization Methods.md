# Regularization Definition

Regularization in neural networks refers to techniques used to prevent overfitting—when a model performs well on training data but poorly on unseen data. These methods add constraints or modifications to the training process to encourage the model to generalize better.

🧠 What Is Regularization?
Regularization methods aim to reduce model complexity or penalize extreme parameter values, helping the network learn more robust patterns rather than memorizing noise.

🛠️ Common Regularization Methods
| Method | Description | Example Use Case |
| L1 Regularization | Adds a penalty proportional to the absolute value of weights (Lasso) | Feature selection in sparse models |
| L2 Regularization | Adds a penalty proportional to the square of weights (Ridge) | Deep CNNs to prevent large weights |
| Dropout | Randomly disables neurons during training to prevent co-adaptation | Image classification with CNNs |
| Early Stopping | Stops training when validation loss starts increasing | Any model prone to overfitting |
| Data Augmentation | Expands training data by transforming inputs (e.g., rotate, flip images) | Vision tasks with limited data |
| Batch Normalization | Normalizes layer inputs to stabilize and regularize training | Deep networks like ResNet |
| Weight Constraint | Forces weights to stay within a certain range (e.g., max norm) | Recurrent Neural Networks |
