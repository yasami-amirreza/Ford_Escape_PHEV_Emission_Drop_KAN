This is the github repository for the papers: ["DropKAN: Regularizing KANs by masking post-activations"](https://arxiv.org/abs/2407.13044) and ["Rethinking the Function of Neurons in KANs
"](https://arxiv.org/abs/2407.20667). 

# Dropout Kolmogorov-Arnold Networks (DropKAN) 
<img width="1200" alt="dropkan_explained" src="https://github.com/Ghaith81/dropkan/blob/master/DropKAN_explained.JPG">
DropKAN operates by randomly masking some of the post-activations within the KANs computation graph, while scaling-up the retained post-activations.

## How to use

The DropKAN model can be used similar to KAN to create a model of DropKANLayers. Three parameters are needed with DropKAN:

- drop_rate: A list of floats indicating the rates of drop for the DropKAN mask. E.g., for the DropKAN model [6, 10, 1], drop_rate could be [0.1, 0.2], indicating a 0.1 drop_rate for the 6x10 activations between layers 0 and 1, and 0.2 drop_rate for the 10x1 activations between layers 1 and 2.
- drop_mode:  Accept the following values 'postspline' the drop mask is applied to the layer's postsplines, 'postact' the drop mask is applied to the layer's postacts, 'dropout' applies a standard dropout layer to the inputs, Default: 'postact'.
- drop_scale: If true, the retained postsplines/postacts are scaled by a factor of 1/(1-drop_rate). Default: True.


## Citation
```python
@article{altarabichi2024dropkan,
  title={DropKAN: Regularizing KANs by masking post-activations},
  author={Altarabichi, Mohammed Ghaith},
  journal={arXiv preprint arXiv:2407.13044},
  year={2024}
}

```

#Rethinking the Function of Neurons in KANs
In this paper, we suggest replacing the summation in KAN neurons with an averaging function. Our experiments show that employing the average function results in more stable training, ensuring that the inputs remain within the effective range of the spline activations. Utilizing the average function clearly aligns with the Kolmogorov-Arnold representation theorem.

## How to use
To change the neuron function the parameter neuron_fun must be passed to the DropKANLayer with one of the following possible values:
 ['sum', 'min', 'max', 'multiply', 'mean', 'std', 'var', 'median',
 and 'norm']


## Contact
For any questions, please contact: mohammed_ghaith.altarabichi@hh.se

