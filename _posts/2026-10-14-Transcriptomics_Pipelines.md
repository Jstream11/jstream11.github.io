---
layout: single
title: "On Going: Transcriptomic Pipeline - Snakemake and Nextflow Pipelines"
excerpt: "I’m developing a reproducible bulk RNA-seq workflow using a small public test dataset. The project is to demonstrate scalable workflow automation with Snakemake and Nextflow."

classes: wide
date: 2026-10-14
last_modified_at: 2026-10-14
tags:
  - Snakemake
  - Nextflow
  - Transcriptomics
  - Fastqc
  - Multiqc
  - Fastp
  - Cutadapt
  - Star
  - Salmon
category:
  - professional
---

### Purpose

This git repository contains two versions of a bulk rnaseq pipeline, one in Snakemake and one in Nextflow. The purpose of this code base is to demonstrate proficiency in scalable workflow management. The workflow is designed to supply customizable adapter trimming and alignment/quanitification options. The development is on going.

**Current status:** The Snakemake workflow is in progress; the Nextflow
workflow is in progress. The test reads are for checking the workflow—not for
drawing biological conclusions.

### Planned workflow
```text
Paired FASTQ files
        ↓
Input and samplesheet validation
        ↓
Read QC (FastQC)
        ↓
Adapter trimming (Fastp/Cutadapt)
        ↓
Post-trimming QC (FastQC and MultiQC)
        ↓
Quantification/alignment (Star/Salmon)
        ↓
Alignment QC (MultiQC)
        ↓
Differential Expression
```

[Project README](https://github.com/Jstream11/Transcriptomics_Pipelines)

[Snakemake workflow](https://github.com/Jstream11/Transcriptomics_Pipelines/tree/main/workflows/snakemake)

[Nextflow workflow](https://github.com/Jstream11/Transcriptomics_Pipelines/tree/main/workflows/nextflow)