---
order: 996
---

# Sequencing Data

HTAN supports multiple sequencing modalities including Single Cell and Single Nucleus RNA Seq (sc/snRNASeq), Single Cell ATAC Seq, Bulk RNA Seq and Bulk DNA Seq.

The HTAN standard for gene annotations is [GENCODE Version 34](https://www.gencodegenes.org/human/release_34.html). [GENCODE](https://www.gencodegenes.org/) is used for gene definitions by many consortia, including ENCODE, NCI Genomic Data Commons, Human Cell Atlas, and PCAWG (Pan-Cancer Analysis of Whole Genomes). Ensembl gene content is essentially identical to that of GENCODE ([FAQ](https://www.gencodegenes.org/pages/faq.html)) and interconversion is possible.

HTAN has adopted the [GENCODE 34](https://www.gencodegenes.org/human/release_34.html) Gene Transfer Format ([GTF](https://useast.ensembl.org/info/website/upload/gff.html)) comprehensive gene annotation file (GENCODE 34 GTF) and filtered files (GENCODE 34 GTF with genes only; GENCODE 34 GTF with genes only and retaining only chromosome X copy of pseudoautosomal region) for HTAN gene annotation. Note that HTAN also includes data generated with other gene models, as the process of implementing the standard is ongoing. Within HTAN metadata files, the reference genome used can be found in the attribute “Genomic Reference” and “Genomic Reference URL”.

In alignment with The Cancer Genome Atlas and the NCI Genomic Data Commons, sequencing data are divided into four levels:

| Level | Definition                 | Example Data                             |
| ----- | -------------------------- | ---------------------------------------- |
| 1     | Raw data                   | FASTQs, unaligned BAMs                   |
| 2     | Aligned primary data       | Aligned BAMs                             |
| 3     | Derived biomolecular data  | Gene expression matrix files, VCFs, etc. |
| 4     | Sample level summary data. | t-SNE plot coordinates, etc.             |
