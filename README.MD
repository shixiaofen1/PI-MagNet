This is the translated English version of your README.md, with the "Environment Setup" section removed as requested.

---

# PI-MagNet: Physics-Informed Lightweight Attention Network for High-Accuracy MFL Welding Defect Detection


This is the official implementation of the paper: **"Physics-Informed Lightweight Attention Network for High-Accuracy Magnetic Flux Leakage Welding Defect Detection."**

PI-MagNet is a lightweight network specifically designed for industrial welding defect detection. By integrating Magnetic Perturbation Gradient (MPG) and Magnetic Perturbation-Aware (MPA) attention mechanisms, it overcomes the "physics-blind" limitations of conventional deep learning models. It achieves superior accuracy (92.1% mAP@0.5) with a highly compact footprint of only 2.50M parameters.

## ✨ Key Features

- **Physics-Informed**: Integrates deterministic electromagnetic principles (Gauss’s law for magnetism and Magnetic Dipole Model) into the network architecture.
- **MPG Enhancement Module**: Extracts 2D spatial gradients to amplify defect-induced structural variations while suppressing low-frequency "magnetic pedestal" background noise.
- **MPA Spatial Attention**: Uses gradient-derived cues to steer the network's focus toward defect-sensitive regions based on field-consistency violations.
- **Lightweight Design**: Incorporates **GhostConv** to eliminate feature redundancy, reducing parameters by over 94% compared to YOLOv8, making it ideal for edge devices like NVIDIA Jetson Nano.
- **Physics-Constrained Loss ($L_{phys}$)**: Implements Magnetic Perturbation Divergence (MPD) and Magnetic Leakage Source (MLS) constraints to anchor predicted bounding boxes to physical leakage peaks and prevent "box drift."

## 🛠 Architecture Overview

![Architecture](docs/architecture.png)  
*(Recommended: Insert Fig. 2 from your paper here)*

## 📊 Open-Source Dataset (HC430LA MFL Dataset)

This project releases the high-resolution 2D Magnetic Flux Leakage (MFL) image dataset used in the study:
- **Hardware**: Captured by a customized flexible 32×32 z-axial Hall sensor array.
- **Resolution**: Super-resolution enhancement yielding ~0.5 mm per pixel.
- **Quantity**: 1,000 high-resolution MFL images (800 training / 200 validation).
- **Material**: Automotive-grade HC430LA high-strength steel welds.
- **Download**: [Link to Zenodo / IEEE DataPort / Hugging Face]

## 🚀 Quick Start

### 1. Data Preparation
Organize your dataset in the following structure:
```text
/data
  /images
    /train
    /val
  /labels
    /train
    /val
```



## 📈 Performance Comparison

Benchmark results on the automotive-grade HC430LA steel weld dataset:

| Model | mAP@0.5 (%) | Parameters (M) | Deployment |
| :--- | :---: | :---: | :--- |
| YOLOv8 | 87.6 | 43.61 | GPU |
| YOLOv11 | 80.7 | 25.28 | GPU |
| FasterNet | 81.9 | 3.85 | Edge/GPU |
| EfficientViT | 86.9 | 41.50 | GPU |
| **PI-MagNet (Ours)** | **92.1** | **2.50** | **Jetson Nano (18 FPS)** |

Here is the updated **Citation** section and a **Project Status** notice for your README.md. I have modified the BibTeX to reflect the "Under Review" status as requested.

---

# PI-MagNet: Physics-Informed Lightweight Attention Network for High-Accuracy MFL Welding Defect Detection

> **Note:** This repository corresponds to a research paper currently **Under Review**. Full citation details and the official DOI will be updated upon publication.

... (Keep the rest of your sections like Key Features, Architecture, etc.) ...

## 🔗 Citation

If you use this code or our imaging method in your research, please cite the following papers. 

### 1. PI-MagNet Algorithm (Main Paper - Under Review)
```bibtex
@article{shi2026physics,
  title={Physics-Informed Lightweight Attention Network for High-Accuracy Magnetic Flux Leakage Welding Defect Detection},
  author={Shi, Chengyu and Li, Xuan and Zhang, Yi and Zhu, Hongxi and Li, Chu and Ji, Guanghao and Huang, Yunkai and Sun, Siyi and Pei, Zhengyang and Zhang, Mingji},
  journal={Under Review},
  year={2026},
  note={To be updated upon publication}
}
```

### 2. MFL Imaging Foundation (Hardware & Data Foundation)
```bibtex
@article{shi2026magnetic,
  title={Magnetic leakage flux imaging method for thin steel sheet welding quality inspection},
  author={Shi, Chengyu and Zhang, Buyuan and Hou, Tianchen and Zhang, Yi and Qin, Lifa and Li, Xuan and Li, Hangcheng and Pei, Zhengyang and Peng, Huawen and Li, Chunbo and Zhang, Wenwei and Zhang, Mingji},
  journal={Measurement},
  volume={276},
  pages={121350},
  year={2026},
  publisher={Elsevier},
  doi={10.1016/j.measurement.2026.121350}
}
```


## 📧 Contact
**Author**: Mingji ZHANG (zhangmingji@sztu.edu.cn)  
**Affiliation**: Laboratory 1203, Sino-German Institute of Intelligent Manufacturing, Shenzhen University of Technology

---
*Note: Make sure to replace the bracketed placeholders (e.g., INSERT_YOUR_DATASET_LINK_HERE) with your actual information before publishing.*