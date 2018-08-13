# RandomSequenceGeneratoR
This repository describes a R workflow for the generation of random DNA sequences, based on the approach described in Tourlousse et al. (2017).

**Approach:**
The process for generating the sequences starts from a set of random k-mers that are subsequently concatenated into longer sequences and screened based on user-defined conditions, namely homopolymers, GC content, repeats, palindromes and between-sequence identity.

## Loading required R packages

```
library(dplyr)
library(Biostrings)
library(stringr)
library(stringi)
library(seqinr)
```

## Generating set of k-mers

A set of k-mers is generated using R's `sample` command, using the following set of parameters:

`kmer_seed` = 123
`kmer_size` = 12
`kmer_count` = 10000
`kmer_baseProbabilitiesACGT` = c(0.25,0.25,0.25,0.25)
`kmer_GClow` = 30
`kmer_GChigh` = 70
`kmer_maximumLengthHompolymers` = 4
