Virtual Try-On Network (VTON)
---
**Role:** Lead Architect & Project Manager

### Technical Archive (2023 - 2026)
This repository serves as a technical archive of the system developed in 2022-2023. It is published here to document the system architecture and generative AI implementation.

**Note on IP & Confidentiality:**  
To protect proprietary logic and prevent unauthorized reproduction of this system for commercial use, certain datasets and pre-trained model weights (.pth files) have been excluded from this public archive. Technical proof of the system's performance (FID scores/Visual outputs) is provided in the documentation.



### System Architecture
Dreshion implements a **Coarse-to-Fine** synthesis pipeline to transfer apparel items onto 2D human figures without the overhead of 3D modeling.

#### 1. Geometric Matching Module (GMM)
* **Function:** Non-rigid warping of 2D clothing.
* **Logic:** Utilizes **Thin-Plate Spline (TPS)** regressions to map apparel onto 18-point human pose heatmaps. 
* **Innovation:** Implemented Grid Interval Consistency (GIC) to mitigate distortion during complex occlusions (arms/hair).

#### 2. Try-On Module (TOM)
* **Function:** Identity-preserving texture refinement.
* **Logic:** A 23-layer **U-Net** architecture designed for multi-stage feature extraction and expansive path synthesis.
* **Optimization:** Integrated **SN-PatchGAN** (Spectral Normalized Patch Generative Adversarial Network) to resolve blurry boundaries and preserve facial identity.

#### 3. Full-Stack Integration
* **Architecture:** Decoupled the PyTorch inference engine from the web layer.
* **Backend:** Django-based framework supported by PostgreSQL for session-based try-on history and catalog management.

### Performance & Validation
* **Quantitative:** Achieved an **FID score of 10.09**, validating high-fidelity synthesis against real-world image distributions.
* **Pre-processing:** Implemented custom segmentation masks to protect non-target regions (skin tone, hair, lower garments).


---
© 2023 Swornim Shrestha. All Rights Reserved.
