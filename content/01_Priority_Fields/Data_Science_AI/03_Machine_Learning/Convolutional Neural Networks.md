---
type: zettel
domain: machine-learning
category: deep-learning
topic: convolutional-neural-networks
status: evergreen
---

# Convolutional Neural Networks (CNN)

> A Convolutional Neural Network (CNN) is a neural network architecture designed to process grid-structured data (such as images) using convolutional layers that exploit spatial locality and weight sharing.

---

## 1. One-Line Intuition

> Instead of connecting every pixel to every neuron, learn small filters that scan across the image.

---

## 2. Why CNNs Exist

Images have:

- Local spatial structure
- Translation invariance
- Repeated patterns (edges, textures)

Fully connected networks:

- Ignore spatial structure
- Require huge number of parameters
- Overfit easily

CNNs solve this using:

- Local receptive fields
- Shared weights
- Hierarchical feature learning

---

## 3. Core Components of CNN

A CNN typically consists of:

1. Convolutional layers
2. Activation functions
3. Pooling layers
4. Fully connected layers (optional)
5. Output layer

---

## 4. Convolution Operation

For an input image \( X \) and filter \( K \):

\[
Y(i,j) = \sum_m \sum_n X(i+m, j+n) K(m,n)
\]

Filter (kernel):

- Small matrix (e.g., 3×3, 5×5)
- Slides across image
- Produces feature map

---

## 5. Key Concepts

### 5.1 Local Receptive Field

Each neuron sees only a small region of the input.

---

### 5.2 Weight Sharing

Same filter applied everywhere.

This:

- Reduces parameters.
- Enforces translation invariance.

---

### 5.3 Feature Maps

Each filter produces:

- One feature map.

Multiple filters:
- Detect different patterns (edges, corners, textures).

---

## 6. Activation Functions

After convolution:

\[
a = \phi(z)
\]

Common choices:

- ReLU (most common)
- Sigmoid
- Tanh

🔗 Related:
- [[Sigmoid Function]]

---

## 7. Pooling Layer

Reduces spatial dimension.

Common type:

- Max pooling

Purpose:

- Downsampling
- Translation invariance
- Reduce computation

---

## 8. Stride and Padding

Stride:
- Step size of filter movement.

Padding:
- Adds zeros around border.
- Controls output size.

---

## 9. Forward Pass in CNN

Input → Conv → Activation → Pool → Conv → ... → Flatten → Dense → Output

---

## 10. Loss Functions

For classification:

- Cross-Entropy
- Softmax output

🔗 Related:
- [[Cross-Entropy]]
- [[Softmax Function]]

---

## 11. Backpropagation in CNN

Gradients computed:

- Through convolution layers.
- Using chain rule.
- Similar to MLP but with shared weights.

🔗 Related:
- [[Gradient Descent]]
- [[Multilayer Perceptron]]

---

## 12. Hierarchical Feature Learning

Early layers:
- Edges
- Simple patterns

Middle layers:
- Shapes
- Textures

Deep layers:
- Objects
- Complex concepts

---

## 13. Bias–Variance Perspective

CNNs:

- Lower bias than linear models.
- Fewer parameters than fully connected MLP on images.
- Better generalization due to structure.

---

## 14. Why CNNs Are Efficient

If image is 100×100:

Fully connected layer:
- 10,000 weights per neuron.

3×3 filter:
- Only 9 weights per filter.

Massive parameter reduction.

---

## 15. Variants of CNN

- LeNet
- AlexNet
- VGG
- ResNet
- EfficientNet

Introduce:

- Deeper architectures
- Residual connections
- Better optimization

---

## 16. Limitations

- Require large datasets.
- Computationally expensive.
- Less effective for non-spatial tabular data.
- Harder to interpret.

---

## 17. Relationship to Other Concepts

CNN connects strongly to:

- [[Multilayer Perceptron]]
- [[Gradient Descent]]
- [[Cross-Entropy]]
- [[Softmax Function]]
- [[Bias–Variance Tradeoff]]
- [[Computer Vision MOC]]

---

## 18. Why CNNs Matter

CNNs teach:

- Exploiting structure in data.
- Weight sharing and locality.
- Deep hierarchical representation learning.
- Why architecture matters in ML.

They are foundational to:
> Modern computer vision and deep learning.
