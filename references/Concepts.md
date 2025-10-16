# Neural Network Concepts

## Shape
At each dimension, what is the size of ***that*** dimension? Arrays must be homologous, meaning they must have the same size ***in*** each dimension

For example:
> Given:
> ```python
> [1, 5, 6, 2]
> ```
> The shape is (4,)
>> This is a
>> - 1 dimensional list in python
>> - 1 dimensional array in numpy
>> - Vector in mathematics

> Given:
> ```python
> [[1, 5, 6, 2]
>  [3, 2, 1, 3]]
> ```
> The shape is (2, 4)
>> This is a
>> - List of lists in python
>> - 2 dimensional list in numpy
>> - Matrix in mathematics (a rectangular array, a list of vectors is a matrix)

> Given:
> ```python
> [[[1, 5, 6, 2],
>   [3, 2, 1, 3]]
>  [[5, 2, 1, 2],
>   [6, 4, 8, 4]],
>  [[2, 8, 5, 3],
>   [1, 1, 9, 4]]]
> ```
> The shape is (3, 2, 4)
>> This is a
>> - List of lists of lists in python
>> - 3 dimensional array in numpy

## Dot Product
Computed by multiplying the values of different array indices, and then adding them together. Weights are passed first when calculating **Dot Product** given a single sample of inputs because data should be indexed by weight sets. Weight is passed second and transposed when given a batch of inputs because otherwise the inner dimensions do not match.

> The second dimension of the first matrix must equal the first dimension of the second matrix.

### Examples with single samples of inputs:

Python:
> Given:
> ```python
> a = [1, 2, 3]
> b = [2, 3, 4]
> dot_product = a[0]*b[0] + a[1]*b[1] + a[2]*b[2]
> ```
> Output is 20

Plain text:
> $\vec{a} = [1,2,3]$ <br>
> $\vec{b} = [2,3,4]$ <br>
>
> $\vec{a} * \vec{b} = Dot Product$ <br>
> $[1,2,3] * [2,3,4] = Dot Product$ <br>
> $1*2 + 2*3 + 3*4 = Dot Product$ <br>
> $20 = Dot Product$

## Batches
The number of training samples processed before the models parameters are updated. Should be 32, 64 or in rare cases 128, in most cases 32 is the most utilized batch size.

## Transposing
Convert rows to columns in a matrix. This is done for the purpose of calculating **Dot Product** when given batches of inputs, rather than a single list.

## Fully Connected Layer Example

The following is a basic example of a fully connected layer

```python
import numpy as np
# Used for consistent values in testing
np.random.seed(0)

class Layer_Dense:
    def __init__(self, n_inputs, n_neurons):
        self.weights = 0.10 * np.random.randn(n_inputs, n_neurons)
        self.biases = np.zeros((1, n_neurons))
    def forward(self, inputs):
        self.output = np.dot(inputs, self.weights) + self.biases
```

### Breakdown ---
1. `__init__` <br>
    1. `np.random.randn(n_inputs, n_neurons)`
        - Creates a matrix of random values normally distributed with a mean of 0 and std of 1. This produces a shape of `(n_inputs, n_neurons)` - each **row** corresponds to an input feature and each **column** corresponds to a neuron
    2. `0.10 * ...`
        - Scales down weight values to prevent large numbers at the start of training
    3. `np.zeros((1, n_neurons))`
        - Each neuron has one `bias`
        - The `(1, n_neurons)` shape means one row and one bias per neuron
        - Initially set to 0
2. `forward` <br>
    1. Function where the layer computes output given some inputs

## Hidden Layers
All layers in between the input and output layers. These are referred to as **hidden layers** because you do not directly interact with or necessarily see the input or output.

## ReLU (Rectified Linear Unit)
One of the most common activation functions used in neural networks. Introduces non-linearity into a network, allowing for learning of complex patterns.

Characterized by being:
- Simple and fast
- Allow for complex function learning by a network
- Less prone to vanishing gradients

With `X` representing input:
> If `X > 0`, `output = X`<br>
> If `X <= 0`, `output = 0`