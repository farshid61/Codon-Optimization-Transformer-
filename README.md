**Transformer-Based Codon Sequence Prediction**

This project implements a Transformer-based sequence-to-sequence model in PyTorch for predicting coding DNA sequences from amino acid sequences. The model learns codon-usage and sequence-context patterns from the training dataset. Therefore, its predictions reflect the characteristics of the sequences used for training; for example, training on sequences with higher GC content can bias predictions toward higher-GC codon patterns.

The Transformer architecture was implemented based on the principles introduced in “Attention Is All You Need,” including positional encoding, multi-head attention, encoder-decoder attention, residual connections, and feed-forward layers.

Pretrained WordLevel tokenizers for amino-acid, DNA, and RNA sequences are provided in the tokenizers directory. Example paired protein and coding sequences from Oryza sativa are included in the data directory.

The pipeline includes training, validation, testing, and autoregressive inference. During inference, an amino-acid sequence is provided as input, and the model predicts the corresponding codon sequence using greedy decoding by default. The output also reports sequence-level information such as GC content and codon usage.

Model performance can be examined using sequence-quartile accuracy, confusion matrices, precision, recall, and F1-score. The project also provides exploratory analysis of learned amino-acid and codon embeddings using UMAP and K-means clustering to investigate patterns captured by the Transformer.
