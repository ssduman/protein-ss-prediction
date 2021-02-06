# Protein Secondary Structure Prediction
Prediction secondary structure just by looking amino acid sequence of proteins.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/perought/protein-ss-prediction/blob/master/protein_ss_prediction.ipynb)

## Summary: ##
* All amino acid sequences are merged
* 20 amino acid and their 3 secondary structures (E, H and t) or 8 secondary structures are used
* Sliding windows technique is used
* Tried for window size 21 and 13, best is 21 window size
* Secondary structure of middle amino acid is used for target structure
* Each amino acid in the window is translated into one-hot-encoding
* All one-hot-encoding of amino acid in the windows concatenated to get 21x20 matrix
* Each one-hot-encoding matrix interpreted as 1 channel black and white image
* Image-like input is given to model
* CNN is used
* Tried with RNN, LSTM or GRU but found little affect on accuracy 
* Trained models for predicting 3 and 8 secondary structure is under _/trained-model_ 
<img src="https://github.com/perought/protein-ss-prediction/blob/master/img/architecture.png" alt="architecture" >

## Benchmarks: ##
* Predicting 3 secondary structures: %73
* Predicting 8 secondary structures: %52

## Dependencies: ##
* PyTorch
* Pandas
* Numpy
* Matplotlib
* Seaborn
* scikit-learn
* torchsummary
* Tested on Python 3.8.3 x64

## Datasets: ##
* https://github.com/upsheroes3/dataset
* https://www.kaggle.com/alfrandom/protein-secondary-structure
* Can be ported with different datasets
