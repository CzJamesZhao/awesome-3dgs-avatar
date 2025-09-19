# awesome-3dgs-avatar
**Awesome 3D Gaussian Splatting → Avatars & Dynamic Humans**

A curated list of papers, implementations, datasets, demos, and resources focusing on **3D Gaussian Splatting (3DGS)** methods applied to **avatars / dynamic human modeling**: head avatars, full-body clothed avatars, expression & pose control, single-image / video / multi-view inputs, and real-time rendering.

⭐ If you like this list, give it a star! 😄

---

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](#license)  
[![Last Updated](https://img.shields.io/badge/last%20updated-2025--09--19-blue.svg)](#)  
[![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-green.svg)](#contributing)  


---

## 🚀 Table of Contents

- [Papers](#papers)
  - [Head and Face Avatars](#head--face-avatars)
  - [Full-Body and Clothed Avatars](#full-body--clothed-avatars)
  - [Pose and Expression Control](#pose--expression-control)
- [Implementations and Code](#implementations--code)
- [Datasets](#datasets)
- [Demos and Videos](#demos--videos)
- [Surveys and Related Resources](#surveys--related-resources)
- [Scope and What's Included](#scope--whats-included)
- [Contributing](#contributing)
- [License](#license)

---

## 📚Papers

### Head & Face Avatars

| Title | Model Input | What is Controllable | Real-Time? / Speed | Link | Contribution | Views Type |
|---|---|---|---|---|---|---|
| **SEGA: Drivable 3D Gaussian Head Avatar from a Single Image** | Single image; using UV-space Gaussian framework + FLAME prior | Expression + view + identity; generalizes to unseen identities | Real-time performance claimed | [arXiv 2025](https://arxiv.org/abs/2504.14373) :contentReference[oaicite:0]{index=0} |

---

### Full-Body / Clothed Avatars

| Title | Model Input | What is Controllable | Real-Time? / Speed | Link | Contribution | Views Type |
|---|---|---|---|---|---|---|
| **(MM24)Animatable 3D Gaussian: Fast and High-Quality Reconstruction of Multiple Human Avatars** | video sequence of one or more humans along with their corresponding pose data $(S_t,T_t)$ for each frame. | novel view synthesis and novel pose synthesis | real-time claimed |[![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b?style=for-the-badge.svg)](https://arxiv.org/pdf/2311.16482)<br>  [![Code](https://img.shields.io/badge/Code-GitHub-8A2BE2?style=for-the-badge.svg)](https://github.com/jimmyYliu/Animatable-3d-Gaussian)| 1. Animatable 3D Gaussian: A new representation for dynamic humans that allows for fast, high-quality reconstruction without needing a specific shape prior like SMPL. 2. significantly faster (training in seconds) and uses less memory than previous state-of-the-art methods. 3. Dynamic Shadow Modeling. | monocular (single-view) or sparse multi-view video sequences |
| **(3DV25)D3GA - Drivable 3D Gaussian Avatars** | 3D joint angles and facial keypoints | body, individual garments (like shirts and pants), and the face. | 1024×667 resolution, it achieves approximately 26 FPS | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2311.08581)<br>  [![Code](https://img.shields.io/badge/Code-GitHub-8A2BE2.svg)](https://github.com/facebookresearch/D3GA) | 1. A lightweight and composable avatar model using 3D Gaussians that are deformed by tetrahedral cages instead of standard Linear Blend Skinning (LBS). This allows for more natural stretching and re-orientation of the primitives. 2. The ability to use localized conditioning, meaning different parts of the avatar (e.g., face, body) can be driven by different input signals (e.g., keypoints, joint angles). | dense multi-view video captured in a studio setting. 200 cameras as well as a smaller 40-camera setup |


---

### Pose & Expression Control

| Title | Focus | Controlled Variables | Link | Modality | Contribution | Views Type |
|---|---|---|---|---|---|---|
| SEGA | head / face; disentangle dynamic vs static parts; control expression + view + identity | Expression, view, identity | [arXiv](https://arxiv.org/abs/2504.14373) :contentReference[oaicite:3]{index=3} |
| GAvatar | full‐body / identity; geometry + appearance; animatable via pose | Pose, identity, geometry detail | [arXiv](https://arxiv.org/abs/2312.11461) :contentReference[oaicite:4]{index=4} |

---


## 🔧Implementations & Code

- Whenever available, include GitHub / project URLs  
- Example: if SEGA / GAvatar have official code releases, include here (you may need to check if code is published yet)  
- For projects without code, note that status

---

## 📂Datasets

- List datasets used by the papers above (e.g. datasets with multi‐view images, expression / pose annotations, identity variation)  
- If there are avatar / human scan datasets useful for 3DGS avatar work, include them

---

## 🎥Demos & Videos

- Link to project demo pages  
- Embeddable video / gif if available  
- Screenshots of avatars / animations help

---

## 📖Surveys & Related Resources

- *A Survey on 3D Human Avatar Modeling -- From Reconstruction to Generation* — Links: [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2406.04253)

---

## 📋Scope / What’s Included

This repository collects methods and resources that satisfy **all** of:

1. Use **3D Gaussian Splatting** (or methods clearly based on or extending 3DGS) as a core component.  
2. Target **avatars / dynamic humans** (head, face, full body, clothed, expression / pose animation).  
3. Support or demonstrate **dynamic / controllable outputs** (pose, expression, identity, view etc.).  

Excluded (for now):

- Static scenes / static objects without human / avatar elements.  
- Methods that use only 2D Gaussian Splatting without 3D extension.  
- Non-human characters unless specified.  

---

## 🤝Contributing

We welcome contributions! If you find a new paper / code repo / demo / dataset relevant to **3D Gaussian Splatting + avatars / dynamic humans**, please send a Pull Request. When submitting, please include:

- Title, authors, year  
- Type of avatar (head / full body / clothed)  
- Input modality (single image / video / multi-view / text prompt etc.)  
- Controlled variables (pose, expression, identity, view etc.)  
- Speed / resource info (if available)  
- Code / demo / project page link 
---

## ⚠️License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 🙏Acknowledgments

Thank you to the authors of all the papers/projects listed, and to the wider 3DGS community.  

---

