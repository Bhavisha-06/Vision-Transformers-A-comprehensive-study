# Attention Is All You Need (2017)

## Model Name and Publication Year
- **Transformer** (2017)

## Paper Details and Authors
- **Title**: "Attention Is All You Need"
- **Authors**: Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Łukasz Kaiser, Illia Polosukhin
- **Conference**: Neural Information Processing Systems (NeurIPS) 2017

## Link to the Original Paper
- [Attention Is All You Need](https://arxiv.org/abs/1706.03762)

## Concise Summary of Key Contributions
The paper introduced the Transformer architecture, which relies entirely on self-attention mechanisms rather than recurrence or convolution to process sequential data. This approach enabled more parallelization during training and achieved state-of-the-art results on machine translation tasks. The Transformer has since become a foundational architecture for many modern NLP models.

## Architectural Details and Diagrams

The Transformer architecture consists of an encoder and a decoder, each composed of stacked self-attention and point-wise, fully connected layers:

- **Encoder**: 6 identical layers, each with:
  - Multi-head self-attention mechanism
  - Position-wise fully connected feed-forward network
  - Layer normalization and residual connections

- **Decoder**: 6 identical layers, each with:
  - Masked multi-head self-attention mechanism
  - Multi-head attention over encoder output
  - Position-wise fully connected feed-forward network
  - Layer normalization and residual connections

- **Positional Encoding**: Since the model contains no recurrence or convolution, positional encodings are added to the input embeddings to provide information about token positions.

## Key Innovations

1. **Multi-Head Attention**: Allows the model to jointly attend to information from different representation subspaces at different positions.

2. **Scaled Dot-Product Attention**: An efficient attention mechanism that computes attention weights using dot products between queries and keys, scaled by the square root of their dimension.

3. **Self-Attention**: Enables the model to relate different positions in a sequence to compute a representation of the sequence.

4. **Positional Encodings**: Uses sine and cosine functions of different frequencies to encode position information.

5. **Full Parallelization**: Unlike RNNs, the Transformer can process all tokens in a sequence in parallel during training.

## Relationship to Vision Transformers

The original Transformer was designed for NLP tasks. Vision Transformers (ViT), introduced by Dosovitskiy et al. in 2020, adapted the Transformer architecture to computer vision by:

- Treating image patches as tokens (similar to word tokens in NLP)
- Using the same self-attention mechanisms from the original Transformer
- Maintaining the overall architecture with appropriate modifications for image data

The success of Vision Transformers demonstrated the versatility of the attention-based architecture beyond NLP.

## Code Snippets and Implementation Links


### Implementation Links:
- [Official TensorFlow Implementation](https://github.com/tensorflow/tensor2tensor)
- [PyTorch Implementation by Harvard NLP](https://github.com/harvardnlp/annotated-transformer)
- [Hugging Face Transformers Library](https://github.com/huggingface/transformers)

## Further Reading Suggestions

1. **BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding** (Devlin et al., 2018)
   - Demonstrates the power of Transformers for pre-training language models

2. **GPT: Improving Language Understanding by Generative Pre-Training** (Radford et al., 2018)
   - Shows how Transformers can be used for generative pre-training

3. **Vision Transformer (ViT): An Image is Worth 16x16 Words** (Dosovitskiy et al., 2020)
   - Adapts the Transformer architecture to computer vision

4. **Transformers: Attention Is All You Need** by Vaswani et al. - Explained (Jay Alammar)
   - [Illustrated Guide to Transformers](http://jalammar.github.io/illustrated-transformer/)

5. **The Annotated Transformer** (Harvard NLP)
   - [Step-by-step explanation with code](https://nlp.seas.harvard.edu/2018/04/03/attention.html)

6. **Attention, Self-Attention, and Transformers** (Peter Bloem, 2019)
   - Provides theoretical background and intuition behind attention mechanisms
