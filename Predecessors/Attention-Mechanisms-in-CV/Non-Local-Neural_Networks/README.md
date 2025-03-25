# Non-Local Neural Networks

## Model Name and Publication Year
- **Full Name**: Non-Local Neural Networks
- **Publication Year**: 2018
- **Presented at**: CVPR 2018 (Computer Vision and Pattern Recognition)

## Paper Details and Authors
- **Authors**: Xiaolong Wang, Ross Girshick, Abhinav Gupta, Kaiming He (Facebook AI Research)
- **Publication**: "Non-Local Neural Networks"
- **Citation**: Wang, X., Girshick, R., Gupta, A., & He, K. (2018). Non-local neural networks. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 7794-7803).

## Original Paper
- [Non-Local Neural Networks](https://arxiv.org/abs/1711.07971)

## Concise Summary of Key Contributions
Non-Local Neural Networks introduced the "non-local block," a groundbreaking building block for capturing long-range dependencies in deep neural networks. While convolutional operations capture only local information within their receptive fields, non-local operations compute the response at a position as a weighted sum of features at all positions, similar to self-attention mechanisms. This approach enabled models to capture global context directly, regardless of positional distance, and significantly improved performance on video classification, object detection, instance segmentation, and pose estimation tasks. Most importantly, Non-Local Networks pioneered the use of self-attention mechanisms in computer vision, predating and laying foundational groundwork for Vision Transformers and other attention-based architectures.

## Architectural Details

### Core Innovation: Non-Local Block
The non-local block is designed to capture long-range dependencies directly through computing interactions between any two positions, regardless of their distance:

```
       Input Features (x)
        /      |      \
       ↓       ↓       ↓
     [θ(x)]   [ϕ(x)]  [g(x)]
       |        |       |
       ↓        ↓       ↓
  Query (q)  Key (k)  Value (v)
       |        |       |
       \        |       /
        \       ↓      /
         \  Similarity /
          \     |     /
           \    ↓    /
            Attention Weights
                 |
                 ↓
         Weighted Values
                 |
                 ↓
            [1×1 Conv]
                 |
                 ↓
        Residual Connection
                 |
                 ↓
             Output (y)
```

### Network Architecture
Non-Local Networks are not standalone architectures but rather enhancements to existing backbones like ResNet. The paper primarily demonstrated non-local blocks integrated into:

- **I3D**: For video classification
- **ResNet-50/101**: For image classification, object detection, instance segmentation
- **ResNet-101 + FPN**: For Mask R-CNN

### Variants of Non-Local Blocks:
1. **Gaussian**: Computes similarity using a Gaussian function
2. **Embedded Gaussian**: Applies feature transformations before computing similarity (equivalent to self-attention)
3. **Dot Product**: Uses dot product for similarity computation
4. **Concatenation**: Concatenates features before similarity computation

### Spatial-Temporal Extensions:
For video tasks, non-local blocks are extended to process 3D volumes, capturing dependencies across both spatial and temporal dimensions simultaneously.

## Key Innovations

1. **Non-Local Operations**: Formalization of non-local means as differentiable neural network blocks.

2. **Long-Range Dependencies**: Direct modeling of relationships between distant positions without requiring multiple stacked local operations.

3. **Self-Attention in Vision**: One of the first successful applications of self-attention mechanisms in computer vision.

4. **Spatial-Temporal Modeling**: Effective joint modeling of spatial and temporal dependencies for video understanding.

5. **Complementary to CNNs**: Designed to complement, not replace, convolutional layers by capturing different aspects of visual data.

6. **Instantaneous Global Context**: Ability to capture global context in a single layer, unlike CNNs which require deep stacking.

7. **Flexible Formulations**: Various similarity functions can be used, leading to different non-local operations.

8. **Efficiency Considerations**: Introduced subsampling strategies to reduce computational costs while maintaining performance.

## Relationship to Vision Transformers

Non-Local Networks are a critical precursor to Vision Transformers (ViT), establishing many foundational concepts:

1. **Self-Attention Mechanism**: The embedded Gaussian non-local block is mathematically equivalent to self-attention used in transformers.

2. **Chronological Significance**: Non-Local Networks (2018) applied self-attention to vision tasks two years before Vision Transformers (2020).

3. **Hybrid vs. Pure Approach**: Non-Local Networks integrate self-attention blocks into CNN backbones, while ViT replaces convolutions almost entirely.

4. **Implementation Differences**:
   - Non-Local blocks typically use a single attention head
   - ViT uses multi-head attention and includes positional encodings
   - Non-Local blocks are often used sparingly in networks, while ViT is composed entirely of transformer blocks

5. **Evolution Path**: Non-Local Networks → Transformer-based detection models → Vision Transformers
   - Models like DETR built upon non-local concepts before full Vision Transformers emerged

6. **Design Philosophy**: Non-Local Networks showed that global dependencies are important for vision tasks, which became a central tenet of Vision Transformers.

## Code Snippets and Implementation Links


### Popular Implementations

- **Original Caffe2 Implementation**: [facebookresearch/video-nonlocal-net](https://github.com/facebookresearch/video-nonlocal-net)
- **PyTorch**: [AlexHex7/Non-local_pytorch](https://github.com/AlexHex7/Non-local_pytorch)
- **TensorFlow**: [nnUyi/Non-Local_Nets-Tensorflow](https://github.com/nnUyi/Non-Local_Nets-Tensorflow)
- **MMAction2 (Video Understanding Toolbox)**: [open-mmlab/mmaction2](https://github.com/open-mmlab/mmaction2)

## Further Reading Suggestions

1. **Self-Attention Generative Adversarial Networks**: "Self-Attention Generative Adversarial Networks" (2019) - Applied self-attention to GANs.

2. **Attention Augmented Convolutional Networks**: "Attention Augmented Convolutional Networks" (2019) - Integrates multi-head self-attention into CNNs.

3. **Axial Attention**: "Axial Attention in Multidimensional Transformers" (2019) - Decomposes self-attention for efficiency in images and videos.

4. **DETR**: "End-to-End Object Detection with Transformers" (2020) - Uses transformers for object detection.

5. **Vision Transformer (ViT)**: "An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale" (2020) - Applies transformer architecture to image classification.

6. **Swin Transformer**: "Swin Transformer: Hierarchical Vision Transformer using Shifted Windows" (2021) - Hierarchical transformer with shifted window attention.

7. **MViTv2**: "MViTv2: Improved Multiscale Vision Transformers for Classification and Detection" (2022) - Multiscale vision transformer that builds on non-local concepts.

8. **Space-Time Correspondence Networks**: "Learning Correspondence from the Cycle-Consistency of Time" (2019) - Self-supervised learning with temporal non-local operations.
