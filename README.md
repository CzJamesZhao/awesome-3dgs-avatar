# awesome-3dgs-avatar
**Awesome 3D Gaussian Splatting → Avatars & Dynamic Humans**

A curated list of papers, implementations, datasets, demos, and resources focusing on **3D Gaussian Splatting (3DGS)** methods applied to **avatars / dynamic human modeling**: head avatars, full-body clothed avatars, expression & pose control, single-image / video / multi-view inputs, and real-time rendering.

⭐ If you like this list, give it a star! 😄

---

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](#license)  
[![Last Updated](https://img.shields.io/badge/last%20updated-2025--09--24-blue.svg)](#)  
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

| Title | Model Input | What is Controllable | Real-Time? / Speed | Papers & Codes | Contribution | Views Type |
|---|---|---|---|---|---|---|
| **(CVPR24)Gaussian Head Avatar:Ultra High-fidelity Head Avatar via Dynamic Gaussians** | | | | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2312.03029)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/YuelangX/Gaussian-Head-Avatar)  | | |
| **(25)SEGA: Drivable 3D Gaussian Head Avatar from a Single Image** | Single image; using UV-space Gaussian framework + FLAME prior | Expression + view + identity; generalizes to unseen identities | Real-time performance claimed | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/abs/2504.14373) Not release code|

---

### Full/Upper-Body / Clothed Avatars

