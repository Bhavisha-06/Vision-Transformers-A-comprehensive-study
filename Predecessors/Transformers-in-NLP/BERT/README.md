# BERT (2018)

## Paper Details
- **Title**: BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding
- **Authors**: Jacob Devlin, Ming-Wei Chang, Kenton Lee, Kristina Toutanova
- **Published**: NAACL 2019 (arXiv preprint: October 2018)
- **Link**: [https://arxiv.org/abs/1810.04805](https://arxiv.org/abs/1810.04805)

## Summary of Key Contributions
BERT (Bidirectional Encoder Representations from Transformers) fundamentally changed NLP by introducing a powerful pre-training approach that enabled deep bidirectional representations. Unlike previous models that processed text in one direction (left-to-right or right-to-left), BERT considers the entire context of a word by looking at the words that come before and after it, leading to much richer language representations.

## Model Variants
- **BERT-base**:
  - 12 layers
  - 768 hidden units
  - 12 attention heads
  - 110M parameters

- **BERT-large**:
  - 24 layers
  - 1024 hidden units
  - 16 attention heads
  - 340M parameters

## Key Components

### Special Tokens
- `[CLS]`: Appears at the start of every sequence, used for classification tasks
- `[SEP]`: Used to separate sentence pairs or mark the end of a sequence
- `[MASK]`: Used during pre-training to mask tokens for prediction

### Input Representation
Combines three embeddings:
- Token embeddings: WordPiece vocabulary (30,000 tokens)
- Position embeddings: Learned positional information
- Segment embeddings: Distinguishes between sentence pairs (A/B)

## Key Innovations

1. **Bidirectional Context**
   - Processes all tokens simultaneously
   - Allows true bidirectional representations
   - Differs from unidirectional models like GPT

2. **Pre-training Tasks**
   - **Masked Language Modeling (MLM)**: 
     - Randomly masks 15% of tokens
     - Trains model to predict masked tokens
   - **Next Sentence Prediction (NSP)**:
     - Predicts if sentence B follows sentence A
     - Teaches model to understand sentence relationships

3. **Transfer Learning Approach**
   - Two-step process:
     1. Pre-train on large unlabeled text corpus
     2. Fine-tune for specific downstream tasks with minimal task-specific parameters

## Performance Highlights
Achieved state-of-the-art results on:
- GLUE benchmark
- SQuAD v1.1 and v2.0 (question answering)
- SWAG (commonsense inference)

## Code Implementation


## Relationship to Other Models
- **GPT**: Unidirectional transformer vs BERT's bidirectional approach
- **ELMo**: Shallow concatenation of independent LSTMs vs BERT's joint context conditioning
- **Derivatives**: RoBERTa, ALBERT, DistilBERT, and more

## Implementation Resources
- [Hugging Face Transformers](https://github.com/huggingface/transformers)
- [Official TensorFlow Implementation](https://github.com/google-research/bert)
- [BERT Explained Resources](http://jalammar.github.io/illustrated-bert/)

## Further Reading
1. RoBERTa: A Robustly Optimized BERT Pretraining Approach
2. ALBERT: A Lite BERT for Self-supervised Learning
3. DistilBERT: A distilled version of BERT

## Impact
BERT demonstrated the power of bidirectional context and pre-training, leading to significant advances in language understanding and establishing the transfer learning paradigm that now dominates modern NLP.

## Citation
```bibtex
@article{devlin2018bert,
  title={BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding},
  author={Devlin, Jacob and Chang, Ming-Wei and Lee, Kenton and Toutanova, Kristina},
  journal={arXiv preprint arXiv:1810.04805},
  year={2018}
}
```
