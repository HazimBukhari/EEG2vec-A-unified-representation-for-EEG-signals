# EEG2VEC: a unified representation for EEG signals  

# TODO:  
- [ ] Train code
- [ ] eval code
- [ ] base model
- [ ] dataloader
- [ ] supporting functioned (utils)
- [ ] config
- [x] Data collection
- [ ] Experiments
- [ ] Results analysis

# Data sources:  
- [x] [TUH](https://isip.piconepress.com/projects/nedc/html/tuh_eeg/) Contact Hazim for access or fill the form (whichever is easier for you)
  ## Motor imagery
- [ ] [Psychological and Cognitive Factors in Motor Imagery Brain Computer Interfaces](https://dataverse.nl/dataset.xhtml?persistentId=doi:10.34894/Z7ZVOD)
- [ ] [A large EEG database with users’ profile information for motor imagery brain-computer interface research](https://www.sciencedirect.com/science/article/pii/S093336572300252X)
- [ ] [An in-depth survey on Deep Learning-based Motor Imagery Electroencephalogram (EEG) classification](https://www.sciencedirect.com/science/article/pii/S093336572300252X) check table 3
  ## Brain-to-speech
- [ ] [Fourteen-channel EEG with Imagined Speech (FEIS) dataset](https://zenodo.org/records/3554128)
  ## SSVEP
- [ ] [An open dataset for human SSVEPs in the frequency range of 1-60 Hz](https://www.nature.com/articles/s41597-024-03023-7)
  ## P300
- [ ] [Brain Invaders calibration-less P300-based BCI using dry EEG electrodes Dataset (bi2014a)](https://zenodo.org/records/3266223)
- [ ] [Brain Invaders Adaptive versus Non-Adaptive P300 Brain-Computer Interface dataset](https://zenodo.org/records/2669187)
- [ ] [Building Brain Invaders: EEG data of an experimental validation](https://zenodo.org/records/2649069)

# Baselines
- [ ] EEGformer (unofficial implementation)
- [ ] EEGNet
- [ ] TBA
- [ ] TBA

# base model
- [ ] ~~steal~~ get inspired by [wav2vec2](https://github.com/facebookresearch/fairseq/blob/main/fairseq/models/wav2vec/wav2vec2.py) implementation
- [ ] ~~steal~~ get further inspiration by [wavLM](https://github.com/microsoft/unilm/blob/master/wavlm/WavLM.py) implementation
- [ ] check [moment](https://github.com/moment-timeseries-foundation-model/moment) foundation models for time-series data

# dataloader
- [ ] Implement cleaning
- [ ] remove power grid noise
- [ ] remove cardiac noise (Ask Michele for more implementation details)
- [ ] instance normalization 
- [ ] Implement augmentations
- [ ] Implement segmentation of input (overlapping vs non-overlapping)
- [ ] Implementing wavelet and stft feature extraction
- [ ] If feeling fancy play with GPUdirect by Nvidia

# Experiments:
| Expermints     | Task1 results | Task2 results   | Task3 results | avg | 
|----------------|---------------|---------------|----------------|-----------|
| preprocess/model | TBA  | TBA | TBA | TBA
| preprocess/model   | TBA  | TBA | TBA | TBA
| preprocess/model   | TBA  | TBA | TBA | TBA
| preprocess/model   | TBA  | TBA | TBA | TBA

# Extras
- [Notebook](https://github.com/BRomans/OpenCortex/blob/main/notebooks/P300_Epoching.ipynb)

# Notes
- TUH dataset
  - Channels: max 31, but could go to 20 (check which channels are present in all data point)
  - Sampling rate: 250, 256, 400, 512 Hz (resample them all to 250Hz)
  - Unique subjects: 10874 (think about splitting the data subject-wise)
  - No mention of any preprocessing (might need to remove some noise)
- SLEEP AND EAT for the love of god
