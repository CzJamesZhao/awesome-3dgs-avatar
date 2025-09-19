# awesome-3dgs-avatar
# Awesome 3D Gaussian Splatting → Avatars & Dynamic Humans

A curated list of papers, implementations, datasets, demos, and resources focusing on **3D Gaussian Splatting (3DGS)** methods applied to **avatars / dynamic human modeling**: head avatars, full-body clothed avatars, expression & pose control, single-image / video / multi-view inputs, and real-time rendering.

---

## 🚀 Table of Contents

- [Papers](#papers)  
  - [Head & Face Avatars](#head-face-avatars)  
  - [Full-Body / Clothed Avatars](#full-body-clothed-avatars)  
  - [Pose & Expression Control](#pose-expression-control)  
  - [Input Modalities (Single-Image / Video / Multi-View)](#input-modalities)  
- [Implementations & Code](#implementations--code)  
- [Datasets](#datasets)  
- [Demos & Videos](#demos--videos)  
- [Surveys & Related Resources](#surveys--related-resources)  
- [Contributing](#contributing)  

---

## 📚 Papers

### Head & Face Avatars

| Title | Input / Setting | What is Controllable | Real-Time? / Speed | Link | Modality |
|---|---|---|---|---|---|
| **SEGA: Drivable 3D Gaussian Head Avatar from a Single Image** | Single image; using UV-space Gaussian framework + FLAME prior | Expression + view + identity; generalizes to unseen identities | Real-time performance claimed | [arXiv 2025](https://arxiv.org/abs/2504.14373) :contentReference[oaicite:0]{index=0} |
| **FMGS-Avatar: Mesh-Guided 2D Gaussian Splatting with Foundation Model Priors for 3D Monocular Avatar Reconstruction** | Monocular video / limited view; uses mesh guidance + foundation model priors | Improves geometric detail + appearance fidelity; consistent rendering under novel views/poses | — (track speed via experiments) | [arXiv 2025](https://arxiv.org/abs/2509.14739) :contentReference[oaicite:1]{index=1} |

---

### Full-Body / Clothed Avatars

| Title | Input / Setting | What is Controllable | Real-Time? / Speed | Link |
|---|---|---|---|---|
| **GAvatar: Animatable 3D Gaussian Avatars with Implicit Mesh Learning** | Text prompt + pose‐driven primitives; combines explicit Gaussian + implicit mesh learning | Identity / geometry + appearance; animation support | ~100 fps at 1K res claimed | [arXiv 2023](https://arxiv.org/abs/2312.11461) :contentReference[oaicite:2]{index=2} |

---

### Pose & Expression Control

| Title | Focus | Controlled Variables | Link |
|---|---|---|---|
| SEGA | head / face; disentangle dynamic vs static parts; control expression + view + identity | Expression, view, identity | [arXiv](https://arxiv.org/abs/2504.14373) :contentReference[oaicite:3]{index=3} |
| GAvatar | full‐body / identity; geometry + appearance; animatable via pose | Pose, identity, geometry detail | [arXiv](https://arxiv.org/abs/2312.11461) :contentReference[oaicite:4]{index=4} |

---

### Input Modalities

| Modality | Example Works | Notes |
|---|---|---|
| Single Image | SEGA (single image driven head avatar) :contentReference[oaicite:5]{index=5} | Useful for minimal input / avatar from photo |
| Monocular Video / Sparse Views | FMGS-Avatar, GAvatar :contentReference[oaicite:6]{index=6} | More temporal consistency; more geometry info |

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

## 🤝 Contributing

We welcome contributions! If you find a new paper / code repo / demo / dataset relevant to **3D Gaussian Splatting + avatars / dynamic humans**, please feel free to send a Pull Request. Here are suggestions for what to include:

- Title, authors, year  
- What part is avatar / dynamic human (head / full‐body / expression / pose / identity)  
- Input modality (single image / video / multi‐view / text prompt / etc.)  
- What is controllable (pose, expression, identity, view, etc.)  
- Whether there's code / demo, speed / real-time info if available  
- Link to paper, code, project page, demo

---

## ⚠️ License

Specify a license for this repository (MIT or other).  

---

## 🙏 Acknowledgments

Thank you to the authors of all the papers / projects listed, and to the wider 3DGS community.  

---

