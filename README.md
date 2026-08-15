<div align="center">

# Awesome Super-Resolution in the Dark

**A curated list of papers, code, datasets, and resources for low-light image and video super-resolution.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![Last Update](https://img.shields.io/github/last-commit/moriyaya/awesome-super-resolution-in-the-dark?label=updated)](https://github.com/moriyaya/awesome-super-resolution-in-the-dark/commits/main)
[![License: CC0-1.0](https://img.shields.io/badge/license-CC0--1.0-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

</div>

Low-light super-resolution (LLSR/LLISR) aims to recover a **well-illuminated high-resolution image or video** from observations degraded jointly by insufficient illumination, low spatial resolution, noise, blur, color distortion, and camera processing. This list focuses on methods that explicitly address both illumination and resolution—not generic low-light enhancement or standard super-resolution alone.

> **Living list.** The field is young and terminology is not yet standardized. Missing work and corrections are welcome through [issues](https://github.com/moriyaya/awesome-super-resolution-in-the-dark/issues) or [pull requests](CONTRIBUTING.md).

## Contents

- [Scope](#scope)
- [Taxonomy](#taxonomy)
- [Papers](#papers)
  - [Single-image methods](#single-image-methods)
  - [RAW and sensor-aware methods](#raw-and-sensor-aware-methods)
  - [Burst and video methods](#burst-and-video-methods)
  - [Specialized and adjacent methods](#specialized-and-adjacent-methods)
- [Datasets](#datasets)
- [Related awesome lists](#related-awesome-lists)
- [Contributing](#contributing)

## Scope

### Included

- direct low-light low-resolution (LLLR) → normal/well-lighted high-resolution reconstruction;
- joint low-light enhancement and image/video super-resolution;
- real, synthetic, RAW, sRGB, burst, and video settings;
- datasets and benchmarks created specifically for the coupled task;
- specialized low-light SR settings when clearly labeled.

### Not included by default

- low-light enhancement that preserves the input spatial resolution;
- ordinary super-resolution evaluated only under normal illumination;
- pipelines that merely use an off-the-shelf enhancer and upsampler without studying the coupled task;
- “high-resolution low-light enhancement” where *high-resolution* describes the input size rather than an SR objective.

## Taxonomy

| Axis | Categories | Main question |
|---|---|---|
| Input | Single image · RAW/sRGB · Burst · Video | What observations are available? |
| Degradation | Synthetic · Real-captured · Ultra-dark · Unknown/mixed | How faithfully is darkness coupled with downsampling, noise, and blur? |
| Learning | Direct mapping · Decoupled/multi-stream · Multi-level optimization · Diffusion | How are illumination recovery and detail reconstruction coordinated? |
| Prior | Retinex/illumination · Semantic · Frequency · Degradation · Temporal | What guides reconstruction when the signal is weak? |
| Output | NLHR image · WIHR video · Task-specific HR output | What is reconstructed? |

## Papers

Legend: **Code** links to an author-released implementation. **Announced** means a repository exists but the relevant implementation or weights are not yet fully released. `—` means no author code was located during curation.

### Single-image methods

| Year | Method | Paper | Venue | Main idea | Resources |
|---:|---|---|---|---|---|
| 2026 | DTP | [Dual-Path Learning based on Frequency Structural Decoupling and Regional-Aware Fusion for Low-Light Image Super-Resolution](https://arxiv.org/abs/2603.27301) | ICME 2026 | Frequency decoupling and dual-path luminance/texture reconstruction | [Code](https://github.com/JXVision/DTP) |
| 2026 | GTFMN | [Guided Texture and Feature Modulation Network for Low-Light Image Enhancement and Super-Resolution](https://arxiv.org/abs/2601.19157) | arXiv 2026 | Illumination-guided modulation of a texture stream | — |
| 2025 | DARE | [Degradation-Aware One-Step Diffusion Model for Content-Sensitive Super-Resolution in the Dark](https://doi.org/10.1145/3746027.3755853) | ACM MM 2025 | One-step diffusion with degradation-aware LoRA and content-sensitive priors | [Code](https://github.com/csmty/DARE) |
| 2025 | UltraIS | [A Dual-Stream-Modulated Learning Framework for Illuminating and Super-Resolving Ultra-Dark Images](https://doi.org/10.1109/TNNLS.2024.3409056) | IEEE TNNLS 2025 | Illumination-semantic dual modulation and resolution-sensitive upsampling | [Code](https://github.com/moriyaya/UltraIS) |
| 2024 | JSLNet | [Joint Image Super-resolution and Low-light Enhancement in the Dark](https://openaccess.thecvf.com/content/ACCV2024/html/Zhou_Joint_Image_Super-resolution_and_Low-light_Enhancement_in_the_Dark_ACCV_2024_paper.html) | ACCV 2024 | Dual RAW/sRGB inputs with frequency fusion | [Code & data](https://github.com/flyhu2/DarkSR) |
| 2024 | TriCo | [Enhancing Images with Coupled Low-Resolution and Ultra-Dark Degradations: A Tri-level Learning Framework](https://doi.org/10.1145/3664647.3681682) | ACM MM 2024 | Tri-level cooperative optimization with PGR and IHEM | [Code](https://github.com/moriyaya/TriCo) |
| 2024 | MSIRNet | [Learning Multi-Granularity Semantic Interactive Representation for Joint Low-Light Image Enhancement and Super-Resolution](https://doi.org/10.1016/j.inffus.2024.102467) | Information Fusion 2024 | Semantic and codebook priors for interactive reconstruction | [Code](https://github.com/liushh39/MSIRNet) |
| 2024 | CollaBA | [Collaborative Brightening and Amplification of Low-Light Imagery via Bi-Level Adversarial Learning](https://www.sciencedirect.com/science/article/pii/S0031320324003091) | Pattern Recognition 2024 | Dual-path modulation with bi-level adversarial learning | [Code](https://github.com/moriyaya/CollaBA) |
| 2024 | BrZoNet | [Unveiling Details in the Dark: Simultaneous Brightening and Zooming for Low-Light Image Enhancement](https://doi.org/10.1609/aaai.v38i7.28515) | AAAI 2024 | Retinex-induced Siamese decoupling and illumination-aware interaction | [Code](https://github.com/Yueziyu/BrZoNet) |
| 2023 | JLSN | [Joint Low-Light Enhancement and Super Resolution with Image Underexposure Level Guidance](https://papers.bmvc2023.org/0046.pdf) | BMVC 2023 | Relative underexposure estimation and multi-scale sampling | — |
| 2023 | RELIEF | [RELIEF: Joint Low-Light Image Enhancement and Super-Resolution with Transformers](https://vbn.aau.dk/files/751780650/relief_scia2023_camera_ready.pdf) | SCIA 2023 | Hierarchical encoder-decoder Transformer with cross-shaped attention | — |
| 2022 | LSR | [LSR: Lightening Super-Resolution Deep Network for Low-Light Image Enhancement](https://doi.org/10.1016/j.neucom.2022.08.025) | Neurocomputing 2022 | Iterative back-projection for joint lightening and SR | — |

### RAW and sensor-aware methods

| Year | Method / Dataset | Paper | Venue | Input | Resources |
|---:|---|---|---|---|---|
| 2024 | SRRIIE | [Super-Resolving Real-World Image Illumination Enhancement: A New Dataset and a Conditional Diffusion Model](https://arxiv.org/abs/2410.12961) | arXiv 2024 | Paired RAW images across exposure/ISO settings | [Code & data](https://github.com/Yaofang-Liu/Super-Resolving) |
| 2024 | JSLNet / DarkSR | [Joint Image Super-resolution and Low-light Enhancement in the Dark](https://openaccess.thecvf.com/content/ACCV2024/html/Zhou_Joint_Image_Super-resolution_and_Low-light_Enhancement_in_the_Dark_ACCV_2024_paper.html) | ACCV 2024 | Paired LR RAW + LR sRGB → HR sRGB | [Code & data](https://github.com/flyhu2/DarkSR) |

### Burst and video methods

| Year | Method | Paper | Venue | Setting | Resources |
|---:|---|---|---|---|---|
| 2026 | VSRELL | [VSRELL: A Simple Baseline for Video Super-Resolution and Enhancement in Low-Light Environment](https://openaccess.thecvf.com/content/CVPR2026/html/Hui_VSRELL_A_Simple_Baseline_for_Video_Super-Resolution_and_Enhancement_in_CVPR_2026_paper.html) | CVPR 2026 | Joint illumination enhancement and spatio-temporal VSR | [Announced](https://github.com/373hdj/VSRELL) |
| 2025 | BIRE | [Burst Image Restoration and Enhancement](https://doi.org/10.1109/TPAMI.2024.3356188) | IEEE TPAMI 2025 | Includes burst low-light SR on SID-SR | [Code](https://github.com/akshaydudhane16/BIPNet) |

### Specialized and adjacent methods

These works are useful for tracing the field but differ from the central single-image natural-scene setting.

| Year | Paper | Venue | Why adjacent | Resources |
|---:|---|---|---|---|
| 2022 | [JSENet: A Deep Convolutional Neural Network for Joint Image Super-Resolution and Enhancement](https://doi.org/10.1016/j.neucom.2021.12.071) | Neurocomputing 2022 | General color/contrast enhancement plus SR, not exclusively low-light | — |
| 2021 | [Low-Light-Level Image Super-Resolution Reconstruction Based on a Multi-Scale Features Extraction Network](https://doi.org/10.3390/photonics8080321) | Photonics 2021 | Specialized low-light-level imaging detector; grayscale/colorization setting | — |

## Datasets

| Dataset | Year | Data type | Scale / size | Ground truth | Resources |
|---|---:|---|---|---|---|
| RELLISUR | 2021 | Real-captured sRGB | 12,750 paired images; multiple darkness and resolution levels | Normal-light HR | [Paper](https://neurips.cc/virtual/2021/29875) · [Homepage](https://vap.aau.dk/rellisur/) · [Download](https://doi.org/10.5281/zenodo.5234969) |
| LOL-SR | 2022 | Synthetic LLLR derived from LOL | Bicubic-downsampled LOL pairs | Normal-light HR | Introduced with [LSR](https://doi.org/10.1016/j.neucom.2022.08.025) |
| DarkSR | 2024 | Synthetic and real RAW + sRGB | 1,395 train / 153 test paired samples in the released benchmark | Normal-light HR sRGB | [Paper](https://openaccess.thecvf.com/content/ACCV2024/html/Zhou_Joint_Image_Super-resolution_and_Low-light_Enhancement_in_the_Dark_ACCV_2024_paper.html) · [Download](https://github.com/flyhu2/DarkSR) |
| SRRIIE | 2024 | Real-captured RAW | 4,800 paired images; −6 EV to 0 EV, ISO 50–12,800 | Higher-quality reference | [Paper](https://arxiv.org/abs/2410.12961) · [Repository](https://github.com/Yaofang-Liu/Super-Resolving) |
| SID-SR | 2025 | RAW burst patches derived from SID | Burst low-light ×4 SR protocol | Long-exposure reference | Described in [BIRE](https://doi.org/10.1109/TPAMI.2024.3356188) |

Common synthetic evaluation sets such as LIME-SR, NPE-SR, MEF-SR, DICM-SR, and VV-SR are typically produced by downsampling established low-light enhancement datasets. Please report the exact preprocessing, split, and scale when using them.

## Related awesome lists

- [Awesome Super-Resolution](https://github.com/ChaofWang/Awesome-Super-Resolution) — broad image/video SR literature.
- [Awesome Low-Light Image Enhancement](https://github.com/zhihongz/awesome-low-light-image-enhancement) — enhancement methods, datasets, and metrics.
- [Awesome Diffusion Models in Low-Level Vision](https://github.com/ChunmingHe/awesome-diffusion-models-in-low-level-vision) — diffusion-based restoration and enhancement.
- [Awesome Low-Level Vision](https://github.com/DarrenPan/Awesome-CVPR2024-Low-Level-Vision) — conference-oriented low-level vision collections.

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) and provide a stable paper link, verified venue/year, official code link when available, and a one-line explanation of why the work belongs in scope.

If this list helps your research, consider starring the repository and sharing corrections so the metadata remains useful to the community.

## License

To maximize reuse of this bibliography, the list is released under [CC0 1.0](LICENSE). Linked papers, code, datasets, and images retain their original licenses and copyrights.
