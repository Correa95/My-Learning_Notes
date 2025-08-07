# Defining a Model with Hidden Layers

1. import pandas as pd
   concrete = pd.read_csv('../input/dl-course-data/concrete.csv')
   concrete.head()

imported keras from the tensorflow librery
from tensorflow import keras
from tensorflow.keras import layers

# YOUR CODE HERE

model = keras.Sequential([
layers.Dense(unit=512, activation= "relu", input_shape = input_shape),
layers.Dense(units=512, activation= "relu", input_shape = input_shape),
layers.Dense(units=512, activation= "relu", input_shape = input_shape)
layers.Dess(units=1)
])
