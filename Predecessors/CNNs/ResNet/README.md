# ResNet (Residual Networks)

## Model Name and Publication Year
**Full Name:** Deep Residual Learning for Image Recognition (ResNet)  
**Publication Year:** 2015  
**Presented at:** CVPR 2016 (Computer Vision and Pattern Recognition)  

## Paper Details and Authors
**Authors:** Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun (Microsoft Research)  
**Publication:** "Deep Residual Learning for Image Recognition"  
**Citation:** He, K., Zhang, X., Ren, S., & Sun, J. (2016). Deep residual learning for image recognition. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 770-778).  

### [Original Paper](https://arxiv.org/abs/1512.03385)

---

## Summary of Key Contributions
ResNet introduced the concept of **"residual learning"** to address the degradation problem in deep neural networks. As networks get deeper, accuracy tends to saturate and then degrade rapidly. ResNet solves this by using **skip connections (shortcuts)** that allow gradients to flow more easily during backpropagation.

Key Achievements:
- Enabled training of very deep networks (up to 152 layers).
- Achieved **state-of-the-art performance** in the **ILSVRC 2015** classification competition with a **top-5 error rate of 3.57%**.

---

## Architectural Details

### **Core Innovation: Residual Block**
The fundamental building block of ResNet is the **residual block**:
```
Input → Conv Layer → Batch Norm → ReLU → Conv Layer → Batch Norm → (Skip Connection) → ReLU → Output
```
Instead of learning the desired mapping **H(x)** directly, the residual block learns **F(x) = H(x) - x**, making the final output **F(x) + x**.

### **Network Architecture**
Various ResNet architectures were proposed, ranging from **18 to 152 layers**:
- **ResNet-18/34**: Uses basic blocks with 2 layers.
- **ResNet-50/101/152**: Uses **bottleneck blocks** with 3 layers to improve efficiency.

#### **ResNet-50 Structure**:
1. Initial **7×7 Conv Layer** with stride 2 → **3×3 Max Pooling**
2. **Four stages** of bottleneck blocks (3, 4, 6, 3 blocks respectively)
3. **Global Average Pooling** → **Fully-Connected Layer** for classification

---

## Key Innovations
- **Residual Learning Framework**: Skip connections help train deeper networks.
- **Identity Mappings**: Identity shortcuts add no extra parameters or computational complexity.
- **Bottleneck Architecture**: Reduces dimensionality before 3×3 convolutions to lower computational costs.
- **Batch Normalization**: Accelerates and stabilizes training.
- **Deep Supervision**: ResNet is trained end-to-end without requiring auxiliary supervision.

---

## Relationship to Vision Transformers (ViT)
- **Different Paradigms**: ResNet uses **convolutions** for local feature learning, while **ViT** uses self-attention for global dependencies.
- **Skip Connections**: Both architectures use skip connections, but in different ways.
- **Hybrid Models**: Modern architectures like **ConvNeXt** and **Swin Transformers** combine ResNet and ViT features.
- **Feature Extraction**: ResNets are often used as feature extractors for ViTs in resource-constrained scenarios.

---

## Code Snippets and Implementation Links
### **Popular Implementations**
- **PyTorch**: `torchvision.models.resnet`
- **TensorFlow/Keras**: `tf.keras.applications.ResNet50`
- **Original Caffe Implementation**: [Kaiming He's Repository](https://github.com/KaimingHe/deep-residual-networks)

---

## Further Reading Suggestions
- **ResNeXt** (2017) - [Aggregated Residual Transformations](https://arxiv.org/abs/1611.05431)
- **Wide ResNet** (2016) - [Increased width over depth](https://arxiv.org/abs/1605.07146)
- **DenseNet** (2017) - [Dense connectivity patterns](https://arxiv.org/abs/1608.06993)
- **SENet** (2018) - [Squeeze-and-Excitation Networks](https://arxiv.org/abs/1709.01507)
- **ResNeSt** (2020) - [Split-Attention Networks](https://arxiv.org/abs/2004.08955)
- **Pre-Activation ResNet** (2016) - [Better normalization-activation ordering](https://arxiv.org/abs/1603.05027)
- **EfficientNet** (2019) - [Systematic model scaling](https://arxiv.org/abs/1905.11946)

---

## Conclusion
ResNet revolutionized deep learning by making very deep networks trainable. Its residual learning framework remains a foundation for many modern architectures, and it continues to be widely used in computer vision tasks.

---

