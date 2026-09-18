## Transformer-based codon prediction

This project uses a Transformer model to predict codon sequences from protein sequences.

The model learns codon usage patterns from the training dataset. For example, if the training sequences have high GC content, the model will tend to predict codons following a similar pattern.

The model was built in PyTorch based on the Transformer architecture from the "Attention Is All You Need" paper.

### How it works

The input is an amino acid sequence and the target is its corresponding DNA sequence. During training, the model learns the relationship between amino acids, codons, and their sequence context.

Pretrained tokenizers for amino acids, DNA, and RNA are already provided in the `tokenizers` folder. Example protein and DNA sequences from *Oryza sativa* are also available in the `data` folder.

During inference, you only need to provide a protein sequence in FASTA format. The model predicts the codon sequence step by step using greedy decoding. The output also provides information such as GC content and codon usage for each amino acid.

### Model evaluation

The code includes several options for checking model performance:

- accuracy across four regions of the protein sequence
- confusion matrix
- precision, recall, and F1-score
- GC content of predicted sequences

I also used UMAP to visualize the learned amino acid and codon embeddings, followed by K-means clustering. This was mainly an exploratory analysis to see whether the model learned interesting relationships among amino acids and codons.
