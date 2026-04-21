# Phase 2 Whole Exome Sequencing

+++ Overview
# Overview
Phase 2 HTAN data standards for Whole Exome Sequencing (WES) are similar to those implemented in Phase 1 under the assay type "Bulk DNA-seq".

Metadata requirements are documented in the HTAN Data Model <a href="https://htan2-data-model.readthedocs.io/en/main/" target="_blank" rel="noopener noreferrer">readthedocs</a> pages. This part of the manual describes **file requirements** for Whole Exome Sequencing data.

+++ Data Levels
## Data Levels

WES data has 3 levels.

Table 1 HTAN Data Levels for WES Data

| Level | Definition | Example Data |
|-------|------------|--------------|
| 1 | Raw data | FASTQs, Unaligned BAMs |
| 2 | Aligned primary data | Aligned BAMs |
| 3 | Derived biomolecular data | VCFs (mafs optional) | 

+++ Reference and Annotation Versions
## Genomic Reference and Annotation Version
HTAN data contributors must provide the genomics reference and annotation version used for any aligned sequencing files. This information can be found in the level 2 metadata. HTAN strongly recommends using GENCODE/Ensembl genome annotations for level 2 sequencing data.

+++ File Requirements
## File Requirements

!!! Terminology:
This document uses the following terms from IEFT RFC 2119

MUST / REQUIRED / SHALL:  ✅ (denotes absolute requirement)

MUST NOT / SHALL NOT: ❌ (denotes absolute prohibition)

SHOULD / RECOMMENDED: 🌟 (denotes recommendation)

SHOULD NOT / NOT RECOMMENDED: :no_good: (denotes not recommended)

MAY / OPTIONAL: :woman-shrugging: (denotes optional) 
!!!
**Level 1** \
✅	FASTQ files or Unaligned BAM files MUST be submitted for all sequencing data.\
✅	Each FASTQ or Unaligned BAM file MUST have a single record (row) in the manifest. 

**Level 2** \
✅	Level 2 data MUST be submitted if alignment was performed.

**Level 3** \
✅	Level 3 DNA-seq files MUST include a vcf file containing called variants.\
🌟	Level 3 DNA-seq files SHOULD include a seg file if copy number variation was assessed.\
:woman-shrugging:	Submission of maf files is OPTIONAL. 
