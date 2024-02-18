---
layout: post
title: Coding the Central Dogma
date: 2023-11-4 00:00:00 +0300
description: Sequence manipulation, file processing, and visualization in python for understanding the central dogma # Add post description (optional)
img: workflow.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Academic, Python] # add tag
---

### The Goal

---

[Project 1: Coding the Central Dogma](https://www.notion.so/Project-1-Coding-the-Central-Dogma-bbdd6c53472f441daf530b78f1170bf9?pvs=21)

This project follows the above guidelines using Python in order to build functions and a class for sequence manipulation, file processing, and visualization.

### The Design

---

### **Task 1: DNA Sequence Operations**

1. **`dna_complementary`** finds the complementary sequence for a given DNA sequence.
    - Handles both lower and upper case letters, outputs only upper case letters.
    - Includes an argument **`direction`** to define the complementary sequence direction (same or reverse).
    - Catches errors for non-canonical bases or non-DNA sequences, outputting a **`ValueError`** with an informative message.
2. **`dna_rna`** finds the RNA sequence for a given DNA sequence.
    - Replaces 'T' with 'U'.
    - Handles cases where the sequence is already an RNA sequence, outputs a message indicating it's an RNA molecule.
    - Catches errors for non-canonical bases or non-RNA sequences, outputting a **`ValueError`** with an informative message.
3. **`rna_aa`** finds the amino acid sequence for a given RNA sequence.
    - Use the RNA Codon Table to map triplets to amino acid symbols. Map stop codons to '*'.
4. **`dna_aa`** combines the above functions and outputs an amino acid sequence given a DNA sequence.
    - Allows parameters for **`direction`** (same/reverse).
5. Annotates a protein sequence (obtained from NCBI’s protein database) using packages **`minotaur`** and **`dna_features_viewer`**.

### **Task 2: FastQ File Processing**

1. `**extract_seqs`** reads a FastQ file and extracts sequences with quality scores above Q10.
    - Uses Illumina quality score encoding.
    - Outputs a dictionary of **`id: sequence`** for passing sequences.
2. **`Genome`** class with methods for various sequence operations.
    - Method 1: Extract sequences passing a quality threshold.
    - Method 2: Find complementary sequences for passed sequences.
    - Method 3: Find RNA sequences for passed sequences.
    - Method 4: Find amino acid sequences for passed RNA sequences.
    - Method 5: Annotated plot of amino acid sequence for a specific
