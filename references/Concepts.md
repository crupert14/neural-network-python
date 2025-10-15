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
Computed by multiplying the values of different array indices, and then adding them together. Weights are passed first when calculating **Dot Product** because data should be indexed by weight sets.

### Examples:

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