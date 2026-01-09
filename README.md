## System Configuration

- **OS:** Linux Mint
- **GPU:** NVIDIA RTX 3090 (24GB)
- **RAM:** 16GB

## TLDR:
- Mamba architecture was added to the DeepSTPP paper.
- The code was also GPU optimized.

## Visual Represenations For MAMBA Results:

### Covid NJ Dataset

<p align="center">
  <img src="notebooks/video/gifs/mamba_covidnj0_gt.gif" alt="Mamba STPP COVIDNJ0" width="32%" />
  <img src="notebooks/video/gifs/mamba_covidnj1_gt.gif" alt="Mamba STPP COVIDNJ1" width="32%" />
  <img src="notebooks/video/gifs/mamba_covidnj2_gt.gif" alt="Mamba STPP COVIDNJ2" width="32%" />
</p>

### Japanese Earthquake Dataset

<p align="center">
  <img src="notebooks/video/gifs/mamba_jpds0_gt.gif" alt="Mamba STPP Japanese Earthquake DS0" width="32%" />
  <img src="notebooks/video/gifs/mamba_jpds1_gt.gif" alt="Mamba STPP Japanese Earthquake DS1" width="32%" />
  <img src="notebooks/video/gifs/mamba_jpds2_gt.gif" alt="Mamba STPP Japanese Earthquake DS2" width="32%" />
</p>

### Spatio Temporal Hawkes Process

<p align="center">
  <img src="notebooks/video/gifs/mamba_sthp0_gt.gif" alt="Mamba STPP Hawkes Process DS0" width="32%" />
  <img src="notebooks/video/gifs/mamba_sthp1_gt.gif" alt="Mamba STPP Hawkes Process DS1" width="32%" />
  <img src="notebooks/video/gifs/mamba_sthp2_gt.gif" alt="Mamba STPP Hawkes Process DS2" width="32%" />
</p>


### Spatio Temporal Self-Correcting Process
<p align="center">
  <img src="notebooks/video/gifs/mamba_stscp0_gt.gif" alt="Mamba STPP Self-Correcting Process DS0" width="32%" />
  <img src="notebooks/video/gifs/mamba_stscp1_gt.gif" alt="Mamba STPP Self-Correcting Process DS1" width="32%" />
  <img src="notebooks/video/gifs/mamba_stscp2_gt.gif" alt="Mamba STPP Self-Correcting Process DS2" width="32%" />
</p>

## Neural Point Process for Learning Spatiotemporal Event Dynamics (DeepSTPP) with Mamba Application

*Mamba Abstract* Spatiotemporal point processes (STPPs) provide a principled framework for modeling irregular event sequences over continuous space and time. DeepSTPP introduced a nonparametric kernel mixture approach with latent stochastic processes and amortized inference, using Transformer-based encoders to capture event history. However, Transformer encoders suffer from quadratic scaling with sequence length and may struggle to capture long-range dependencies efficiently. In this work, we propose DeepSTPP-Mamba, replacing the Transformer encoder with the recently developed Structured State Space Sequence Model, Mamba, which enables linear-time sequence modeling via selective state space dynamics. Extensive experiments on both synthetic and real-world continuous STPP datasets show that DeepSTPP-Mamba achieves comparable or superior forecasting accuracy while improving computational scalability. Our results suggest that structured state space models provide an effective alternative to attention-based architectures for continuous-time spatiotemporal event modeling.

## Original Deep Spatiotemporal Point Process [[Paper](https://proceedings.mlr.press/v168/zhou22a/zhou22a.pdf)]

**Zihao Zhou, Adam Yang, Ryan Rossi, Handong Zhao, Rose Yu**

In proceedings of *Annual Conference on Learning for Dynamics and Control* (L4DC), 2022

![example](example.gif)

