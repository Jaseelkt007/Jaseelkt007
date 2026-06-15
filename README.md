<div align="center">

<picture>
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f0c29,50:302b63,100:24243e&height=180&section=header&text=Mohammed%20Jaseel&fontSize=48&fontColor=ffffff&fontAlignY=40&desc=Controllable%20Generative%20Models%20%E2%80%A2%20Video%20Generation%20%E2%80%A2%20Neural%20Codecs&descSize=14&descAlignY=62&descColor=a0a0c0"/>
</picture>

<br/>

![Generative Models](https://img.shields.io/badge/Generative%20Models-302b63?style=flat-square&logoColor=white)
![Video Generation](https://img.shields.io/badge/Video%20Generation-302b63?style=flat-square&logoColor=white)
![Diffusion](https://img.shields.io/badge/Diffusion%20%26%20VAEs-302b63?style=flat-square&logoColor=white)
![Autonomous Driving](https://img.shields.io/badge/AD%20Simulation-302b63?style=flat-square&logoColor=white)
![Neural Codec TTS](https://img.shields.io/badge/Neural%20Codec%20TTS-302b63?style=flat-square&logoColor=white)

</div>

---

## `whoami`

M.Sc. researcher at the **University of Stuttgart** working on **controllable generative models** for vision and speech. My core interest is *steerability* — building models whose outputs you can precisely control through dense, structured conditioning, and understanding the representation choices that decide whether that control actually holds.

Most of my work lives at the seam between **video diffusion**, **latent representation design**, and **autonomous-driving simulation** — with a parallel line in **neural audio codecs and controllable TTS**.

---

## Research

### 🎬 Ctrl-V-Seg — Semantically Controlled Video Generation for Autonomous Driving
*ISS, University of Stuttgart · Supervisor: Khaled Seyam (PhD) · Prof. Dr.-Ing. Bin Yang · Sep 2025 – Feb 2026*

A semantic-conditioning extension of **Ctrl-V (TMLR 2025)** that replaces sparse bounding-box control with **dense per-pixel semantic-map control** on KITTI-360.

- **+20.2 pp semantic mIoU** over the Ctrl-V baseline (50.64% vs 30.48%), at FID 21.91 / FVD-I3D 255.2 — within **3.25 pp** of the purpose-built SVS-GAN baseline despite using a generic Stable Video Diffusion XT backbone.
- Diagnosed a **representation mismatch** in Ctrl-V: a frozen RGB-trained VAE was being reused to encode structured control signals it was never trained on.
- Designed a **Semantic-Native VAE** (~200K trainable params, full SVD backbone frozen) reaching **89.87% mIoU** — **+31 pp** over the RGB-VAE baseline — by retraining only the input/output projections.
- Found that ControlNet residuals alone cannot steer a frozen decoder; selectively unfreezing ~15–20% of the UNet raised fidelity by +27.4 pp and converged **3× faster**.

🔗 [Ctrl-V-Seg pipeline](https://github.com/Jaseelkt007/Ctrl-v-SEG) · [Semantic-Native VAE](https://github.com/Jaseelkt007/VAE_semantic)

### 🔊 Neural Codec TTS with Controllable Duration & Voice Cloning
*Sony Europe · AI, Speech & Sound Group · Supervised by Dr. Hassan Shahmohammadi · May 2025 – May 2026*

- Pre-trained **autoregressive Transformer** language models for neural-codec TTS that predict discrete audio tokens.
- Implemented **speaker-rate prefix conditioning** — discretising per-utterance token rates into bins and injecting a learned rate embedding to control speech tempo *without forced alignment*.
- Built phased pre-/post-training for duration control and reference-audio voice cloning, on distributed multi-GPU infrastructure with Prefix-LM masking and repetition-aware sampling.

### 🧪 SiliconGPT — Learning Semiconductor Process Logic from Scratch
*Zero One Hack (AI Factory Austria / Infineon track) · May 2026*

- Trained a **1.37M-parameter transformer from scratch** (one fab process step = one token) for next-step prediction, anomaly detection, and **out-of-distribution generalization** — beating GPT-5 / Gemini / DeepSeek / Qwen while ~1000× smaller and CPU-only.
- Designed it via a measurement-grounded **multi-agent discovery loop** (inspired by Google's AI Co-Scientist) that trains and benchmarks each hypothesis on GPUs; the study surfaced that a *smaller* model generalizes better OOD.

🔗 [SiliconGPT](https://github.com/Jaseelkt007/SiliconGPT) · [Discovery-loop skill](https://github.com/Jaseelkt007/co-scientist-lab)

---

## Research Interests

```
Controllable / conditional generation ──── ██████████ core
Video diffusion & world dynamics ───────── █████████░ active
Latent representation design (VAEs) ────── █████████░ active
Autonomous-driving simulation ──────────── ███████░░░ active
Neural audio codecs & TTS ──────────────── ███████░░░ active
```

---

## Tech Stack

<div align="center">

**Languages**

![Python](https://img.shields.io/badge/Python-0d1117?style=for-the-badge&logo=python&logoColor=3670A0)
![C++](https://img.shields.io/badge/C++-0d1117?style=for-the-badge&logo=cplusplus&logoColor=00599C)

**Frameworks & Generative Modeling**

![PyTorch](https://img.shields.io/badge/PyTorch-0d1117?style=for-the-badge&logo=pytorch&logoColor=EE4C2C)
![HuggingFace](https://img.shields.io/badge/Diffusers%20%26%20Transformers-0d1117?style=for-the-badge&logo=huggingface&logoColor=FFD21E)
![TensorFlow](https://img.shields.io/badge/TensorFlow-0d1117?style=for-the-badge&logo=tensorflow&logoColor=FF6F00)

<sub>Latent diffusion (SVD, DDPM, flow matching) · ControlNet · VAE / VQ-VAE · autoregressive token models · semantic segmentation (KITTI-360 / Cityscapes) · FID / FVD / mIoU protocols</sub>

**Training Infrastructure**

![SLURM](https://img.shields.io/badge/SLURM%20multi--GPU-0d1117?style=for-the-badge&logo=linux&logoColor=FCC624)
![CUDA](https://img.shields.io/badge/CUDA-0d1117?style=for-the-badge&logo=nvidia&logoColor=76B900)
![Weights & Biases](https://img.shields.io/badge/W%26B-0d1117?style=for-the-badge&logo=weightsandbiases&logoColor=FFBE00)
![Docker](https://img.shields.io/badge/Docker-0d1117?style=for-the-badge&logo=docker&logoColor=2496ED)

<sub>H200 / A6000 clusters · FP16 mixed-precision · gradient checkpointing</sub>

</div>

---

## Also Building

Outside research, I ship fast at hackathons and on open-source AI tooling — agentic systems, RAG, voice agents, and applied ML. Recent: **🥇 1st place** Energy Hack Munich (per-inverter ML digital twins) · **🥈 2nd place** Algorand x402 Berlin · **🥈 2nd place** Ignition EPFL × UNIL. More on my [portfolio](https://jaseel.live).

---

## Find Me

<div align="center">

[![Portfolio](https://img.shields.io/badge/jaseel.live-Portfolio-9D8CFF?style=for-the-badge&logo=vercel&logoColor=white)](https://jaseel.live)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/jaseelkt)
[![Instagram](https://img.shields.io/badge/Instagram-Follow-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/jaseel_kt_)
[![Email](https://img.shields.io/badge/Email-Reach_Out-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:jaseelkt1official@gmail.com)

</div>

---

<div align="center">

<sub><i>"The best way to understand a model is to build one."</i></sub>

<br/><br/>

<picture>
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:24243e,50:302b63,100:0f0c29&height=80&section=footer"/>
</picture>

</div>
