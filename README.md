## System Configuration

- **OS:** Linux Mint
- **GPU:** NVIDIA RTX 3090 (24GB)
- **RAM:** 16GB

## TLDR:
- Mamba architecture was added to the DeepSTPP paper.
- The code was also GPU optimized.

## Neural Point Process for Learning Spatiotemporal Event Dynamics (DeepSTPP) with Mamba Application

*Mamba Abstract* Spatiotemporal point processes (STPPs) provide a principled framework for modeling irregular event sequences over continuous space and time. DeepSTPP introduced a nonparametric kernel mixture approach with latent stochastic processes and amortized inference, using Transformer-based encoders to capture event history. However, Transformer encoders suffer from quadratic scaling with sequence length and may struggle to capture long-range dependencies efficiently. In this work, we propose DeepSTPP-Mamba, replacing the Transformer encoder with the recently developed Structured State Space Sequence Model, Mamba, which enables linear-time sequence modeling via selective state space dynamics. Extensive experiments on both synthetic and real-world continuous STPP datasets show that DeepSTPP-Mamba achieves comparable or superior forecasting accuracy while improving computational scalability. Our results suggest that structured state space models provide an effective alternative to attention-based architectures for continuous-time spatiotemporal event modeling.

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

### Real-World Datasets

The table below presents results on COVID-19 NJ and Japan Earthquake datasets:

**Table 1: Real-world dataset results.**

| Model | COVID-LL | COVID-Time | JPDS-LL | JPDS-HD |
| :--- | :---: | :---: | :---: | :---: |
| Mamba | -0.1158 | 2.4564 | -4.3811 | 0.4393 |
| LSTM | -0.1489 | 2.4468 | -4.4488 | 0.3580 |
| Separate Encoders | -0.1148 | 2.4559 | -4.4011 | 0.4007 |
| Shared Decoder | -0.1093 | 2.4570 | -4.4018 | 0.4044 |
| No Sample | -0.0892 | 2.4575 | -4.4018 | 0.4044 |

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

### Synthetic Datasets

The table below summarizes results on both synthetic processes:

**Table 2: Synthetic dataset results.**

| Model | STHP-LL | STHP-HD | STSCP-LL | STSCP-HD |
| :--- | :---: | :---: | :---: | :---: |
| Mamba | -2.4772 | -0.1985 | -0.0949 | -1.3956 |
| LSTM | -2.3444 | -0.2633 | -0.1706 | -1.3876 |
| Separate Encoders | -2.4483 | -0.3751 | -0.1736 | -1.3909 |
| Shared Decoder | -3.7436 | -0.6879 | -1.0055 | -1.8314 |
| No Sample | -2.3037 | -0.1947 | -0.1173 | -1.3674 |

On STSCP, DeepSTPP-Mamba achieves the best log-likelihood, outperforming both LSTM and ablations. On STHP, LSTM slightly outperforms Mamba in LL but Mamba yields lower HD, suggesting better intensity‐surface estimation.

### Interpretation of Tables 1 and 2  
For log-likelihood (LL), higher (less negative) values indicate better model fit. For Hellinger Distance (HD), lower values reflect improved intensity estimation. Mamba achieves its largest gains on STSCP and COVID-19, while remaining competitive with LSTM on Hawkes and JPDS datasets. Across both synthetic and real-world settings, Mamba demonstrates stable and robust performance.

## Training Efficiency
While Mamba offers linear-time scaling theoretically, our datasets consist of relatively short event sequences where per-step computation cost dominates total runtime. Consequently, training throughput for Mamba is somewhat slower than LSTM due to the higher complexity of state-space updates; however, the linear-scaling benefits would emerge for longer sequences or larger datasets.


## Original Deep Spatiotemporal Point Process [[Paper](https://proceedings.mlr.press/v168/zhou22a/zhou22a.pdf)]

**Zihao Zhou, Adam Yang, Ryan Rossi, Handong Zhao, Rose Yu**

In proceedings of *Annual Conference on Learning for Dynamics and Control* (L4DC), 2022

![example](example.gif)

