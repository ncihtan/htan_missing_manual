---
order: 1000
---

# Introduction

HTAN Data includes both assay files and [metadata](../data_submission/metadata.md). All HTAN metadata are **open access data** whereas assay files may be either **access-controlled** or **open access**.

!!! Access Levels
**open access**: de-identified clinical and biospecimen data, multiplex images, and processed genomic data. Access to this data is mainly provided via <a href="https://synapse.org" target="_blank" rel="noopener noreferrer">Synapse</a>  \
**access-controlled**: includes unprocessed genomic data, e.g. fastq and BAM files. Similar to TCGA BAM files, this data is available via [an approved dbGaP mechanism](db_gap.md). Access to this data is controlled by the National Cancer Institute (NCI) Cancer Research Data Commons (CRDC) <a href="https://datacommons.cancer.gov/repository/general-commons" target="_blank" rel="noopener noreferrer">General Commons (GC)</a>.
!!!

The <a href="https://humantumoratlas.org/explore" target="_blank" rel="noopener noreferrer">HTAN Data Portal</a> provides an overview of all released data and serves as an interface through which all data access can occur. While most data storage and direct data access occurs via Synapse (open access data) and GC (access-controlled data), HTAN supports many other mechanisms of data access and visualization. These include:

- [Google BigQuery](biq_query.md) for analysis of metadata and a subset of processed assay data.
- The <a href="https://portal.imaging.datacommons.cancer.gov/" target="_blank" rel="noopener noreferrer">NCI CRDC Imaging Data Commons (IDC)</a> for image file visualization and download.
- <a href="https://www.cancergenomicscloud.org/" target="_blank" rel="noopener noreferrer">Seven Bridges Cancer Genomic Cloud (SB-CGC)</a> for cloud processing and analysis of data.
- [CELLxGENE](../data_visualization/cell_by_gene.md) for visualization of processed single cell/single nuclei RNA-sequencing (sc/snRNA-seq) data.
- [Xena](../data_visualization/xena.md) for visualization of sc/snRNA-seq and multi-immunofluorescence data.
- [Minerva](../data_visualization/minerva.md) for visualization of rendered images and stories.
- <a href="https://www.cbioportal.org/" target="_blank" rel="noopener noreferrer">cBioPortal</a> for data exploration and visualization.