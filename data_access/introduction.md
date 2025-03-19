---
order: 1000
---

# Introduction

HTAN Data includes both assay files and [metadata](../data_submission/metadata.md). All HTAN metadata are **open access data** whereas assay files may be either **access-controlled** or **open access**.

!!! Access Levels
**open access**: de-identified clinical and biospecimen data, multiplex images, and processed genomic data. Access to this data is mainly provided via Synapse (assay files) and Google Big Query (metadata).  \
**access-controlled**: includes unprocessed genomic data, e.g. fastq and BAM files. Similar to TCGA BAM files, this data is available via [an approved dbGaP mechanism](db_gap.md). Access to this data is controlled by the NCI CRDC Cancer Data Service (CDS).
!!!

The [HTAN Data Portal](https://humantumoratlas.org/explore) provides an overview of all released data. The Portal is an interactive website which can be used to filter and explore the data. While primary access to assay data is provided either via Synapse (open access data) or CDS (access-controlled data), HTAN supports various mechanisms of data access and visualization. Table 1 summarizes these data access and visualization mechanisms.   

Table 1. Data Access and Visualization

| Access Level | Data Type | Access/visualization mechanism | Purpose | Requires dbGAP approval |
|------------|-----------|--------------------------------|---------|-------------------------|
| Open | Assay Files and Metadata | Synapse | File download | No |
| Open | Metadata and a subset of Assay Data | Google BigQuery | Query and download | No |
| Open | Processed sc/snRNA-seq Data | CELLxGENE | Data visualization and download | No |
| Open | Processed sc/snRNA-seq Data | Xena | Data visualization | No |
| Open | Image files | Minerva | Image visualization -- rendered images and stories | No |
| Open | Processed data | cBioPortal | Data exploration | No |
| Open | Assay files | Cancer Genomics Cloud (CGC) | Cloud processing and analysis | No |
| Controlled | Assay Files | CDS | File download | Yes |
| Controlled | Assay files | Cancer Genomics Cloud (CGC) | Cloud processing and analysis | Yes |