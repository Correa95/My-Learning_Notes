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
