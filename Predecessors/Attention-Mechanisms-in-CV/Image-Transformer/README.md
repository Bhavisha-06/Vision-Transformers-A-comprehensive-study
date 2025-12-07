# Image Transformer (2018)

## Paper Details
- **Title**: Image Transformer
- **Authors**: Niki Parmar, Ashish Vaswani, Jakob Uszkoreit, Łukasz Kaiser, Noam Shazeer, Alexander Ku, Dustin Tran
- **Publication**: International Conference on Machine Learning (ICML), 2018
- **Link**: Image Transformer[https://arxiv.org/abs/1802.05751]

## Key Contributions
- First successful application of self-attention mechanisms to image generation
- Extended the Transformer architecture from NLP to computer vision
- Introduced efficient self-attention techniques for handling the quadratic complexity in images
- Demonstrated competitive results on image super-resolution and unconditional image generation

## Architectural Details
The Image Transformer adapts the Transformer architecture for image modeling by:
- Treating an image as a 1D sequence of pixels
- Applying self-attention mechanisms to capture long-range dependencies
- Using local attention patterns to reduce computational complexity

## Key Innovations

### 1. Local Self-Attention
To address the quadratic complexity of self-attention for images, the authors introduced local self-attention:
- Each position attends only to a limited neighborhood of positions
- Enables efficient modeling of images with thousands of pixels
- Maintains the ability to capture important local dependencies

### 2. 1D Sequence Ordering for 2D Images
- Developed effective mechanisms to convert 2D image data into 1D sequences
- Introduced specific position encodings for image data
- Designed attention patterns that respect the 2D structure of images

### 3. Query-Key-Value Attention for Images
Adapted the Query-Key-Value attention mechanism for image modeling:
- Attention(Q, K, V) = softmax(QK^T / √d_k)V
- Where Q, K, and V are learned linear projections of the input image data

## Implementation


## Further Reading Suggestions
1. [Attention Is All You Need](https://arxiv.org/abs/1706.03762) (Vaswani et al., 2017) - The original Transformer paper
2. [Axial Attention in Multidimensional Transformers](https://arxiv.org/abs/1912.12180) (Ho et al., 2019) - Extends Image Transformer with more efficient attention patterns
3. [Vision Transformer (ViT)](https://arxiv.org/abs/2010.11929) (Dosovitskiy et al., 2020) - Applies Transformers to image classification
4. [Efficient Attention: Attention with Linear Complexities](https://arxiv.org/abs/1812.01243) (Shen et al., 2018)
5. [Generating Diverse High-Fidelity Images with VQ-VAE-2](https://arxiv.org/abs/1906.00446) (Razavi et al., 2019) - Alternative approach to image generation

## Conclusion
The Image Transformer laid important groundwork for the future development of Transformer-based models in computer vision, influencing later architectures like ViT (Vision Transformer) and DETR (Detection Transformer).
