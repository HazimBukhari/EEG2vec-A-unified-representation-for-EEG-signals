# EEG2VEC: A unified representation for EEG signals  

This project explores an end-to-end masked prediction, a self-supervised foundation model for EEG that learns unified representations transferable to any downstream task without task-specific fine-tuning. 

## Results 

<p align="left">
  <a href="https://drive.google.com/file/d/1u8bEVWO1eJZF72DPtHYrFqi5dyHEDno1/view?usp=sharing" target="_blank">
    <img src="https://img.shields.io/badge/View%20Final%20Report-blue?style=for-the-badge" alt="View Final Report">
  </a>
</p>

## Codebase

- [`HuBERT`](./HuBERT): Code to run HuBERT models
- [`SVM`](./SVM):  Code to run SVM models
- [`sep-CNN`](./sep-CNN): Code to run Separable Convolutional 1D Network baseline
- [`GNN`](./GNN): Code to run GNN models (we need to create this folder and put all Mayur's code)

## Experiments to-do list 

- [x] Data collection:
  - [x] TUH
  - [x] BNCI2014-009
        
- [x] Create baselines:
  - [x] SVM
  - [x] Separable Convolutional 1D Network
  - [x] Graph Neural Network
        
- [x] HuBERT:
  - [x] setup HuBERT
  - [x] Make necessary changes to adapt to EEG
        
- [x] Preprocess:
  - [x] chunk signal and extract features from EEG (TUH)
  - [x] split on training and evaluation based on subject (TUH)
  - [x] train k-means (TUH)
  - [x] create clusters (TUH)
  - [x] prepare BNCI2014-009 for downstream task evaluation
     
- [x] Training baselines:
  - [x] SVM
  - [x] Separable Convolutional 1D Network
  - [x] Graph Neural Network
     
- [x] HuBERT experiments:
  - [x] MultiChannel (17 channels input)
  - [x] superimposing of the signal (summing channels to 1 channel)
      
The project is completed as a part of [CMU 11-785: Introduction to Deep Learning](https://deeplearning.cs.cmu.edu/S25/index.html).
