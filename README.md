<img width="1200" alt="dropkan_explained" src="https://github.com/Ghaith81/dropkan/blob/master/DropKAN_explained.JPG">


# Dropout Kolmogorov-Arnold Networks (DropKAN) 

This is the github repository for the paper: ["DropKAN: Regularizing KANs by masking post-activations"](https://arxiv.org/abs/2407.13044). DropKAN operates by randomly masking some of the post-activations within the KANs computation graph, while scaling-up the retained post-activations.

## How to use

The DropKAN model can be used similar to KAN to create a model of DropKANLayers. Three parameters are needed with DropKAN:

- drop_rate: A list of floats of the rate of drops for the DropKAN mask. E.g., for the DropKAN model [6, 10, 1], drop_rate could be [0.1, 0.2], indicating a 0.1 drop_rate for the 6x10 activations between layers 0 and 1, and 0.2 drop_rate for the 10x1 activations between layers 1 and 2.
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

## Contact
For any questions, please contact: mohammed_ghaith.altarabichi@hh.se

