# Defining a Model with Hidden Layers

1. import pandas as pd
   concrete = pd.read_csv('../input/dl-course-data/concrete.csv')
   concrete.head()

2. from tensorflow import keras

# YOUR CODE HERE

from tensorflow.keras import layers
model = keras.Sequential([
layers.Dense(unit=512, activation= "relu", input_shape = input_shape),
layers.Dense(units=512, activation= "relu", input_shape = input_shape),
layers.Dense(units=512, activation= "relu", input_shape = input_shape)
layers.Dess(units=1)
])
