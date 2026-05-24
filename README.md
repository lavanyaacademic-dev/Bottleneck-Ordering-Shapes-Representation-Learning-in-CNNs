

<a href="https://handle.test.datacite.org/10.5072/zenodo.502245"><img src="https://sandbox.zenodo.org/badge/1241399528.svg" alt="DOI"></a>


# Bottleneck-Ordering-Shapes-Representation-Learning-in-CNNs
This work introduces the Multi-Stage Bottleneck CNN (MSB-CNN) to systematically investigate how hierarchical capacity allocation influences representation learning in convolutional neural networks.

Environment setup-
Python/PyTorch versions-
Installation commands-
Dataset download/preparation-
Training commands-
Evaluation commands-
Reproduction of figures/tables-
Bottleneck configurations-
CKA analysis scripts-
Retinal preprocessing implementation-
Hardware requirements-
Expected runtime-

# Environment Setup

Experiments were implemented using:

Python 3.10
PyTorch 2.x
Torchvision 0.x
CUDA 11.x (GPU experiments)

Recommended environment:

conda create -n msbcnn python=3.10
conda activate msbcnn


# Bottleneck Configurations
# MSB-CNN
# Configuration	Stage 1	Stage 2	Stage 3
     Tight	      4	      8	      16
     Progressive	 8     	 32	      128
     Regressive	128	      32	       8
     Wide	           32	      64	      128

     
# Bottleneck ResNet18
# Configuration	       Channels
  Progressive	         [32, 64, 128, 256]
  Regressive	         [256, 128, 64, 32]
  Uniform	             [64, 64, 64, 64]


# CKA Analysis

The repository includes scripts for:

layer-wise CKA computation
representation similarity analysis
cross-model comparison

Run:

python cka.py
msb_cnn+_resnet_+_cka_.py






# Retinal Preprocessing

The biologically inspired retinal preprocessing stage uses:

Difference-of-Gaussians filtering
center-surround contrast enhancement
spatial frequency emphasis

Implementation is provided in:


ganglion_filters.py
retinal_ganglion_cell_model.py

# Hardware Requirements

Recommended:

NVIDIA GPU (>=8GB VRAM)
CUDA-enabled environment
16GB system RAM



# Expected Runtime

Approximate runtimes:

Dataset	Model	Runtime
CIFAR-10	MSB-CNN	4–5 hours
CIFAR-100	Bottleneck ResNet18	6–8 hours
Tiny-ImageNet	Bottleneck ResNet18	10–12 hours

Runtime depends on:

GPU hardware
batch size
number of epochs

# citation
If you use this work, please cite:

@article{Lavanya_2026,
author = {Lavanya Srinivasan},
doi = {10.5072/zenodo.502246},
journal = {The Visual Computer},
title = {{Bottleneck Ordering Shapes Representation Learning in CNNs}},
year = {2026}
}
