# Defining a Model with Hidden Layers

1. import pandas as pd
   concrete = pd.read_csv('../input/dl-course-data/concrete.csv')
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
layers.Dense(32, activation='relu', input_shape=[8]),
layers.Dense(32, activation='relu'),
layers.Dense(1),
])
