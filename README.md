# DCVD Generative Model ReadMe

## Overview

The generative model is based on VAE using TensorFlow. Scripts are at `/projects/piml_inversion/DCVD/`. Everything for training the model is in `vae.py`, including data loading and processing, model structure, training, and saving model. Python script to reconstruct is `vae_recon.py`, and to sample from latent space is `vae_gen.py`. ~~The training script with style loss is `vae_style.py`~~
(Not implemented yet)

### Update

> 03.10.2021 Add python script to reconstruct and sample from latent space. Add number of iterations to 1,000, still not converge. 

## Requirements

* Python 3
* Numpy
* PIL
* TensorFlow 1.15 (tested) or latest TensorFlow 2 (not tested)

## Training

To train VAE on Darwin using TensorFlow, using Power nodes is suggested, since GPU cannot be used when using x86 nodes with GPU. Creating environment for Power architecture in Anaconda: https://www.ibm.com/support/knowledgecenter/SS5SF7_1.6.0/navigation/pai_install.htm. Shell script for submitting jobs is `vae.sh`. Please edit the scripts accordingly, like file name, output files, job name, data folder and so on. Before submitting a job to Power node, please load anaconda module and activate the environment for power architecture. 

## ATTENTION

The model using current hyperparameters cannot converge! Maybe more iterations or smaller learning rate is needed, but may lead to overfitting. 
