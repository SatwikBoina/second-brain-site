# 📌 MOC — Computer Vision (CV)

> Central hub for **Computer Vision** in Machine Learning.
> Computer Vision focuses on enabling machines to **perceive, understand, and act upon visual data** such as images and videos.

---

## 1. Core Idea

Computer Vision is about mapping:

\[
\text{Pixels (images, video)} \rightarrow \text{Structure, Meaning, or Action}
\]

Key challenge:
> Pixels are **raw signals**, not concepts.

CV systems must learn:
- Invariances (scale, rotation, lighting)
- Spatial structure
- Semantic meaning

---

## 2. Why Computer Vision Is Hard

Visual data introduces challenges:

- Extremely high dimensional input
- Strong spatial correlations
- Sensitivity to noise and lighting
- Occlusion and viewpoint changes
- Large intra-class variation

Unlike tabular data, **features are not given — they must be learned**.

---

## 3. Computer Vision in the ML Landscape

CV intersects multiple paradigms:

- Supervised learning (classification, detection)
- Unsupervised learning (representation learning)
- Self-supervised learning (contrastive learning)
- Reinforcement learning (robot vision)
- Probabilistic modeling (uncertainty, tracking)

🔗 Related:
- [[Supervised Learning — MOC]]
- [[Unsupervised Learning — MOC]]
- [[Reinforcement Learning — MOC]]

---

## 4. Visual Data Types

---

### 4.1 Images

- 2D grids of pixel intensities
- Single-channel or multi-channel (RGB)

---

### 4.2 Video

- Temporal sequence of images
- Adds motion and time dependency

🔗 Related:
- [[Time Series MOC]]

---

### 4.3 3D Data

- Depth maps
- Point clouds
- Multi-view images

---

## 5. Levels of Visual Representation

---

### 5.1 Pixel-Level

- Raw intensities
- Edges, gradients

Low-level, high noise.

---

### 5.2 Local Features

- Corners
- Blobs
- Texture patterns

Used heavily in classical CV.

---

### 5.3 Mid-Level Features

- Shapes
- Parts
- Regions

Bridge between pixels and semantics.

---

### 5.4 High-Level Semantic Features

- Objects
- Scenes
- Actions

Learned via deep models.

---

## 6. Core Computer Vision Tasks

---

### 6.1 Image Classification

Goal:
- Assign label(s) to an image

Examples:
- Object recognition
- Medical diagnosis

---

### 6.2 Object Detection

Goal:
- Locate and classify objects

Outputs:
- Bounding boxes + labels

---

### 6.3 Image Segmentation

Types:
- Semantic segmentation
- Instance segmentation

Goal:
- Pixel-level understanding

---

### 6.4 Keypoint & Pose Estimation

Goal:
- Detect landmarks or joints

---

### 6.5 Optical Flow & Motion Analysis

Goal:
- Estimate motion between frames

---

## 7. Classical Computer Vision

Before deep learning, CV relied on:

- Edge detectors
- Feature descriptors
- Geometric heuristics

Examples:
- SIFT
- HOG
- Haar features

Pros:
- Interpretable
- Low compute

Cons:
- Limited scalability
- Manual feature design

---

## 8. Deep Learning for Computer Vision

Deep learning revolutionized CV by enabling:

- End-to-end learning
- Automatic feature extraction
- Robust invariances

Key architectures:
- CNNs
- Residual networks
- Vision Transformers

🔗 Related:
- [[Neural Networks — MOC]]
- [[Optimization Methods — MOC]]

---

## 9. Convolutional Neural Networks (CNNs)

Core ideas:
- Local connectivity
- Weight sharing
- Translation invariance

CNNs exploit the **spatial structure** of images.

---

## 10. Vision Transformers (ViTs)

Transformers applied to vision by:
- Treating image patches as tokens
- Using self-attention instead of convolution

Strong performance at scale, data-hungry.

---

## 11. Representation Learning in Vision

Modern CV focuses on:
- Learning reusable visual embeddings
- Pretraining on massive datasets
- Fine-tuning for downstream tasks

This mirrors NLP evolution.

🔗 Related:
- [[Representation Learning]]
- [[Semi-Supervised Learning]]

---

## 12. Loss Functions in Computer Vision

Common losses:
- Cross entropy (classification)
- IoU / Dice loss (segmentation)
- Regression losses (bounding boxes)
- Contrastive losses (representation learning)

Loss choice strongly shapes visual behavior.

🔗 Related:
- [[Loss Functions — MOC]]

---

## 13. Evaluation in Computer Vision

Metrics depend on task:

- Accuracy / Top-K accuracy
- mAP (mean average precision)
- IoU
- Dice coefficient

Visual inspection is often required.

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## 14. Error Analysis in Computer Vision

Key questions:
- Are errors due to scale?
- Occlusion?
- Lighting?
- Background bias?

Failure cases are often **visually interpretable**.

🔗 Related:
- [[Error Analysis]]

---

## 15. Curse of Dimensionality in Vision

Images are:
- Extremely high dimensional
- Highly correlated

CV relies heavily on:
- Inductive bias (convolutions)
- Dimensionality reduction
- Regularization

🔗 Related:
- [[Curse of Dimensionality]]
- [[Dimensionality Reduction — MOC]]

---

## 16. Computer Vision in Production

Challenges:
- Latency (real-time inference)
- Memory constraints
- Model size
- Robustness to noise
- Dataset shift

CV systems must be **stress-tested**.

🔗 Related:
- [[Deployment Basics]]

---

## 17. Ethics and Bias in Computer Vision

Risks include:
- Surveillance misuse
- Racial and demographic bias
- Privacy violations

Bias in visual data is often **invisible but severe**.

🔗 Related:
- [[Fairness in Machine Learning]]

---

## 18. How Computer Vision Fits in ML

Visual Data  
↓  
Representation Learning  
↓  
Models (Classify / Detect / Segment)  
↓  
Evaluation  
↓  
Deployment


Computer vision is **learning perception from raw signals**.

---

## 19. Relationship to Other Concepts

Computer Vision connects strongly to:

- [[Linear Algebra for Machine Learning — MOC]]
- [[Information Theory — MOC]]
- [[Neural Networks — MOC]]
- [[Optimization Methods — MOC]]
- [[Time Series MOC]]
- [[Experiment Tracking]]

---

## Usage Notes

- This MOC is a domain-level hub
- Each task and architecture lives in separate notes
- Always separate representation learning from task logic
- Ask: *what invariance is the model learning?*
