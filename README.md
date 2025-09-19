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
  - [Head & Face Avatars](#head-face-avatars)  
  - [Full-Body / Clothed Avatars](#full-body-clothed-avatars)  
  - [Pose & Expression Control](#pose-expression-control)  
- [Implementations & Code](#implementations--code)  
- [Datasets](#datasets)  
- [Demos & Videos](#demos--videos)  
- [Surveys & Related Resources](#surveys--related-resources)  
- [Scope / What’s Included](#scope-whats-included)  
- [Contributing](#contributing)  
- [License](#license)  

---

## 📚 Papers

### Head & Face Avatars

| Title | Input / Setting | What is Controllable | Real-Time? / Speed | Link | Modality | Contribution | Views Type |
|---|---|---|---|---|---|---|---|
| **SEGA: Drivable 3D Gaussian Head Avatar from a Single Image** | Single image; using UV-space Gaussian framework + FLAME prior | Expression + view + identity; generalizes to unseen identities | Real-time performance claimed | [arXiv 2025](https://arxiv.org/abs/2504.14373) :contentReference[oaicite:0]{index=0} |
| **FMGS-Avatar: Mesh-Guided 2D Gaussian Splatting with Foundation Model Priors for 3D Monocular Avatar Reconstruction** | Monocular video / limited view; uses mesh guidance + foundation model priors | Improves geometric detail + appearance fidelity; consistent rendering under novel views/poses | — (track speed via experiments) | [arXiv 2025](https://arxiv.org/abs/2509.14739) :contentReference[oaicite:1]{index=1} |

---

### Full-Body / Clothed Avatars

| Title | Input / Setting | What is Controllable | Real-Time? / Speed | Link | Modality | Contribution | Views Type |
|---|---|---|---|---|---|---|---|
| **GAvatar: Animatable 3D Gaussian Avatars with Implicit Mesh Learning** | Text prompt + pose‐driven primitives; combines explicit Gaussian + implicit mesh learning | Identity / geometry + appearance; animation support | ~100 fps at 1K res claimed | [arXiv 2023](https://arxiv.org/abs/2312.11461) :contentReference[oaicite:2]{index=2} |

---

### Pose & Expression Control

| Title | Focus | Controlled Variables | Link | Modality | Contribution | Views Type |
|---|---|---|---|---|---|---|
| SEGA | head / face; disentangle dynamic vs static parts; control expression + view + identity | Expression, view, identity | [arXiv](https://arxiv.org/abs/2504.14373) :contentReference[oaicite:3]{index=3} |
| GAvatar | full‐body / identity; geometry + appearance; animatable via pose | Pose, identity, geometry detail | [arXiv](https://arxiv.org/abs/2312.11461) :contentReference[oaicite:4]{index=4} |

---


## 🔧 Implementations & Code

- Whenever available, include GitHub / project URLs  
- Example: if SEGA / GAvatar have official code releases, include here (you may need to check if code is published yet)  
- For projects without code, note that status

---

## 📂 Datasets

- List datasets used by the papers above (e.g. datasets with multi‐view images, expression / pose annotations, identity variation)  
- If there are avatar / human scan datasets useful for 3DGS avatar work, include them

---

## 🎥 Demos & Videos

- Link to project demo pages  
- Embeddable video / gif if available  
- Screenshots of avatars / animations help

---

## 📖 Surveys & Related Resources

- *A Survey on 3D Human Avatar Modeling -- From Reconstruction to Generation* — Links: [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2406.04253)

---

## 📋 Scope / What’s Included

This repository collects methods and resources that satisfy **all** of:

1. Use **3D Gaussian Splatting** (or methods clearly based on or extending 3DGS) as a core component.  
2. Target **avatars / dynamic humans** (head, face, full body, clothed, expression / pose animation).  
3. Support or demonstrate **dynamic / controllable outputs** (pose, expression, identity, view etc.).  

Excluded (for now):

- Static scenes / static objects without human / avatar elements.  
- Methods that use only 2D Gaussian Splatting without 3D extension.  
- Non-human characters unless specified.  

---

## 🤝 Contributing

We welcome contributions! If you find a new paper / code repo / demo / dataset relevant to **3D Gaussian Splatting + avatars / dynamic humans**, please send a Pull Request. When submitting, please include:

- Title, authors, year  
- Type of avatar (head / full body / clothed)  
- Input modality (single image / video / multi-view / text prompt etc.)  
- Controlled variables (pose, expression, identity, view etc.)  
- Speed / resource info (if available)  
- Code / demo / project page link 
---

## ⚠️ License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

Thank you to the authors of all the papers/projects listed, and to the wider 3DGS community.  

---

