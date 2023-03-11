

# ${Code \space Snippets}$

The Code Snippets are provided here. The code snippets for the ***three different models*** are provided. This folder must be opened when the person wants to have an 
***abstract knowledge*** of the project and the Models developed.

### ${First \space Model}$

```java
from keras import Sequential                                           # Importing Sequential neural network...
from keras.layers import Dense, Conv2D, AveragePooling2D, Flatten                 # Importing layers...
from keras.activations import relu, softmax                            # Importing activation functions...

classes = 3
ConvolutionalNetworkI = Sequential([
    Conv2D(filters=32, input_shape=(128, 128, 1), kernel_size=5, activation="relu", name="conv1", padding="same"),
    AveragePooling2D(pool_size=(3, 3)),
    Conv2D(filters=16, kernel_size=4, activation="relu", name="conv2", padding="same"),
    AveragePooling2D(pool_size=(2, 2)),
    Flatten(name="Flatten"),                # Output shape = 16 neurons, Input shape = 7056 neurons...
    Dense(16, relu, name="dense1"),         # Output shape = 16 neurons, Input shape = 16 neurons...
    Dense(8, relu, name="dense2"),          # Output shape = 8 neurons, Input shape = 16 neurons...
    Dense(classes, softmax, name="dense3")  # Output shape = 3 neurons, Input shape = 8 neurons...
])
```

    Accuracy Score = 0.7826
    Loss = 0.4794

-----

### ${Second \space Model}$

```java
from keras import Sequential     # Importing sequential neural network...
from keras.layers import MaxPooling2D, Dense        # Importing the required layers...
from keras.activations import relu, linear, softmax   # Importing activation functions...

classes = 3
ConvolutionalNetworkII = Sequential([
    Conv2D(filters=128, input_shape=(128, 128, 1), kernel_size=3, activation="relu", name="conv1", padding="same"),      
    # Convolution Neural Network...
    MaxPooling2D(pool_size=(2, 2)),   # Max Pooling...
    Conv2D(filters=64, kernel_size=3, activation="relu", name="conv2", padding="same"),
    MaxPooling2D(pool_size=(2, 2)),   # Max Pooling...
    Conv2D(filters=32, kernel_size=3, activation="relu", name="conv3", padding="same"),
    MaxPooling2D(pool_size=(2, 2)),   # Max Pooling...
    Flatten(name="Flatten"),               # Output layer = 8192 neurons, Input layer = 16 x 16 x 32 neurons...
    Dense(32, relu, name="dense1"),        # Output layer = 32 neurons, Input layer = 8192 neurons...
    Dense(16, relu, name="dense2"),        # Output layer = 16 neurons, Input shape = 32 neurons...
    Dense(8, linear, name="dense3"),       # Output layer = 8 neurons, Input layer = 16 neurons...
    Dense(classes, softmax, name="dense4") # Output layer = 3 neurons, Input layer = 8 neurons...
])
```

    Accuracy Score = 0.8416
    Loss = 0.3420

-----

### ${Third \space Model}$

```java
from keras.activations import elu, relu, linear, softmax

ConvolutionalNetworkIII = Sequential([
    Conv2D(filters=256, input_shape=(128, 128, 1), kernel_size=2, activation="relu", name="conv1", padding="same"),
    MaxPooling2D(pool_size=(2, 2)),
    Conv2D(filters=128, kernel_size=2, activation="relu", name="conv2", padding="same"),
    MaxPooling2D(pool_size=(2, 2)),
    Conv2D(filters=64, kernel_size=2, activation="relu", name="conv3", padding="same"),
    MaxPooling2D(pool_size=(2, 2)),
    Conv2D(filters=32, kernel_size=2, activation="relu", name="conv4", padding="same"),
    MaxPooling2D(pool_size=(2, 2)),
    Flatten(name="Flatten"),                
    Dense(32, elu, name="dense1"),         # Output layer = 32 neurons, Input layer = 8224 neurons...
    Dense(16, relu, name="dense2"),        # Output layer = 16 neurons, Input layer = 32 neurons...
    Dense(8, linear, name="dense3"),       # Output layer = 8 neurons, Input layer = 16 neurons...
    Dense(4, linear, name="dense4"),       # Output layer = 4 neurons, Input layer = 8 neurons...
    Dense(classes, softmax, name="dense5") # Output layer = 3 neurons, Input layer = 4 neurons...
])
```

    Accuracy Score = 0.8202
    Loss = 0.3966

-----


### ${Fourth \space Model}$

```java
from keras.activations import swish, relu, elu, softmax

ConvolutionalNetworkIV = Sequential([
    Conv2D(filters=300, input_shape=(128, 128, 1), kernel_size=1, activation="relu", name="conv1", padding="same"),
    MaxPooling2D(pool_size=(2, 2)),
    Conv2D(filters=150, kernel_size=1, activation="relu", name="conv2", padding="same"),
    MaxPooling2D(pool_size=(2, 2)),
    Conv2D(filters=75, kernel_size=1, activation="relu", name="conv3", padding="same"),
    MaxPooling2D(pool_size=(2, 2)),
    Conv2D(filters=32, kernel_size=2, activation="relu", name="conv4", padding="same"),
    MaxPooling2D(pool_size=(2, 2)),
    Flatten(name="Flatten"),
    Dense(32, elu, name="dense1"),           # Output layer = 32, Input layer = 2048 neurons...
    Dense(16, relu, name="dense2"),          # Output layer = 16, Input layer = 32 neurons...
    Dense(8, swish, name="dense3"),          # Output layer = 8, Input layer = 16 neurons...
    Dense(4, relu, name="dense4"),           # Output layer = 4 neurons, Input layer = 8 neurons...
    Dense(classes, softmax, name="dense5")   # Output layer = 3 neurons, Input layer = 4 neurons...
])
```

    Accuracy Score = 0.7862
    Loss = 0.4476

-----

## ${Ciphered \space By}$
***Vishu Kalier***






























