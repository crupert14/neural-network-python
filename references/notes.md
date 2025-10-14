# Neuron Basics

## `inputs[]`
Data given to a neuron — a neuron can take **any number of inputs**.

These inputs can come from:
- External data sources  
**or**
- Other neurons’ outputs

Input data cannot be changed directly, they are provided or produced. Inputs can only be changed by altering `weights[]` or `bias`

## `weights[]`
Each input is associated with a **weight** (1:1 mapping).

The neuron’s first step is to compute a **weighted sum** of all inputs, then add the bias


## `bias`
Bias is a **singular constant** associated with a neuron

> Every neuron has its own unique **bias**.

## `output`
Ouput is computed by multiplying each input with its associated weight and then adding the bias using the formula:

$output = \sum (inputs * weights) + bias$

### Examples:

Plain text:
> Bias = 2
>|Indices|0|1|2|3|
>|-|-|-|-|-|
>| Input | 1 | 2 | 3 | 2.5 |
>| Weight | 0.2 | 0.8 | -0.5 | 1.0 |
>
> $output = \sum (inputs * weights) + bias$ <br>
> $output = (1 * 0.2 + 2 * 0.8 + 3 * -0.5 + 2.5 * 1.0) + 2$ <br>
> $output = 4.8$

Python:
```python
inputs = [1, 2, 3, 2.5]
weights = [0.2, 0.8, -0.5, 1.0]
bias = 2

output = inputs[0]*weights[0] + inputs[1]*weights[1] + inputs[2]*weights[2] + inputs[3]*weights[3] + bias
print(output)
```
> Outputs 4.8
