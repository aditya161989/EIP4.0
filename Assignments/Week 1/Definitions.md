# Definitions

**Convolution** - A fixed size matrix(generally 3X3) which iterates over an image to produce a feature map which is of lesser dimensionality than the original image.



**Filters/Kernels** - The output of a convolution on a region of the image creates a kernel.



**Epochs** - The number of times the whole dataset is iterated while training a model.



**1X1 Convolution** - A special convolution which is used for reducing the dimension of input.



**3X3 Convolution** - A standard convolution which creates an (n-2)X(n-2) feature map from a nXn input. Any higher dimension convolution can be created using the same.



**Feature Maps** - The output of a convolution applied on either an image or another feature map is called a feature map.



**Activation Function** - A function which triggers a neural network. If the function does not return a value then the neural network is said to have not fired. e.g. ReLU.



**Receptive Field** - The area visible to a feature. Differentiated into Global and Local. 