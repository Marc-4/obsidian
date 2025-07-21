*"brain cells"*
## Fundamental data types used to influence a model's decision making.

> [!terms]
> *Rank/Degree = array dimension
> *Shape = elements in each dimension

The number of elements in tensor is equal to product of all its shapes.
`[[[1,1,1], [1,1,1]]]`
shape = [1,2,3]
#### Reshaping
Tensors can be reshaped with the reshape() function.

>[!example]
>[1, 2, 3] -> [2, 3, 1]
> `[[[1], [1], [1]],[[1], [1], [1]]]`
> *number of elements in reshaped tensor must be the same.*
#### Types of Tensors

| Type         | Notes   |
| ------------ | ------- |
| [^1]Variable | mutable |
| Constant     |         |
| Placeholder  |         |
| SparseTensor |         |
#### Learning Algorithms
##### Linear Regression
