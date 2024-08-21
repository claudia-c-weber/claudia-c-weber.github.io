---
title: Software
toc: true
header:
  overlay_color: "#333"
---

# Phylogenetic methods
## Modelling contraints on physicochemical amino acid properties

Most codon substitution models treat all nonsynonymous changes as equivalent, regardless of the physicochemical properties of the amino acids involved. "CoRa" is a parametric codon model that allows constraints on radical or conservative amino acid substitutions to be considered separately. The model describes the evolution of protein coding sequences in organisms with large populations and effective selection significantly better than the standard model.

<details>
<summary>Expand for more details...</summary>
  
- Instructions for running the model are available under: https://github.com/claudia-c-weber/CoRa
  
- Details can be found in: Weber CC and Whelan S (2019). _Physicochemical Amino Acid Properties Better Describe Substitution Rates in Large Populations_. Molecular Biology and Evolution. https://doi.org/10.1093/molbev/msz003

</details>

## Ancestral protein sequence reconstruction

I contributed to benchmarking [ProtASR 1.0](https://github.com/MiguelArenas/protasr) [(Arenas et al, 2017)](https://academic.oup.com/sysbio/article/66/6/1054/2840014), which addresses a common issue with methods based on empirical substitution models that tend to reconstruct proteins that are more stable than those found in nature. 


# Unsupervised learning for genome assembly
## Identifying sample contamination in long-read sequencing data 
Samples collected for sequencing often contain genetic material from non-target organisms, and gaps in reference databases often make identifying the source of a sequence challenging. However, two-dimensional representations of composition learned by a Variational Autoencoder can help separate sequences from different sources, even when taxonomic labels are unavailable.

<details>
<summary>Expand for illustration and more info...</summary>

The example below shows HiFi reads from a buff-tip moth sample, which was infected _Wolbachia_ strains:
<img src="https://github.com/user-attachments/assets/ac9bf758-5680-44d9-8a94-b0a873de1791" width=400>

- Code for training the VAE and visualising the embeddings is available from: https://github.com/CobiontID/read_VAE
- A description of the method can be found here:  _Disentangling Cobionts and Contamination in Long-Read Genomic Data using Sequence Composition_. G3 Genes|Genomes|Genetics, https://doi.org/10.1093/g3journal/jkae187

</details>

## K-mer statistics
Along with the VAE workflow, I provide a set of standalone k-mer counting tools suitable for high-quality long read data:
<details>
<summary>Show overview of tools...</summary>

| Tool | Description | Application |
|--|--|--|--|
| [kmer-counter](https://github.com/CobiontID/kmer-counter) | Fast k-mer counter for large read sets | Get tetranucleotide counts |
| [unique-kmers](https://github.com/CobiontID/unique-kmer-counts) | Count distinct k-mers in sequences | Calculate k-mer diversity |
| [fastk-medians](https://github.com/CobiontID/fastk-medians) | Calculate median number of times each large k-mer in a sequence occurs across the set | Approximate k-mer coverage |

Further details are provided under https://cobiontid.github.io/

</details>

## Extracting genomes from mixed samples with chromatin network embeddings
Examining chromatin interactions can be helpful for separating distinct genomes in contaminated assemblies. Though this is often done manually, automated clustering of highly interconnected scaffolds based on graph embeddings provides a convenient approach.

<details>
<summary>Show more...</summary>
  
- Code for learning network embeddings and visualizing Hi-C maps: https://github.com/CobiontID/HiC_network
- Preprint coming soon...
</details>
