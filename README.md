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
- [ ] generate train/test data CVSs
- [ ] Literature Review

# Data sources:  
- [x] [TUH](https://isip.piconepress.com/projects/nedc/html/tuh_eeg/) Contact Hazim for access or fill the form (whichever is easier for you)
  ## Motor imagery 
- [x] [Psychological and Cognitive Factors in Motor Imagery Brain Computer Interfaces](https://www.frontiersin.org/journals/human-neuroscience/articles/10.3389/fnhum.2021.634748/full) | [Download](https://dataverse.nl/dataset.xhtml?persistentId=doi:10.34894/Z7ZVOD)
- [x] [A large EEG database with users’ profile information for motor imagery brain-computer interface research](https://www.nature.com/articles/s41597-023-02445-z) | [Downlaod](https://zenodo.org/records/8089820)
- [ ] [An in-depth survey on Deep Learning-based Motor Imagery Electroencephalogram (EEG) classification](https://www.sciencedirect.com/science/article/pii/S093336572300252X) check table 3 | [Download](https://www.bbci.de/competition/) (Did not download. too small)
  ## Brain-to-speech
- [x] Fourteen-channel EEG with Imagined Speech (FEIS) dataset | [Downlaod](https://zenodo.org/records/3554128) | [Github](https://github.com/scottwellington/FEIS)
  ## SSVEP
- [x] [An open dataset for human SSVEPs in the frequency range of 1-60 Hz](https://www.nature.com/articles/s41597-024-03023-7) | [Downlaod](https://figshare.com/articles/dataset/An_open_dataset_for_human_SSVEPs_in_the_frequency_range_of_1-60_Hz/23641017)
  ## P300 
- [x] [Brain Invaders calibration-less P300-based BCI using dry EEG electrodes Dataset (bi2014a)](https://hal.science/hal-02171575) | [Download](https://zenodo.org/records/3266223) | [Github](https://github.com/plcrodrigues/py.BI.EEG.2014a-GIPSA)
- [x] [Brain Invaders Adaptive versus Non-Adaptive P300 Brain-Computer Interface dataset](https://hal.archives-ouvertes.fr/hal-02103098) | [Doownload](https://zenodo.org/records/2669187) | [Github](https://github.com/plcrodrigues/py.BI.EEG.2013-GIPSA)
- [x] [Building Brain Invaders: EEG data of an experimental validation](https://hal.archives-ouvertes.fr/hal-02126068) | [Download](https://zenodo.org/records/2649069) | [Github](https://github.com/plcrodrigues/py.BI.EEG.2012-GIPSA)

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
- [ ] remove power grid noise
- [ ] remove cardiac noise (Ask Michele for more implementation details)
- [ ] instance normalization 
- [ ] Implement augmentations
- [ ] Implement segmentation of input (overlapping vs non-overlapping)
- [ ] Implementing wavelet, stft, MFCC feature extraction
- [ ] Implementing additional feature extraction methods
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

# Datasets Descriptions
- TUH dataset
  - Channels: max 31, but could go to 20 (check which channels are present in all data point)
  - Sampling rate: 250, 256, 400, 512 Hz (resample them all to 250Hz)
  - Unique subjects: 10874 (think about splitting the data subject-wise)
  - Preprocess: No mention of any preprocessing (might need to remove some noise)
  - Downstream tasks:
    -  Detecting normal\abnormal EEG signals
    -  Artifacts detection (eye movement, chewing, shivering, electrode pop/static & lead artifacts, muscle artifacts)
    -  Epilepsy detection
    -  Seizure (start time, stop , channel & seizure type)
    -  Slowing event detection

-  Psychological and Cognitive Factors in Motor Imagery Brain-Computer Interfaces dataset
  - Channels: 16 (F3, Fz, F4, FC1, FC5, FC2, FC6, C3, Cz, C4, CP1, CP5, CP2, CP6, T7, and T8) A reference electrode was set on the right earlobe and a ground electrode on AFz
  - Sampling rate: 250 Hz
  - Unique subjects: 55 (think about splitting the data subject-wise)
  - Preprocess: EEG signals were amplified by a g.Nautilus amplifier (g.tec Medical Engineering, Austria). A 48-52 Hz Notch filter and 0.5-30 Hz bandpass filter were applied to reduce the noise in the data.
  - Downstream tasks:
    -  Motor-imagery BCIs (MI-BCI): mental imagination of body movements
  
-  A large EEG database with users’ profile information for motor imagery brain-computer interface research dataset
  - Channels: 27 (Fz, FCz, Cz, CPz, Pz, C1, C3, C5, C2, C4, C6, F4, FC2, FC4, FC6, CP2, CP4, CP6, P4, F3, FC1, FC3, FC5, CP1, CP3, CP5, P3) referenced to the left earlobe, the ground electrode is placed in FPz position
  - Sampling rate: 512
  - Unique subjects: 87
  - Preprocess: None mentioned (recheck again)
  - Measuring device: g.USBAmp (g.tec, Austria)
  - Note: For Dataset A the EOG signals of the right eye were recorded, and then due to a change in the layout of the experimental room, in Dataset B the EOG signals of the left eye were recorded.
  - Downstream tasks:
    -  Motor-imagery BCIs (MI-BCI): mental imagination of body movements

-  Fourteen-channel EEG with Imagined Speech (FEIS) dataset
  - Channels: 14 (F3 FC5 AF3 F7 T7 P7 O1 O2 P8 T8 F8 AF4 FC6 F4)
  - Sampling rate: TBA
  - Unique subjects: 21
  - Preprocess: None mentioned (recheck again)
  - Measuring device: Neuroscan Synamps2 
  - Downstream tasks:
    - phoneme classification

-  An open dataset for human SSVEPs in the frequency range of 1-60 Hz dataset
  - Channels: 64 ( international 10/20 system), with the reference electrode at the vertex and the electrode impedance always kept below 20 K ohm
  - Sampling rate: 1000
  - Unique subjects: 30
  - Preprocess:  A built-in 50 Hz notch filter was used to eliminate power line noise, and the band-pass filter was set from 0.1 Hz to 100 Hz to preserve wideband spectral characteristics. These filtering procedures were already incorporated during the data acquisition process.
  - Downstream tasks:
    - Good question my man

-  Brain Invaders calibration-less P300-based BCI using dry EEG electrodes Dataset (bi2014a) dataset
  - Channels: 16 (Fp1, Fp2, F5, AFZ, F6, T7, Cz, T8, P7, P3 , PZ, P4 , P8, O1, Oz, O2) with reference electrode on the right earlobe and ground electrode at the FZ scalp location.  10-10 international system.
  - Sampling rate: 512
  - Unique subjects: 71
  - Preprocess: None mentioned (recheck again)
  - Measuring device: g.USBamp, g.tec, Schiedlberg, Austria) equipped with 16 dry 8-pins 
  - Downstream tasks:
    -  P300 36 symbols (1 Target, 35 Non-Target)

-  Brain Invaders Adaptive versus Non-Adaptive P300 Brain-Computer Interface dataset
  - Channels: 16 (re FP1, FP2, F5, AFZ, F6, T7, CZ, T8, P7, P3, PZ, P4, P8, O1, OZ and O2) The reference was placed on the left earlobe and the ground at the FZ scalp location. 10-20 international system
  - Sampling rate: 512
  - Unique subjects: 24
  - Preprocess: None mentioned (recheck again)
  - Measuring device: (g.USBamp, g.tec, Schiedlberg, Austria) and the g.GAMMAcap (g.tec, Schiedlberg, Austria) equipped with 16 wet Silver/Silver Chloride electrodes
  - Downstream tasks:
    - P300 36 symbols (1 Target, 35 Non-Target)

-  Building Brain Invaders: EEG data of an experimental validation dataset
  - Channels: 16 (e F7, F3, F4, F8, T7, C3, CZ, C4, T8, P7, P3, PZ, P4, P8, O1 and O2). The ground was placed at the FZ scalp location. 10-20 international system.
  - Sampling rate: 128
  - Unique subjects: 25
  - Preprocess:
  - Measuring device: NeXus-32 (MindMedia, Herten, Germany), a research-grade amplifier and EEG headset. The cap was equipped with 16 Silver/Silver Chloride wet electrodes. It does not
use an electrode as reference, rather, a, hardware common average reference is used.
  - Note: Note that the tagging process introduces a jitter and a latency which artificially modify the ERPs onset. These belong to the hardware and software components of the
experiment. In particular, a disadvantage of software tagging is a strong drift over time, resulting in higher jitter (2,13). As a consequence, it is only possible to compare the ERP acquired within the same experimental conditions when the latency is not corrected.
  - Downstream tasks:
    - P300 36 symbols (1 Target, 35 Non-Target)
        

- SLEEP AND EAT for the love of god
