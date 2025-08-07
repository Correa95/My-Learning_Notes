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
⚖️ Normalization
Why normalize?

1 Neural networks train better if input values or layer outputs are on similar scales.
2 Prevents exploding or vanishing gradients.

Makes training faster and more stable.

📌 1. Input Normalization
You scale data before feeding it to the network.

Example:

Pixel values in images: from [0, 255]

Normalize to [0, 1] by dividing by 255

📌 2. Batch Normalization
You apply this within the network, between layers.

It does this:

Takes the output of a layer

Calculates mean and variance for a batch

Scales and shifts the output to have zero mean and unit variance

Effect: Helps the model learn faster and generalize better.

🧠 Bringing it All Together:
A typical neural network:

scss
Copy
Edit
Input (normalized data)
↓
Hidden Layer 1 (neurons with weights, biases, activations)
↓
Batch Normalization
↓
Hidden Layer 2
↓
Output Layer
