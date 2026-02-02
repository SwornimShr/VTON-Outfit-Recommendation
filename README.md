# Technical Archive: Virtual Try-On Network

**Role:** Lead Architect & Project Manager

---

### Project Retrospective (2023 - 2026)
This repository is a technical archive of a 2D Image Synthesis system developed between 2022 and 2023. The project was recognized as a National Finalist at the ICT Awards 2023. This archive documents the system architecture and generative AI implementation for academic and portfolio review.

**Confidentiality Note:**  
To protect proprietary logic, pre-trained model weights (.pth) and full training datasets have been excluded from this public archive. Technical proof of performance is provided in the documentation.

### The Team & Role
* **Swornim Shrestha:** Lead Architect & Project Manager. 
  * *Focus: System design, coarse-to-fine pipeline architecture, and full-stack integration.*
* **Sujal Paudel:** AI Research & Lead Developer. 
  * *Focus: Generative model implementation and technical documentation.*
* **Technical Contributors:** Two additional developers contributed to modular implementation, dataset preprocessing, and system validation.
* *Verification:* My leadership role and the project's finalist status are verified by the official ID Badge located in the `/evidence` directory.

### System Design & Architecture
The project, originally developed under the name **Dreshion**, implements a **Coarse-to-Fine** synthesis pipeline to transfer apparel items onto 2D human figures without the overhead of 3D modeling.

#### 1. Geometric Matching Module (GMM)
* **Function:** Non-rigid warping of 2D clothing.
* **Logic:** Utilizes **Thin-Plate Spline (TPS)** regressions to map apparel onto 18-point human pose heatmaps. 
* **Innovation:** Implemented Grid Interval Consistency (GIC) to mitigate texture distortion during complex occlusions (arms/hair).

#### 2. Try-On Module (TOM)
* **Function:** Identity-preserving texture refinement.
* **Logic:** A 23-layer **U-Net** architecture designed for multi-stage feature extraction and expansive path synthesis.
* **Optimization:** Integrated **SN-PatchGAN** (Spectral Normalized Patch Generative Adversarial Network) to resolve blurry boundaries and preserve facial identity.

#### 3. Full-Stack Integration
* **Architecture:** Decoupled the PyTorch inference engine from the web layer to ensure modularity.
* **Backend:** Django-based framework supported by PostgreSQL for session-based try-on history and catalog management.

### Performance & Validation
* **Quantitative:** Achieved an **FID score of 10.09**, validating high-fidelity synthesis against real-world image distributions.
* **Qualitative:** Successfully preserved complex fabric patterns and handled simple hair/arm occlusions while maintaining 100% of the user's facial identity.
* **Pre-processing:** Implemented custom segmentation masks to protect non-target regions (skin tone, hair, lower garments).

### Evidence & Visual Output
Technical proofs and visual results are archived in this repository:
* [Technical Architecture Summary & ID Badge](./evidence/)
* [Visual Output Examples](./examples/)

---
© 2023 Swornim Shrestha. All Rights Reserved.
