[[Python]]
[[Machine Leanring - AI]]

Pytorch tensors are created using torch.tensor():

```python
import torch

scalar = torch.tensor(7)
# A tensor with only value 7, ndim = 0. This is called a scalar

vector = torch.tensor(7, 8, 9)
# This is a typical vector, ndim = 1

# And similarly, ndim increases, tensors change their types,...
matrix = torch.tensor([7, 8],
					 [8, 9]) # ndim = 2 
```

Each of the type bellow is a kind of a Tensor.

