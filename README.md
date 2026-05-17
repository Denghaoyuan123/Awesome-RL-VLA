# Awesome RL-VLA for Robotic Manipulation 🤖
**[[Paper](https://www.techrxiv.org/users/934012/articles/1366553-a-survey-on-reinforcement-learning-of-vision-language-action-models-for-robotic-manipulation?commit=a7c4cf9ff94956e6d3c7f6eb1ff10a6eb2fc05e4)]**

A curated list of papers and resources on **Reinforcement Learning of Vision-Language-Action (RL-VLA)** models for Robotic Manipulation. This repository provides a comprehensive overview of training paradigms, methodologies, and state-of-the-art approaches in RL-VLA research.

## 📢 Latest News

> 🔥 **[November 2025]** Our comprehensive survey paper **"A Survey on Reinforcement Learning of Vision-Language-Action Models for Robotic Manipulation"** is now available on [TechRxiv](https://doi.org/10.36227/techrxiv.176531955.54563920/v1)! Stay tuned for future updates.
> 

## 📖 Table of Contents
- [Awesome RL-VLA for Robotic Manipulation 🤖](#awesome-rl-vla-for-robotic-manipulation-)
  - [📢 Latest News](#-latest-news)
  - [📖 Table of Contents](#-table-of-contents)
  - [🔍 Overview](#-overview)
  - [🚀 Training Paradigms](#-training-paradigms)
    - [Offline RL-VLA](#offline-rl-vla)
    - [Online RL-VLA](#online-rl-vla)
    - [Test-time RL-VLA](#test-time-rl-vla)
  - [📚 Paper Collection](#-paper-collection)
    - [Legend](#legend)
    - [Offline RL-VLA](#offline-rl-vla-1)
    - [Online RL-VLA](#online-rl-vla-1)
    - [Offline + Online RL-VLA](#offline--online-rl-vla)
    - [Test-time RL-VLA](#test-time-rl-vla-1)
  - [🔗 Useful Resources](#-useful-resources)
    - [🎯 RL-VLA Action Optimization](#-rl-vla-action-optimization)
    - [Base VLA Models](#base-vla-models)
    - [Datasets \& Benchmarks](#datasets--benchmarks)
    - [Frameworks \& Tools](#frameworks--tools)
  - [🤝 Contributing](#-contributing)
    - [Contribution Guidelines](#contribution-guidelines)
  - [📄 Citation](#-citation)
  - [⭐ Star History](#-star-history)

## 🔍 Overview

RL training is crucial for enabling VLAs to generalize out-of-distribution (OOD) from large-scale pre-trained data. Existing RL-VLA training paradigms can be categorized into three types based on how agents obtain and utilize feedback from the environment:

- **Online RL-VLA**: Direct interaction with the environment during training
- **Offline RL-VLA**: Learning from static datasets without further environmental interaction  
- **Test-time RL-VLA**: Models adapt their behavior during deployment without altering parameters

## 🚀 Training Paradigms

### Offline RL-VLA

Offline RL trains VLA models on pre-collected static datasets, enabling learning independently from environment interactions. This paradigm is suitable for high-risk or resource-constrained deployment scenarios.

**Key Research Directions:**
- **Data Utilization**: Effective utilization of static datasets for policy improvement
- **Objective Modification**: Customizing RL objectives for novel architectures and data augmentation

### Online RL-VLA

Online RL-VLA enables interactive policy learning through continuous environment interaction, empowering pre-trained VLAs with adaptive closed-loop control capability for real-world OOD environments.

**Key Research Directions:**
- **Policy Optimization**: Direct policy improvement based on environmental rewards
- **Sample Efficiency**: Learning effective policies with limited interaction budget
- **Active Exploration**: Efficient exploration strategies for higher performance gains
- **Training Stability**: Ensuring consistent policy updates and convergence
- **Infrastructure**: Scalable frameworks for online RL-VLA training

### Test-time RL-VLA

Test-time RL-VLA adapts behavior during deployment through lightweight updates, addressing the expensive cost of full model fine-tuning in real-world scenarios.

**Key Adaptation Mechanisms:**
- **Value Guidance**: Using pre-trained value functions to influence action selection
- **Memory Buffer Guidance**: Retrieving relevant historical experiences during inference
- **Planning-guided Adaptation**: Explicit reasoning over future action sequences

## 📚 Paper Collection

### Legend
- **Action**: AR (Autoregressive), Diffusion, Flow (Flow-matching)
- **Reward**: D (Dense Reward), S (Sparse Reward)
- **Model Type**: MB (Model-based), MF (Model-free)
- **Environment**: Sim. (Simulation), Real (Real-world)
- **Task**: MT (Multi-task), ST (Single-task)
- **Policy**: On-Policy, Off-Policy, Hybrid (mixed on/off-policy), Test-time (inference-time adaptation)

### Offline RL-VLA

| Method | Date | Publication | Sim. | Real | Base VLA Model | Action | Reward | Algorithm | Policy | Type | Project |
|--------|------|-------------|------|------|----------------|--------|--------|-----------| --- |------|---------|
| [Q-Transformer](https://arxiv.org/abs/2309.10150) | 2023.10 | CoRL23[🔗](https://proceedings.mlr.press/v229/chebotar23a.html) | ✓ | ✗ | Transformer | AR | S | CQL | Off-Policy | MF | [🔗](https://qtransformer.github.io/) |
| [PAC](https://arxiv.org/abs/2402.05546) | 2024.02 | ICML24[🔗](https://proceedings.mlr.press/v235/springenberg24a.html) | ✓ | ✓ | Perceiver-Actor-Critic | AR | S | AC | Off-Policy | MF | [🔗](https://sites.google.com/view/perceiver-actor-critic) |
| [GeRM](https://arxiv.org/pdf/2403.13358)(Quadruped Robot) | 2024.03 | IROS24[🔗](https://ieeexplore.ieee.org/document/10801816) | ✓ | ✗ | Transformer-MoE | AR | S | CQL | Off-Policy | MF | [🔗](https://songwxuan.github.io/GeRM/) |
| [MoRE](https://arxiv.org/pdf/2503.08007)(Quadruped Robot) | 2025.03 | ICRA25[🔗](https://ieeexplore.ieee.org/document/11128601) | ✗ | ✓  | MLLM-MoE | AR | S | CQL | Off-Policy | MF |  -  |
| [ReinboT](https://icml.cc/virtual/2025/poster/45523) | 2025.05 | ICML25[🔗](https://icml.cc/virtual/2025/poster/45523) | ✓ | ✓ | ReinboT | AR | D | DT + RTG | Off-Policy | MF | [🔗](https://github.com/COST-97/reinboT) |
| [CO-RFT](https://arxiv.org/pdf/2508.02219) | 2025.08 | - | ✗ | ✓ | RoboVLMs | AR | D | Cal-QL + TD3 | Off-Policy | MF | - |
| [ARFM](https://arxiv.org/pdf/2509.04063) | 2025.09 | AAAI26[🔗](https://ojs.aaai.org/index.php/AAAI/article/view/38944) | ✓ | ✓ | π₀ | Flow | D | ARFM | Off-Policy | MF | - |
| [$π^*_{0.6}$](https://arxiv.org/abs/2511.14759) | 2025.11 | - | ✗ | ✓ | $π_{0.6}$ | Flow | D | RECAP | Off-Policy | MF | [🔗](https://www.pi.website/blog/pistar06) |
| [NORA-1.5](https://arxiv.org/pdf/2511.14659) | 2025.11 | - | ✓ | ✓ | NORA-1.5 | AR / Flow | D | DPO | Off-Policy | MB | [🔗](https://declare-lab.github.io/nora-1.5) |
| [GigaBrain-0.5M*](https://arxiv.org/pdf/2602.12099) | 2026.2 | - | ✗ | ✓ | GigaBrain-0.5 | Flow | D | RAMP | Off-Policy | MB | [🔗](https://gigabrain05m.github.io/) |
| [ARM](https://arxiv.org/pdf/2604.03037) | 2026.4 | - | ✗ | ✓ | GR00T N1.5 | Flow | D | AW-BC | Off-Policy | MF | [🔗](https://aiming1998.github.io/ARM/) |


### Online RL-VLA

| Method | Date | Publication | Sim. | Real | Base VLA Model | Action | Reward | Algorithm | Policy | Type | Project |
|--------|------|-------------|------|------|----------------|--------|--------|-----------| --- |------|---------|
| [FLaRe](https://arxiv.org/abs/2409.16578) | 2024.09 | ICRA25[🔗](https://ieeexplore.ieee.org/document/11127934) | ✓ (ST)| ✓ (ST)| SPOC | AR | S | PPO | On-Policy | MF | [🔗](https://github.com/JiahengHu/FLaRe) |
| [PA-RL](https://arxiv.org/abs/2412.06685) | 2024.12 | ICLR25 Workshop[🔗](https://iclr.cc/virtual/2025/10000710) | ✓ (ST)| ✓ (ST)| OpenVLA | AR | S | PA-RL | Off-Policy | MF | [🔗](https://policyagnosticrl.github.io/) |
| [RLDG](https://arxiv.org/pdf/2412.09858) | 2024.12 | RSS25[🔗](https://www.roboticsproceedings.org/rss21/p028.pdf) | ✗ | ✓ (ST)| OpenVLA / Octo | AR / Diffusion | S | RLPD | Off-Policy | MF | [🔗](https://generalist-distillation.github.io/) |
| [iRe-VLA](https://arxiv.org/abs/2501.16664) | 2025.01 | ICRA25[🔗](https://ieeexplore.ieee.org/document/11127299) | ✓ (MT)| ✓ (MT)| iRe-VLA | AR | S | SACfD + SFT | Off-Policy | MF | - |
| [GRAPE](https://arxiv.org/pdf/2411.19309) | 2025.02 | ICRA25 Poster[🔗](https://openreview.net/forum?id=W64vwmZHdK) | ✓ (MT)| ✓ (MT)| OpenVLA | AR | D | TPO | On-Policy | MF | [🔗](https://github.com/aiming-lab/grape) |
| [SafeVLA](https://arxiv.org/abs/2503.03480) | 2025.03 | NeurIPS25 Poster[🔗](https://neurips.cc/virtual/2025/loc/san-diego/poster/116975) | ✓ (ST)| ✗ | SPOC | AR | S | PPO | On-Policy | MF | [🔗](https://sites.google.com/view/pku-safevla) |
| [RIPT-VLA](https://arxiv.org/abs/2505.17016) | 2025.05 | - | ✓ (MT)| ✗ | QueST / OpenVLA-OFT | AR | S | LOOP | On-Policy | MF | [🔗](https://ariostgx.github.io/ript_vla/) |
| [VLA-RL](https://arxiv.org/abs/2505.18719) | 2025.05 | - | ✓ (MT)| ✗ | OpenVLA | AR | D | PPO | On-Policy | MF | [🔗](https://github.com/GuanxingLu/vlarl) |
| [RLVLA](https://arxiv.org/abs/2505.19789) | 2025.05 | NeurIPS25 Poster[🔗](https://neurips.cc/virtual/2025/loc/san-diego/poster/115842) | ✓ (MT)| ✗ | OpenVLA | AR | S | PPO / GRPO / DPO | Hybrid | MF | [🔗](https://github.com/gen-robot/RL4VLA) |
| [RFTF](https://arxiv.org/abs/2505.19767) | 2025.05 | - | ✓ (MT)| ✗ | GR-MG, Seer | AR | D | PPO | On-Policy | MF | - |
| [TGRPO](https://arxiv.org/abs/2506.08440) | 2025.06 | - | ✓ (ST)| ✗ | OpenVLA | AR | D | GRPO | On-Policy | MF | - |
| [RLRC](https://arxiv.org/pdf/2506.17639) | 2025.06 | - | ✓ (MT)| ✗ | OpenVLA | AR | S | PPO | On-Policy | MF | [🔗](https://rlrc-vla.github.io/) |
| [ThinkAct](https://arxiv.org/abs/2507.16815) | 2025.07 | NeurIPS25 Poster[🔗](https://neurips.cc/virtual/2025/loc/san-diego/poster/119747) | ✓  (MT)| ✗ | MLLM + DiT | AR / Diffusion | D | GRPO (System 2) | On-Policy | MF | [🔗](https://jasper0314-huang.github.io/thinkact-vla/) |
| [DiffusionRL-VLA](https://arxiv.org/abs/2509.19752v2) | 2025.9 | - | ✓ | ✗ | π₀ | Flow | S | PPO(DP) + BC(VLA)  | On-Policy | MF | - |
| [SimpleVLA-RL](https://arxiv.org/pdf/2509.09674) | 2025.09 | ICLR26 Poster[🔗](https://openreview.net/forum?id=TQhSodCM4r) | ✓ (MT)| ✓ (ST)| OpenVLA-OFT | AR | S | GRPO | On-Policy | MF | [🔗](https://github.com/PRIME-RL/SimpleVLA-RL) |
| [Dual-Actor FT](https://arxiv.org/pdf/2509.13774) | 2025.09 | IROS25 Workshop Extended Abstract[🔗](https://sites.google.com/view/hil-daft/) | ✓ (MT)| ✓ (MT)| Octo / SmolVLA | Diffusion | S | QL + BC | Off-Policy | MF | [🔗](https://sites.google.com/view/hil-daft/) |
| [Generalist](https://arxiv.org/pdf/2509.15155) | 2025.09 | NeurIPS25 Poster[🔗](https://neurips.cc/virtual/2025/loc/san-diego/poster/118633) | ✓ (MT)| ✓ (MT)| PaLI 3B | AR | D | REINFORCE | On-Policy | MF | [🔗](https://self-improving-efms.github.io./) |
| [VLAC](https://arxiv.org/abs/2509.15937) | 2025.09 | - | ✗ | ✓ (MT)| VLAC | AR | D | PPO | On-Policy | MF | [🔗](https://github.com/InternRobotics/VLAC) |
| [Robo-Dopamine](https://arxiv.org/abs/2512.23703) | 2025.12 | CVPR26[🔗](https://robo-dopamine.github.io/) | ✓ (MT)| ✓ (MT)| Pi0.5 | Flow | D | PPO | On-Policy | MF | [🔗](https://github.com/FlagOpen/Robo-Dopamine) |
| [AC PPO](https://arxiv.org/pdf/2509.25718) | 2025.09 | - | ✓ (ST)| ✗ | Octo-small | AR | S | PPO+BC | On-Policy | MF | - |
| [VLA-RFT](https://arxiv.org/abs/2510.00406) | 2025.10 | - | ✓ (MT)| ✗ | VLA-Adapter | Flow | D | GRPO | On-Policy | MB | [🔗](https://vla-rft.github.io/) |
| [RLinf-VLA](https://arxiv.org/pdf/2510.06710v1) | 2025.10 | - | ✓ (MT)| ✓ (MT)| OpenVLA / OpenVLA-OFT | AR | S | PPO / GRPO | On-Policy | MF | [🔗](https://github.com/RLinf/RLinf) |
| [FPO](https://arxiv.org/pdf/2510.09976) | 2025.10 | - | ✓ (MT)| ✗ | π₀ | Flow | S | FPO | On-Policy | MF | - |
| [ReSA](https://arxiv.org/pdf/2510.12710) | 2025.10 | - | ✓ (MT)| ✗ | OpenVLA | AR | D | PPO + SFT | On-Policy | MF | - |
| [π_RL](https://arxiv.org/abs/2510.25889) | 2025.10 | - | ✓ (MT)| ✗ | π₀ / π₀.₅ | Flow | S | PPO / GRPO | On-Policy | MF | [🔗](https://github.com/RLinf/RLinf) |
| [PLD](https://arxiv.org/abs/2511.00091) | 2025.10 | ICLR26 Poster[🔗](https://iclr.cc/virtual/2026/poster/10008318) | ✓ (MT)| ✓ (MT)| OpenVLA / π₀ / Octo | AR / Flow | S | Cal-QL + SAC | Off-Policy | MF | [🔗](https://www.wenlixiao.com/self-improve-VLA-PLD) |
| [DeepThinkVLA](https://arxiv.org/abs/2511.15669) | 2025.10 | - | ✓ (MT)| ✗ | π₀-Fast | AR | S | GRPO | On-Policy | MF | [🔗](https://github.com/wadeKeith/DeepThinkVLA) |
| [World-Env](https://arxiv.org/abs/2509.24948) | 2025.11 | - | ✓ (ST)| ✓ (ST)| OpenVLA-OFT | AR | D | PPO | On-Policy | MB | [🔗](https://github.com/amap-cvlab/world-env) |
| [RobustVLA](https://arxiv.org/pdf/2511.01331) | 2025.11 | - | ✓ (MT)| ✗ | OpenVLA-OFT | AR | D | PPO | On-Policy | MF | - |
| [WMPO](https://arxiv.org/abs/2511.09515) | 2025.11 | ICLR26 Poster[🔗](https://iclr.cc/virtual/2026/poster/10007263) | ✓ (MT)| ✓ (MT)| OpenVLA-OFT | AR | S | GRPO | On-Policy | MB | [🔗](https://wm-po.github.io/) |
| [ProphRL](https://arxiv.org/abs/2511.20633v1) | 2025.11 | - | ✓ (ST)| ✓ (ST)| VLA-Adapter / π0.5 / OpenVLA-OFT(flow action) | Flow | S | FA-GRPO | On-Policy | MB | [🔗](https://logosroboticsgroup.github.io/ProphRL) |
| [EVOLVE-VLA](https://arxiv.org/pdf/2512.14666) | 2025.12 | - | ✓ (MT)| ✗ |  OpenVLA-OFT | AR | D | GRPO | On-Policy | MB(VLAC) | [🔗](https://showlab.github.io/EVOLVE-VLA) |
| [SOP](https://arxiv.org/abs/2601.03044v1) | 2026.1 | - | ✗ | ✓ (MT)| π0.5 | Flow | S | HG-DAgger / RECAP | Off-Policy | MF | [🔗](https://www.agibot.com/research/sop) |
| [Green-VLA](https://arxiv.org/abs/2602.00919) | 2026.1 | - | ✓ (MT)| ✓ (MT)| Green-VLA | Flow | S | IQL + actor-critic | Off-Policy | MF | [🔗](https://github.com/greenvla/GreenVLA) |
| [SA-VLA](https://arxiv.org/abs/2602.00743) | 2026.1 | - | ✓ (MT)| ✗ | π0.5 | Flow | D | PPO | On-Policy | MF | [🔗](https://github.com/TwSphinx54/SA-VLA) |
| [E2HiL](https://arxiv.org/abs/2601.19969) | 2026.1 | - | ✗ | ✓ (MT) | Octo | Diffusion | S | RLPD | Off-Policy | MF | [🔗](https://e2hil.github.io/) |
| [World-Gymnast](https://arxiv.org/abs/2602.02454) | 2026.2 | ICLR26 Workshop[🔗](https://openreview.net/forum?id=N3jMxWfJlb) | ✓ (MT)| ✓ (MT)| OpenVLA-OFT | AR | S | GRPO | On-Policy | MB | [🔗](https://world-gymnast.github.io) |
| [RL-VLA3](https://arxiv.org/abs/2602.05765) | 2026.2 | ICLR26 Workshop[🔗](https://openreview.net/forum?id=IWS9pJKnlI) | ✓ (MT)| ✗ | π0 / π0.5 / GR00T N1.5 / OpenVLA-OFT | Flow / AR | S| PPO / GRPO | On-Policy | MF | — |
| [World-VLA-Loop](https://arxiv.org/abs/2602.06508) | 2026.2 | - | ✓ (ST)| ✓ (ST)| OpenVLA-OFT | AR | S | GRPO | On-Policy | MB | [🔗](https://showlab.github.io/World-VLA-Loop/) |
| [RISE](https://arxiv.org/abs/2602.11075) | 2026.2 | - | ✗ | ✓ (ST)| π0.5 | Flow | D | RISE | On-Policy | MB | [🔗](https://opendrivelab.com/kai0-rl/) |
| [WoVR](https://arxiv.org/abs/2602.13977) | 2026.2 | - | ✓ (MT)| ✓ (MT)| OpenVLA-OFT | AR | S | GRPO | On-Policy | MB | [🔗](https://github.com/RLinf/RLinf) |
| [ALOE](https://arxiv.org/abs/2602.12691) | 2026.2 | - | ✗ | ✓ (ST)| π₀.₅ | Flow | S | AWR(Advantage-Weighted Regression) | Off-Policy | MF | [🔗](https://rooshy-yang.github.io/) |
| [TwinRL-VLA](https://arxiv.org/abs/2602.09023) | 2026.2 | - | ✗ | ✓ (ST)| Octo | Diffusion | S | Actor-Critic | Off-Policy | MF | — |
| [RL-Co](https://arxiv.org/abs/2602.12628) | 2026.3 | - | ✓ (ST)| ✓ (ST)| OpenVLA / π0.5 | AR / Flow | D |  ReinFlow / GRPO | On-Policy | MF | — |
| [π_StepNFT](https://arxiv.org/abs/2603.02083) | 2026.3 | - | ✓ (MT)| ✗ | π₀ / π₀.₅ | Flow | S | NFT | On-Policy | MF | [🔗](https://github.com/wangst0181/pi-StepNFT) |
| [ROBOMETER](https://arxiv.org/abs/2603.02115) | 2026.3 | - | ✗ | ✓ (MT)| π₀ | Flow | D | DSRL | Off-Policy | MF | [🔗](https://robometer.github.io/) |
| [AtomVLA](https://arxiv.org/abs/2603.08519) | 2026.3 | - | ✓ (MT) | ✓ (ST)| AtomVLA | Flow | D | GRPO | On-Policy | MB | — |
| [NS-VLA](https://arxiv.org/abs/2603.09542) | 2026.3 | - | ✓ (MT)| ✗ | NS-VLA | AR | D | GRPO | On-Policy | MF | [🔗](https://github.com/Zuzuzzy/NS-VLA) |
| [Gen3D-RL-VLA](https://arxiv.org/abs/2603.18532) | 2026.03 | - | ✓(MT) | ✓(MT) | π₀.₅ | Flow | S | PPO | On-Policy | MB | - |
| [Simple Recipe Works](https://arxiv.org/abs/2603.11653) | 2026.03 | - | ✓(MT) | ✗ | OpenVLA-OFT / π₀ / π₀-Fast | AR / Flow | S | PPO | On-Policy | MF | [🔗](https://github.com/UT-Austin-RobIn/continual-vla-rl) |
| [RoboAlign](https://arxiv.org/abs/2603.21341) | 2026.03 | - | ✓(MT) | ✓(MT) | MLLM + Diffusion | AR | D | GRPO | On-Policy | MF | - |
| [SmoothVLA](https://arxiv.org/abs/2603.13925) | 2026.03 | - | ✓(MT) | ✗ | OpenVLA-OFT | AR | D | GRPO | On-Policy | MF | - |
| [AcceRL](https://arxiv.org/abs/2603.18464) | 2026.03 | - | ✓(MT) | ✗ | OpenVLA-OFT | AR | S | PPO | On-Policy | MB | [🔗](https://github.com/distanceLu/AcceRL) |
| [VLA-MBPO](https://arxiv.org/abs/2603.20607) | 2026.03 | - | ✓(MT) | ✓(MT) | π₀ / OpenVLA | Flow / AR | S | MBPO | On-Policy | MB | - |
| [VLA-OPD](https://arxiv.org/abs/2603.26666) | 2026.03 | - | ✓(MT) | ✗ | OpenVLA-OFT | AR | D | OPD | On-Policy | MF | - |
| [OmniVLA-RL](https://arxiv.org/abs/2604.17706) | 2026.04 | - | ✓(MT) | ✗ | OmniVLA-RL (MoT) | Flow | D | Flow-GSPO | On-Policy | MF | - |
| [VLAJS](https://arxiv.org/abs/2604.13733) | 2026.04 | - | ✓(MT) | ✓(ST) | VLA-guided RL agent | AR | S | PPO | On-Policy | MF | - |
| [DAERT](https://arxiv.org/abs/2604.05595) | 2026.04 | - | ✓(MT) | ✗ | π₀ / OpenVLA | AR / Flow | S | Diversity-aware RL | On-Policy | MF | - |
| [RL Token](https://arxiv.org/abs/2604.23073) | 2026.04 | - | ✗ | ✓(ST) | π₀.₅ | Flow | D | RLPD | Off-Policy | MF | [🔗](https://www.pi.website/download/rlt.pdf) |
| [LaST-R1](https://arxiv.org/abs/2604.28192) | 2026.04 | - | ✓(MT) | ✗ | LaST-R1 | AR | D | LAPO | On-Policy | MF | - |


### Offline + Online RL-VLA

| Method | Date | Publication | Sim. | Real | Base VLA Model | Action | Reward | Algorithm | Policy | Type | Project |
|--------|------|-------------|------|------|----------------|--------|--------|-----------| --- |------|---------|
| [ConRFT](https://arxiv.org/pdf/2502.05450) | 2025.4 | RSS26[🔗](https://roboticsconference.org/program/papers/19/) | ✗ | ✓(MT) | Octo-small | Diffusion | S | Cal-QL + BC | Off-Policy | MF | [🔗](https://github.com/cccedric/conrft) |
| [SRPO](https://arxiv.org/abs/2511.15605) | 2025.11 | - | ✓(MT) | ✓(MT) | OpenVLA* / π₀ / π₀-Fast | AR / Flow | D | SRPO | Hybrid | MF (MB-Reward but MF-RL) | [🔗](https://github.com/sii-research/siiRL) |
| [DLR](https://arxiv.org/abs/2511.19528) | 2025.11 | - | ✓ | ✗ | π₀ / OpenVLA | Flow / AR | S | PPO(MLP) + SFT(VLA)  | On-Policy | MF | - |
| [GR-RL](https://arxiv.org/abs/2512.01801) | 2025.12 | - | ✗ | ✓ | GR-3 | Flow | S | TD3 / DSRL | Off-Policy | MF | [🔗](https://seed.bytedance.com/gr_rl) |
| [STARE-VLA](https://arxiv.org/abs/2512.05107) | 2025.12 | - | ✓ | ✗ | OpenVLA / π₀.₅ | AR / Flow | D | PPO / TPO / SFT | On-Policy | MF | [🔗](https://sites.google.com/view/stare-vla) |
| [IG-RFT](https://arxiv.org/abs/2602.20715) | 2026.2 | - | ✗ | ✓ | π₀.₅ | Flow | D | IG-AWR | off-policy | MF | — |
| [POCO](https://arxiv.org/abs/2604.01860) | 2026.04 | - | ✓(MT) | ✓(MT) | π₀ / Octo | Flow / Diffusion | D | POCO (EM + Clipped) | Off-Policy | MF | [🔗](https://cccedric.github.io/poco/) |


### Test-time RL-VLA

| Method | Date | Publication | Sim. | Real | Base VLA Model | Action | Reward | Algorithm | Policy | Type | Project |
|--------|------|-------------|------|------|----------------|--------|--------|-----------| --- |------|---------|
| [V-GPS](https://arxiv.org/abs/2410.13816) | 2024.10 | CoRL25[🔗](https://proceedings.mlr.press/v270/nakamoto25a.html) | ✓(MT) | ✓(MT) | Octo / RT-1 / OpenVLA | AR / Diffusion | D | Cal-QL | Test-time | MF | [🔗](https://github.com/nakamotoo/V-GPS) |
| [Hume](https://arxiv.org/abs/2505.21432) | 2025.5 | CVPR26[🔗](https://github.com/hume-vla/hume)/ | ✓(MT) | ✓(MT) | Hume | Flow | S | Value Guidance | Test-time | MF | [🔗](https://github.com/hume-vla/hume) |
| [DSRL](https://arxiv.org/abs/2506.15799) | 2025.6 | CoRL25[🔗](https://diffusion-steering.github.io/) | ✓(MT) | ✓(MT) | DP / π₀ | Diffusion / Flow | S | Diffusion Steering | Test-time | MF |  [🔗](https://diffusion-steering.github.io/) |
| [VLA-Reasoner](https://arxiv.org/abs/2509.22643) | 2025.9 | ICRA26[🔗](https://vla-reasoner.github.io/) | ✓(ST) | ✓(ST) | OpenVLA / SpatialVLA / π₀-Fast | AR / Diffusion | D | MCTS | Test-time | MB |  [🔗](https://vla-reasoner.github.io/) |
| [VLAPS](https://arxiv.org/abs/2508.12211) | 2025.11 | CoRL25 Workshop[🔗](https://openreview.net/forum?id=XB3NCAheab) | ✓(ST) | ✗ | Octo | Diffusion | S | MCTS | Test-time | MB | [🔗](https://github.com/cyrusneary/vlaps) |
| [VLA-Pilot](https://arxiv.org/pdf/2511.14178) | 2025.11 | - | ✗ | ✓(ST) | DiVLA / RDT | AR / Diffusion | D | Value GuidanceT | Test-time | MB(MLLM) | [🔗](https://rip4kobe.github.io/vla-pilot/) |
| [TACO](https://arxiv.org/pdf/2512.02834) | 2025.12 | - | ✓ | ✓(ST) |  π₀ / OpenVLA et al. | Flow | S | CNF estimation | Test-time | MF | [🔗](https://vla-anti-exploration.github.io/) |
| [TT-VLA](https://arxiv.org/abs/2601.06748v2) | 2026.1 | - | ✓(ST) | ✓(ST) | Nora / OpenVLA / TraceVLA | AR | D | PPO (Value-free) | Test-time | MF | - |
| [VLS](https://arxiv.org/pdf/2602.03973) | 2026.2 | - | ✓(MT) | ✓(MT) | OpenVLA / π₀ / π₀.₅ | Flow | D | gradient-based steer | Test-time | MB(VLM) | [🔗](https://vision-language-steering.github.io/webpage/) |
| [FASTER](https://arxiv.org/abs/2604.19730) | 2026.04 | - | ✓(ST) | ✗ | π₀.₅ | Flow | D | Value-guided Denoising MDP | Test-time | MF | - |

**Note**: The 🔗 symbol in the Project column indicates papers with available project pages, GitHub repositories, or demo websites.
## 🔗 Useful Resources

### 🎯 RL-VLA Action Optimization

Different VLA architectures require distinct RL optimization strategies based on their action generation mechanisms:

<table>
<tr>
<td width="34%">
<img src="action.png" alt="RL-VLA Action Optimization" width="100%" />
</td>
<td width="66%">

- **🔤 Autoregressive VLA**: Optimizes actions at the **token-level**. Each action token is individually optimized through RL, enabling fine-grained control over action sequences but requiring careful handling of sequential dependencies.

- **🌊 Generative VLA** (Diffusion/Flow): Optimizes along the action generation process at the **sequence-level**. The entire action trajectory is optimized as a cohesive unit through the denoising or flow-matching process, providing holistic action optimization.

- **🔗 Dual-system VLA**: Optimizes at the **bridge-level**. RL decides which high-level action proposal to pass to the fast controller, creating a hierarchical optimization approach that complements both token-level and sequence-level methods.

</td>
</tr>
</table>

### Base VLA Models
- [GR00T-N1](https://github.com/NVIDIA/Isaac-GR00T) - NVIDIA series
- [π0](https://github.com/Physical-Intelligence/openpi) - PI series
- [OpenVLA](https://github.com/openvla/openvla) - Open-source VLA model
- [Octo](https://github.com/octo-models/octo) - Generalist robot policy
- [RT-1](https://github.com/google-research/robotics_transformer) - Robotics Transformer

### Datasets & Benchmarks
- [Open X-Embodiment](https://robotics-transformer-x.github.io/) - Large-scale robotic datasets
- [LIBERO](https://libero-ai.github.io/) - Benchmark for lifelong robot learning
- [SimplerEnv](https://github.com/simpler-env/SimplerEnv) - Benchmark for real-sim robot learning
- [RoboTwin](https://github.com/robotwin-Platform/robotwin) - Benchmark for bimanual robot learning
- [DeepPHY](https://github.com/XinrunXu/DeepPHY) - Benchmark for physical reasoning

### Frameworks & Tools
- [RLinf](https://github.com/RLinf/RLinf) - Infrastructure for online RL fine-tuning of VLAs
- [RLinfv0.2](https://rlinf.readthedocs.io/en/latest/rst_source/examples/realworld.html) - Infrastructure for real world RL


## 🤝 Contributing

We welcome contributions to this awesome list! Please feel free to:

1. **Add new papers**: Submit a PR with new RL-VLA papers following the existing format
2. **Update information**: Correct any errors or update paper information
3. **Suggest improvements**: Propose better organization or additional sections

### Contribution Guidelines
- Ensure papers are relevant to RL-VLA research
- Include paper links, project pages (if available), and key details
- Follow the existing table format for consistency
- Add a brief description for new paradigms or significant methodological contributions

## 📄 Citation

If you find this repository useful, please consider citing:

```bibtex
@article{pine2025rlvla,
  title={A Survey on Reinforcement Learning of Vision-Language-Action Models for Robotic Manipulation},
  author={Haoyuan Deng, Zhenyu Wu, Haichao Liu, Wenkai Guo, Yuquan Xue, Ziyu Shan, Chuanrui Zhang, Bofang Jia, Yuan Ling, Guanxing Lu, and Ziwei Wang},
  journal={TechRxiv},
  year={2025},
  doi={10.36227/techrxiv.176531955.54563920/v1},
  note={Preprint}
}
```


---

## ⭐ Star History
 **Star this repository** if you find it helpful!


[![Star History Chart](https://api.star-history.com/svg?repos=Denghaoyuan123/Awesome-RL-VLA&type=date&legend=top-left)](https://www.star-history.com/#Denghaoyuan123/Awesome-RL-VLA&type=date&legend=top-left)