| Title | Model Input | What is Controllable | Speed | Papers & Codes | Contribution | Views Type | specified problem | Training & Inference Device | Limitations |
|---|---|---|---|---|---|---|---|---|---|
| **(MM24)Animatable 3D Gaussian: Fast and High-Quality Reconstruction of Multiple Human Avatars** | video sequence of one or more humans along with their corresponding pose data $(S_t,T_t)$ for each frame. | novel view synthesis and novel pose synthesis | real-time claimed |[![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b?style=for-the-badge.svg)](https://arxiv.org/pdf/2311.16482)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2?style=for-the-badge.svg)](https://github.com/jimmyYliu/Animatable-3d-Gaussian)| 1. Animatable 3D Gaussian: A new representation for dynamic humans that allows for fast, high-quality reconstruction without needing a specific shape prior like SMPL. 2. significantly faster (training in seconds) and uses less memory than previous state-of-the-art methods. 3. Dynamic Shadow Modeling. | monocular (single-view) or sparse multi-view video sequences |
| **(3DV25)D3GA - Drivable 3D Gaussian Avatars** | 3D joint angles and facial keypoints | body, individual garments (like shirts and pants), and the face. | 1024×667 resolution<br> it achieves approximately 26 FPS | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2311.08581)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/facebookresearch/D3GA) | 1. A lightweight and composable avatar model using 3D Gaussians that are deformed by tetrahedral cages instead of standard Linear Blend Skinning (LBS). This allows for more natural stretching and re-orientation of the primitives. 2. The ability to use localized conditioning, meaning different parts of the avatar (e.g., face, body) can be driven by different input signals (e.g., keypoints, joint angles). | dense multi-view video captured in a studio setting. 200 cameras as well as a smaller 40-camera setup |
| **(23)Human101: Training 100+FPS Human Gaussians in 100s from 1 View** | A single-view video, pre-calibrated camera parameters, SMPL (human pose and shape) parameters for each frame, and foreground masks. | SMPL pose (θ) and shape (β)  | Rendering is real-time | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2312.15258.pdf)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/longxiang-ai/Human101) Not release code| 1.  Pioneers the use of 3D Gaussian Splatting (3D GS) for dynamic human reconstruction, leveraging its explicit representation for efficient rendering. 2.  Proposes a Canonical Human Initialization method that creates a high-quality initial model by fusing point clouds, which significantly accelerates convergence. 3.  Introduces a Human-centric Forward Gaussian Animation method that is more efficient than the traditional backward skinning used in NeRF-based approaches, enabling fast pose-driven animation| Monocular |
| **(CVPR24)SC-GS: Sparse-Controlled Gaussian Splatting for Editable Dynamic Scenes** | An image sequence from a monocular dynamic video | Scene motion can be edited by manipulating a graph of sparse control points. | high rendering speed | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://yihua7.github.io/SC-GS-web/materials/SC_GS_Arxiv.pdf)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/CVMI-Lab/SC-GS) | 1. Proposes a novel representation that uses sparse control points and an MLP to model the motion of dense 3D Gaussians for dynamic scenes.  2. Introduces an adaptive strategy to adjust the number of control points and an "As-Rigid-As-Possible" (ARAP) loss to ensure plausible and smooth motions.  3. Enables user-controlled motion editing by deforming a control point graph while preserving high-fidelity appearance | Takes monocular video as input to synthesize novel (free-viewpoint) views of the dynamic scene. |
| **(CVPR24)GauHuman: Articulated Gaussian Splatting from Monocular Human Videos** | Monocular RGB Video (single view video) , along with pre-processed camera parameters, foreground masks, and SMPL parameters. | novel poses for that subject's avatar by providing new SMPL pose parameters. | real-time rendering.<br> Training Speed: around 1-2 minutes on a single GPU. | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2312.02973.pdf)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/skhu101/GauHuman) | 1. Proposes a novel articulated Gaussian Splatting framework for 3D human modeling that achieves both fast training and real-time rendering. 2. Introduces effective pose and LBS (Linear Blend Skinning) refinement modules to capture fine details. 3. Designs a fast optimization strategy using human priors (SMPL) for initialization/pruning and KL-divergence guidance for splitting/cloning Gaussians, plus a new merge operation | Monocular | efficiency bottleneck in creating high-quality 3D human avatars from monocular videos | single NVIDIA RTX 3090 | 1) The current framework is composed of discrete Gaussian spheres, making it difficult to directly extract traditional 3D mesh models. 2) Recovering very fine dynamic details such as clothing wrinkles from monocular videos remains a huge challenge. |
| **(CVPR24)3DGS-Avatar: Animatable Avatars via Deformable 3D Gaussian Splatting** | A single monocular video, along with a tracked skeleton (fitted SMPL parameters), camera calibration, and foreground masks | pose to create novel animations and the viewpoint for novel view synthesis. | Real-time rendering. Training Time: ~30 mins on a single GPU. | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/abs/2312.09228)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/mikeqzy/3dgs-avatar-release) | 1. The first work to apply 3D Gaussian Splatting for creating animatable human avatars from monocular video.  2. Developed a deformation network with **as-isometric-as-possible regularizations** to handle highly articulated and unseen poses effectively. 3. The first method to simultaneously achieve high-quality rendering, model pose-dependent deformation, fast training (<30 min), and real-time rendering (50+ FPS) in a single framework. | Monocular | NeRFs are too slow for practical applications. | single NVIDIA RTX 3090 GPU | 1.Training Speed:some other grid-based approaches that can train in under 5 minutes. 2.Texture Quality: blurry results on clothing with high-frequency textures or repeating patterns. 3.Geometric Accuracy: does not produce an accurate geometric reconstruction of the avatar's surface. The resulting surface normals can be noisy due to inconsistencies in the depth of the Gaussian splats. |
|**(CVPR24)GaussianAvatar: Towards Realistic Human Avatar Modeling from a Single Video via Animatable 3D Gaussians**| A single monocular RGB video of a person| The body pose of the generated avatar, allowing for realistic animation with out-of-distribution motions | real-time rendering speed of 35 FPS | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/abs/2312.02134)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/aipixel/GaussianAvatar) | 1.  Introduces animatable 3D Gaussians for realistic human avatar modeling from a single video. 2.  Designs a dynamic appearance network with an optimizable feature tensor to capture pose-dependent details like wrinkles. 3.  Proposes a joint optimization of motion and appearance in an end-to-end manner to correct inaccurate motion estimations from monocular videos. | free-viewpoint rendering and novel view synthesis of the animated avatar | information from a single viewpoint is highly limited, and the initial body motion estimations are often inaccurate. | single NVIDIA RTX 3090 GPU | Inaccurate Foreground Segmentation. Difficulty with Loose Clothing | 
|**(CVPR24)Animatable Gaussians: Learning Pose-dependent Gaussian Maps for High-fidelity Human Avatar Modeling**| Multi-view RGB videos of a character and their corresponding SMPL-X pose and shape registrations | pose can be controlled by a driving pose signal | 10 FPS for animation when rendering 1024x1024 images on a single RTX 3090 GPU | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2311.16096v3)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/lizhe00/AnimatableGaussians) | 1.  Animatable Gaussians: A new avatar representation combining 3D Gaussian Splatting with powerful 2D CNNs to create lifelike avatars with high-fidelity, pose-dependent dynamics. 2.  Template-guided Parameterization: A method to learn a character-specific template (even for loose clothing like dresses) and parameterize 3D Gaussians onto 2D maps, making them compatible with 2D networks. 3.  Pose Projection Strategy: A PCA-based technique to project novel driving poses into the distribution of training poses, enabling better generalization and higher-quality synthesis for unseen poses. | Multi-view RGB videos are required for initial training and template creation. Experiments show it can work with sparse-view inputs (e.g.,  3 views) and still achieve high-fidelity results. | creating lifelike, animatable human avatars from RGB videos. | Training: single NVIDIA RTX 4090 GPU. Inference/Evaluation: a single NVIDIA RTX 3090 GPU | Coupled Body and Clothing: The method models the human body and clothes as a single, entangled representation. Requires Multi-View Input: The approach relies on multi-view video input to reconstruct the initial high-quality parametric template. Limited Secondary Motion: The model cannot simulate the physical motion of components that are not directly driven by the body's skeleton and joints. |
|**(NeurIPS24)Expressive Gaussian Human Avatars from Monocular RGB Video**|  | | | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/abs/2407.03204)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/evahuman/EVA_Official) |
|**(ECCV24)Expressive Whole-Body 3D Gaussian Avatar**| | | | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/abs/2407.21686)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/mks0601/ExAvatar_RELEASE) |
|**(CVPR24)SplattingAvatar: Realistic Real-Time Human Avatars with Mesh-Embedded Gaussian Splatting**| | | | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/abs/2403.05087)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/initialneil/SplattingAvatar) |
|**(ICCV25)GUAVA: Generalizable Upper Body 3D Gaussian Avatar**| A single image of a person. | The avatar can be animated and controlled by pose, facial expression, and hand gesture parameters extracted from a target video or image sequence. | real-time. • Reconstruction Time: ~0.1 seconds (~98 ms) from a single tracked image. • Animation & Rendering Speed: ~50 FPS (52.21 FPS reported). | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/abs/2505.03351)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/Pixel-Talk/GUAVA) | 1. First Framework: Proposes the first framework for creating a generalizable upper-body 3D Gaussian avatar from a single image.  2. Expressive Human Model (EHM): Introduces the EHM, which combines SMPLX and FLAME, along with an accurate tracking method to provide better priors for reconstruction. 3. Efficient Reconstruction: Leverages inverse texture mapping and projection sampling to enable fast, feed-forward inference for reconstructing detailed "Ubody Gaussians". | single view and supports novel view synthesis, allowing the rendered avatar to be seen from different camera angles. |
|**(NeurIPS24)HumanSplat: Generalizable Single-Image Human Gaussian Splatting with Structure Priors**| A single RGB image of a human | static modeling | Reconstruction: ~9.3 seconds on a single NVIDIA A100 GPU (~9s for the diffusion model, ~0.3s for the reconstruction transformer). Rendering: Exceeds 150 FPS.| [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/abs/2403.05087)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/initialneil/SplattingAvatar) | 1.  The first generalizable method for high-fidelity human reconstruction from a single image using 3D Gaussian Splatting. 2. An end-to-end framework integrating a 2D diffusion model with a latent reconstruction transformer. 3.  Effectively combines appearance priors (from diffusion) and structural priors (from SMPL) within a single Transformer architecture. 4.  Improves reconstruction fidelity in key areas like the face and hands using a semantics-guided hierarchical loss. | Single-view input. Internally, it synthesizes multi-view latent features to perform the reconstruction | To reconstruct a photorealistic 3D human model from a single image, overcoming the need for multi-view data or time-consuming per-instance optimization, while achieving a state-of-the-art balance between quality and speed. | Training: 8x NVIDIA A100 (40G VRAM) GPUs for approximately 4 days. Inference: A single NVIDIA A100 GPU | 1.  Speed could be further improved for real-time applications on mobile devices. 2.  The output is a static model; making it animatable requires separate post-processing steps.|
|**(CVPR25)AniGS: Animatable Gaussian Avatar from a Single Image with Inconsistent Gaussian Reconstruction**| A single human image in an arbitrary pose. | The final 3D avatar can be animated using new human pose conditions (e.g., SMPL-X parameters) during inference. | Avatar Creation: Not real-time. It takes about 5 minutes to generate multi-view images and another 5 minutes for 4DGS optimization, totaling approximately 10 minutes on a single RTX-3090 GPU. Animation/Inference: Yes, real-time. Once the avatar is reconstructed, it can be animated and rendered in real-time. | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2412.02684)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/aigc3d/AniGS) not release code | 1. Proposes a multi-view canonical image generation method using a video model trained on in-the-wild video data, avoiding the need for synthetic 3D rigged datasets. 2. Reformulates the problem of 3D reconstruction from inconsistent images as a 4D reconstruction task, introducing an efficient 4D Gaussian Splatting (4DGS) model to handle view inconsistencies. 3. Achieves high-fidelity, animatable avatar generation from a single image, enabling photorealistic and real-time animation during inference | The model generates multi-view images of the subject in a canonical pose (e.g., T-pose) |
|**(CVPR25)GASP: Gaussian Avatars with Synthetic Priors**|  | | | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2412.07739)<br>  Not Release code |
|**(CVPR25)GAF: Gaussian Avatar Reconstruction from Monocular Videos via Multi-view Diffusion**| A short, monocular video sequence (e.g., 10-15 seconds) captured by a commodity device like a smartphone| Head pose and facial expressions are controllable via the underlying parametric FLAME model. | Rendering is real-time. The method achieves 62 FPS for rendering an image at 802x550 resolution. However, the initial avatar reconstruction/optimization process is offline and time-consuming (approx. 12 hours). | [![PDF](https://img.shields.io/badge/PDF-arXiv-b31b1b.svg)](https://arxiv.org/pdf/2412.10209)<br>  [![CODE](https://img.shields.io/badge/CODE-GitHub-8A2BE2.svg)](https://github.com/tangjiapeng/GAF) not release code| 1.  A novel approach to reconstruct animatable head avatars from monocular videos by using multi-view head diffusion priors to regularize and complete unobserved regions. 2. A multi-view head diffusion model guided by normal maps rendered from FLAME reconstructions, enabling more precise viewpoint control for generating consistent multi-view images. 3. A strategy to enhance photorealism by using iteratively denoised images (as pseudo-ground truths) and integrating a latent upsampler to refine facial details. | Monocular. The method is specifically designed to work with single-camera videos that have limited viewpoints. |



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

