---
order: 994
---

# Spatial Transcriptomics

The HTAN data model for spatial transcriptomics data is based upon the both imaging and single cell sequencing data models. These form a collection of  metadata fields where transcriptomic levels (or gene or protein level measures) can be mapped to locations on a tissue slide and were developed in consultation with the data generating centers who are both experts in imaging metadata (e.g., DICOM and OME) and multiple large-scale atlas projects.

For further information on spatial transcriptomics see the [10X guide on ST](https://www.10xgenomics.com/spatial-transcriptomics). The HTAN data model for spatial transcriptomics was intended initially for 10X Visium, but in the near future more platforms will be supported including Nanostring GeoMX, Pick-Seq, 

As with other data model, 10X Visium data levels are provided as follows:

| Level | Description                                                                                                                              |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| RNA-seq Level 1 | Files contain raw RNA-seq data associated with spot/slide data.                                                                |
| RNA-seq Level 2 | Alignment workflows downstream of Spatial Transcriptomics RNA-seq Level 1.                                                     |
| Auxiliary Files | Auxiliary data associated with spot/slide analysis (aligned Images, quality control files, etc) from Spatial Transcriptomics.  |
| RNA-seq Level 3 | Processed data files based on Spatial Transcriptomics RNA-seq Level 2 and Spatial Transcriptomics Auxiliary files.             |
| RNA-seq Level 4 | Processed data files based on Spatial Transcriptomics RNA-seq Level 3.
