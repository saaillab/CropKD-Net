# CropKD-Net: Sub-100K Parameter Edge Knowledge Distillation Study (In Development)

**Work-in-Progress Edge Compression Extension of CropGuardNet, SAAIL Lab, IIT Madras Zanzibar**

[![Lab Website](https://img.shields.io/badge/SAAIL%20Lab-IITMZ-14532d)](https://saaillab.github.io/)
[![Flagship Architecture](https://img.shields.io/badge/Teacher%20Model-CropGuardNet-0f172a)](https://github.com/saaillab/CropGuardNet)
[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC_BY--NC_4.0-14532d.svg)](LICENSE)

**Authors:** Innocent Nyalala  
**Affiliation:** SAAIL Lab, School of Engineering and Science, Indian Institute of Technology Madras Zanzibar, Tanzania  

---

## Research Scope

**CropKD-Net** is an exploratory knowledge distillation and INT8 post-training quantization study investigating how compact edge student backbones (`< 100K` parameters) can distill multi-scale crop pathology representations and crop-conditioned probability calibration from the **481,574-parameter CropGuardNet teacher model** ([github.com/saaillab/CropGuardNet](https://github.com/saaillab/CropGuardNet)) for entry-level microcontrollers and budget rural smartphones across East Africa.

> **Project Status:** Code, quantized checkpoints, and empirical ablation benchmarks will be published in this repository following peer-reviewed completion of the parent **[CropGuardNet](https://saaillab.github.io/papers/cropguardnet/)** manuscript.

---

## Parent Teacher Architecture (`CropGuardNet`)

For the verified **35,420-image UUID- and pHash-deduplicated benchmark** (`80,238` augmented duplicates removed across 8 crops and 38 disease classes), four-family Explainable AI faithfulness (`Grad-CAM++`, `LayerCAM`, `LIME`, `GradientSHAP`), 20-regime corruption stress tests, and 200.0 FPS single-thread CPU ONNX inference benchmarks, please refer to the active parent repository:

- **Main Codebase & Benchmarks:** [github.com/saaillab/CropGuardNet](https://github.com/saaillab/CropGuardNet)
- **CropGuardNet Project Page:** [saaillab.github.io/papers/cropguardnet/](https://saaillab.github.io/papers/cropguardnet/)
- **Foliar Crop Pathology Program:** [saaillab.github.io/projects/cropguard-pathology/](https://saaillab.github.io/projects/cropguard-pathology/)

---

## Planned Distillation Tracks Under Investigation

| Compression Axis | Teacher Reference (`CropGuardNet`) | Exploratory Student Target | Hardware Objective |
|---|---|---|---|
| Parameter Footprint | 481,574 params (`1.84 MB` FP32) | `< 100K` params | Entry-level 1–2 GB Android & edge SoCs |
| Logit & Spatial Transfer | Dual-Path `GAP(F_SE) || GAP(F_Trans)` | Channel-matched cosine + KL loss | Preserve cross-crop F1-macro (`0.9874`) |
| Post-Training Quantization | `5.00 ms` FP32 ONNX CPU | INT8 ONNX / TFLite calibration | Zero-cloud field diagnostics |
| Interpretability Fidelity | `LayerCAM` Del AUC `0.7262` | Attribution-consistency distillation | Maintain leaf lesion localization under compression |

---

## SAAIL Lab Agricultural Vision Suite

Explore all active and published agricultural computer vision projects at **SAAIL Lab (School of Engineering and Science, IIT Madras Zanzibar)**:

- **[DGS-Bench (`DLI 2026 Best Poster`)](https://saaillab.github.io/papers/dgs-bench/):** Measuring deployment gaps across imbalanced smallholder field datasets.
- **[CLOVES-4603 (`CVPR 2026 V4A`)](https://saaillab.github.io/papers/cloves-4603/):** Five-family commercial clove grading benchmark.
- **[ETRI Journal (2026, Q2 SCI)](https://saaillab.github.io/papers/clove-xai-etri2026/):** Compositional Explanation Evidence Ratio (`100% EER`).
- **[DSA 2026 Kampala Studies](https://saaillab.github.io/gallery/):** Few-shot cassava transfer learning, DCGAN scarcity limits, and AgriAI Bias Card audits.

---

## Repository Structure

```text
CropKD-Net/
├── README.md
├── LICENSE
├── CITATION.cff
└── docs/
    └── index.html          # Standalone companion placeholder page linking to CropGuardNet
```

---

## Reference Citation (Parent Framework)

```bibtex
@misc{nyalala2026cropguardnet,
  title={CropGuardNet: A Unified Lightweight CNN-Transformer Framework with Multi-Scale Attention and Explainable AI for Cross-Crop Leaf Disease Detection},
  author={Nyalala, Innocent},
  howpublished={Manuscript Under Peer Review (SAAIL Lab)},
  year={2026},
  url={https://saaillab.github.io/papers/cropguardnet/}
}
```

---

## License, Attribution & Commercial Restriction

All code, benchmark documentation, splits, and research artifacts in this repository are licensed strictly under **Creative Commons Attribution-NonCommercial 4.0 International ([CC BY-NC 4.0](LICENSE))** by **Innocent Nyalala & SAAIL Lab (Indian Institute of Technology Madras Zanzibar)**.

- **Non-Commercial Scientific Use Only:** Materials may be studied, cited, and adapted strictly for non-commercial academic research and educational replication.
- **Mandatory Attribution:** Any use or derivative study must explicitly acknowledge **Innocent Nyalala** ([IITMZ Profile](https://www.iitmz.ac.in/schools/engineering-and-science/faculty/prof-innocent-nyalala)) and **[SAAIL Lab](https://saaillab.github.io/)** and cite the accompanying publication above.
- **Prohibition on Unauthorized Commercialization:** Commercial deployment, paid hosting, proprietary licensing, or product commercialization is strictly prohibited without prior written authorization and direct inclusion of **Innocent Nyalala (`innocent@iitmz.ac.in`)**.

Maintained by **[SAAIL Lab](https://saaillab.github.io/)** ([IITMZ Labs](https://www.iitmz.ac.in/labs)) · School of Engineering and Science, **[Indian Institute of Technology Madras Zanzibar](https://www.iitmz.ac.in/)** · PI: **[Innocent Nyalala](https://www.iitmz.ac.in/schools/engineering-and-science/faculty/prof-innocent-nyalala)**.
