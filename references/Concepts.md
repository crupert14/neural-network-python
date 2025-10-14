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

# Dot Product