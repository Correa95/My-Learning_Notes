# Defining a Model with Hidden Layers

# imported pandas library to read the data from a CSV file

1. import pandas as pd
   concrete = pd.read_csv('../input/dl-course-data/concrete.csv')

# Display the data

concrete.head()

# This is the imported libraries

2. from tensorflow import keras
   from tensorflow.keras import layers

# This is the model creation using the sequential API

model = keras.Sequential([
layers.Dense(units=512, activation= "relu", input_shape = input_shape),

# input_shape means amount of input OR features

layers.Dense(units=512, activation= "relu", ),

# "relu" is and activation function use when the data is nonlinear

layers.Dense(units=512, activation= "relu", )
layers.Dense(units=1)
])

# Activation Layers Scenario

Let's explore activations functions some.
The usual way of attaching an activation function to a Dense layer is to include it as part of the definition with the activation argument. Sometimes though you'll want to put some other layer between the Dense layer and its activation function. (We'll see an example of this in Lesson 5 with batch normalization.) In this case, we can define the activation in its own Activation layer, like so:
layers.Dense(units=8),
layers.Activation('relu')
This is completely equivalent to the ordinary way: layers.Dense(units=8, activation='relu').
Rewrite the following model so that each activation is in its own Activation layer.
model = keras.Sequential([
layers.Dense(32, input_shape=[8]),
layers.Activation("relu"),
layers.Dense(32, input_shape=[8]),
layers.Activation("relu"),
layers.Dense(1)
])

⚖️ Normalization:
Normalization is a technique to standardize input or activations so that the neural network trains faster and more reliably.

Types:
1 Input normalization: e.g., scaling inputs to a range like [0, 1] or [-1, 1]
2 Batch normalization: applied inside the network, it normalizes outputs of a layer before the next layer.

⚖️ Normalization
Why normalize?
1 Neural networks train better if input values or layer outputs are on similar scales.
2 Prevents exploding or vanishing gradients.
3 Makes training faster and more stable.

📌 1. Input Normalization
You scale data before feeding it to the network.

Example:
1 Pixel values in images: from [0, 255]
2 Normalize to [0, 1] by dividing by 255

📌 2. Batch Normalization
You apply this within the network, between layers.

It does this:
1 Takes the output of a layer
2 Calculates mean and variance for a batch
3 Scales and shifts the output to have zero mean and unit variance

Effect: Helps the model learn faster and generalize better.

🧠 Bringing it All Together:
A typical neural network:

Input (normalized data)
↓
Hidden Layer 1 (neurons with weights, biases, activations)
↓
Batch Normalization
↓
Hidden Layer 2
↓
Output Layer

🏗️ Layer
A layer = a group of neurons.
Each neuron in a layer takes the same input, does its own computation, and passes output to the next layer.

Visualization:

Input Layer: [x1] [x2]
Hidden Layer: ⬤ ⬤ ⬤ (3 neurons)
Output Layer: ⬤
Each ⬤ is a neuron doing its own calculation.

➡️ Neural networks have:
Input layer (raw data)

Hidden layers (extract patterns)

Output layer (gives prediction/class)
