---
order: 1000
---

# Introduction

HTAN Data includes both assay files and [metadata](../data_submission/metadata.md). All HTAN metadata are **open access data** whereas assay files may be either **access-controlled** or **open access**.

!!! Access Levels
**open access**: de-identified clinical and biospecimen data, multiplex images, and processed genomic data. Access to this data is mainly provided via [Synapse](https://synapse.org).  \
**access-controlled**: includes unprocessed genomic data, e.g. fastq and BAM files. Similar to TCGA BAM files, this data is available via [an approved dbGaP mechanism](db_gap.md). Access to this data is controlled by the National Cancer Institute (NCI) Cancer Research Data Commons (CRDC) [Cancer Data Service (CDS)](https://datacommons.cancer.gov/repository/cancer-data-service).
!!!

The [HTAN Data Portal](https://humantumoratlas.org/explore) provides an overview of all released data and serves as an interface through which all data access can occur. While most data storage and direct data access occurs via Synapse (open access data) and CDS (access-controlled data), HTAN supports many other mechanisms of data access and visualization. These include:

- [Google BigQuery](biq_query.md) for analysis of metadata and a subset of processed assay data.
- The [NCI CRDC Imaging Data Commons (IDC)](https://portal.imaging.datacommons.cancer.gov/) for image file visualization and download.
- [Seven Bridges Cancer Genomic Cloud (SB-CGC)](https://www.cancergenomicscloud.org/) for cloud processing and analysis of data.
- [CELLxGENE](../data_visualization/cell_by_gene.md) for visualization of processed single cell/single nuclei RNA-sequencing (sc/snRNA-seq) data.
- [Xena](../data_visualization/xena.md) for visualization of sc/snRNA-seq and multi-immunofluorescence data.
- [Minerva](../data_visualization/minerva.md) for visualization of rendered images and stories.
- [cBioPortal](https://www.cbioportal.org/) for data exploration and visualization.