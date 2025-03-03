#  Emergence of Concepts in Vision Transformers
This is the official repository for the paper "From Colors to Classes: Emergence of Concepts in Vision Transformers" by Teresa Dorszewski, Lenka Tětková, Robert Jenssen, Lars Kai Hansen, Kristoffer Knutsen Wickstrøm.

The basis of this code is from the github repo [Trustworthy-ML-Lab/CLIP-dissect](https://github.com/Trustworthy-ML-Lab/CLIP-dissect) for the paper  [CLIP-Dissect: Automatic Description of Neuron Representations in Deep Vision Networks](https://arxiv.org/abs/2204.10965) published at ICLR 2023. It was adapted to support models from huggingface and save the top activating images for each neuron. 

The labeled neuron lists for all models from our analysis can be found in the `results` folder. The concept set and categoization of concepts is in the `data` folder. 

All figures can be reproduced with the `final_figures.ipynb` and `vis_neurons.ipynb` notebook. 

## Quick guide:
### Analysing your own model

1. Add your path to the datasets and models in `data_utils.py`
2. Dissect the model by running: 
    `python describe_neurons.py --target_model {model_name} --target_layers {layers} --d_probe "imagenet_broden" --concept_set "data/20k.txt"`

You can run this with any model on huggingface, just insert the right layer names, e.g. for vit: `vit.encoder.layer[0],vit.encoder.layer[1],...`

The probing set and concept set can be changed as liked. 

*Note:* The code is written to run on GPU (with cuda), it will take very long to run on a CPU, if it even runs at all. 

### Reproducing our results

To reproduce the results saved in `results`, run `run_clipdissect.sh`. 
It requires a lot of memory, so it might be needed to split by layers. 

## Cite this work

tba