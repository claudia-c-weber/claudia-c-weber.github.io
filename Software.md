---
title: Software
toc: true
header:
  overlay_color: "#333"
---

# Phylogenetic methods
## Modelling contraints on physicochemical amino acid properties

Most codon substitution models treat all nonsynonymous changes as equivalent, regardless of the physicochemical properties of the amino acids involved. "CoRa" is a parametric codon model that allows constraints on radical or conservative amino acid substitutions to be considered separately. The model describes the evolution of protein coding sequences in organisms with large populations and effective selection significantly better than the standard model.

| Repository | Description | Citation |
| -- | -- | -- |
| https://github.com/claudia-c-weber/CoRa | Instructions for running the model | Weber CC and Whelan S (2019). _Physicochemical Amino Acid Properties Better Describe Substitution Rates in Large Populations_. Molecular Biology and Evolution. [https://doi.org/10.1093/molbev/msz003](https://doi.org/10.1093/molbev/msz003) |


## Ancestral protein sequence reconstruction

I contributed to benchmarking [ProtASR 1.0](https://github.com/MiguelArenas/protasr) [(Arenas et al, 2017)](https://academic.oup.com/sysbio/article/66/6/1054/2840014), which addresses a common issue with methods based on empirical substitution models that tend to reconstruct proteins that are more stable than those found in nature. 


# Unsupervised learning for genome assembly
## Identifying sample contamination in long-read sequencing data with VAEs
Samples collected for sequencing often contain genetic material from non-target organisms, and gaps in reference databases often make identifying the source of a sequence challenging. However, two-dimensional representations of composition learned by a Variational Autoencoder can help separate sequences from different sources, even when taxonomic labels are unavailable.

The example below shows HiFi reads from a buff-tip moth sample, which was infected _Wolbachia_ strains:
<img src="https://github.com/user-attachments/assets/ac9bf758-5680-44d9-8a94-b0a873de1791" width=350>

| Repository | Description | Citation |
| -- | -- | -- |
| https://github.com/CobiontID/read_VAE | Code for training the VAE and visualising the embeddings | Weber CC (2024). _Disentangling Cobionts and Contamination in Long-Read Genomic Data using Sequence Composition_. G3 Genes, Genomes, Genetics, [https://doi.org/10.1093/g3journal/jkae187](https://doi.org/10.1093/g3journal/jkae187) |



## K-mer statistics
Along with the VAE workflow, I provide a set of standalone k-mer counting tools suitable for high-quality long read data:

| Tool | Description | Application |
|--|--|--|
| [kmer-counter](https://github.com/CobiontID/kmer-counter) | Fast k-mer counter for large read sets | Get tetranucleotide counts |
| [unique-kmers](https://github.com/CobiontID/unique-kmer-counts) | Count distinct k-mers in sequences | Calculate k-mer diversity |
| [fastk-medians](https://github.com/CobiontID/fastk-medians) | Calculate median number of k-mer occurrences across the whole set for each sequence | Approximate k-mer coverage |

Further details are provided under [https://cobiontid.github.io/](https://cobiontid.github.io/)


## Extracting genomes from mixed samples with chromatin network embeddings
Examining chromatin interactions can be helpful for separating distinct genomes in contaminated assemblies. Though this is often done manually, automated clustering of highly interconnected scaffolds based on graph embeddings provides a convenient approach.

- Code for learning network embeddings and visualizing Hi-C maps: https://github.com/CobiontID/HiC_network
- Preprint: _Kudoa genomes from contaminated hosts reveal extensive gene order conservation and rapid sequence evolution_ [https://www.biorxiv.org/content/10.1101/2024.11.01.621499v1](https://www.biorxiv.org/content/10.1101/2024.11.01.621499v1)

