---
order: 998
---

# File Standards

The HTAN Data Model includes requirements for Assay Files. These include:
1. How Data Files are organized ([Assay Data Levels](#assay-data-levels));
2. What File Formats are accepted ([Accepted File Formats](#accepted-file-formats)); and
3. Specific Assay or Assay Module Requirements ([Specific Requirements](#specific-assayassay-module-requirements)).

## Assay Data Levels
In both the HTAN Phase 1 and Phase 2 Data Models, assay data is divided into levels. Each assay type has levels progressing from raw data to more processed data.  (See Figure 1) For Sequencing data, the HTAN Model Data levels help distinguish data as [open access versus access-controlled](../data_access/introduction.md).  For example, level 1 and 2 sequencing data are access-controlled data. 

==- Figure 1. HTAN Sequencing Data levels (Expand Panel to see Figure.)
![Figure 1. HTAN Sequencing Data levels](../img/sequencing_data_levels.svg)
===

==- Phase 2 Assay Data Levels
### Phase 2 Assay Data Levels
The Phase 2 Data Model is still being developed. This page will be updated as these updates occur. The following are the currently supported assays, organized alphabetically.

| Assay Type | Level |	Definition | Example Data | Notes |
|------------|-------|-------------|--------------|-------|
| DigitalPathology | 2 | Imaging data compiled into a single file format which is compatible with [Bio-Formats](https://www.openmicroscopy.org/bio-formats/) or [openslide python](https://openslide.org/api/python/). | .ome-tiff, .qptiff, .svs, .tif, .dcm, .ndpi. .vms, .vmu, .scn, .mrxs, .tiff, .svslide, .bit, .czi | currently, there is only one file level for DigitalPathology |
| MultiplexedMicroscopy | 2 | Imaging data compiled into a single file format, preferably a tiled and pyramidal OME-TIFF. Accompanied by a csv file containing channel metadata. | image: ome-tiff; channel metadata: csv | there is no level 1 for MultiplexMicroscopy |
|| 3 | Segmentation mask. | ome-tiff | |
|| 4 | An object-by-feature table (typically cell-by-marker) generated from the segmentation mask and image. | csv, h5ad |
| scRNA-seq | 1 | raw sequence data. | fastq, fastq.gz ||
|| 2 | aligned sequence data. | bam, cram ||
|| 3_4 | sample level summary information, e.g. cell annotations, t-SNE/UMAP coordinates, etc. | h5ad | level 3_4 files have specific format and content requirements. Please see [Specific Assay/Assay Module Requirements](#specific-assayassay-module-requirements). |
| SpatialOmics | 1 | Optional level for submission of controlled-access experiment data. | compressed archive (.tar.gz, .zip) containing raw data (e.g. FASTQs, BAMS) | Submission of level 1 is **not required** |
|| 3 | A compressed archive (e.g., .tar.gz, .zip) containing platform-specific output files. Should include segmentation outputs, raw or normalized matrices, and any relevant vendor JSONs, manifest files, or images.  | compressed archive (.tar.gz, .zip)| level 3 bundles **cannot contain controlled-access data** such as FASTQs or BAMs. There is no level 2 for SpatialOmics.|
|| Panel | Panel information if the assay uses a targeted sequencing or protein panel. | csv ||
|| 4 | A harmonized output file for downstream analysis. | AnnData h5ad or seurat compatible RDS | level 4 is optional. A HTAN-standardized format for these files (similar to level 3_4 scRNA-seq data) has not been developed, but may exist in the future. |
| WES | 1	| Raw data	| fastq, fastq.gz ||
||2	| Aligned primary data |	bam, cram ||
||3	| Derived biomolecular data	| vcf, vcf.gz | |

===

==- Phase 1 Assay Data Levels
### Phase 1 Assay Data Levels

Phase 1 data was divided into 4 levels for most assay types. Exceptions include:
- some assays did not have a level 1 (RPPA) or level 1 data was typically not collected (Imaging), but higher levels exist; 
- some assays did not have higher levels such as scDNA-seq and scmC-seq (only levels 1 and 2), Bulk DNA, Bulk RNA, HiC and Bulk Methylation Sequencing (only levels 1-3);
- spatial transcriptomics assays had platform-specific data levels which deviated from the traditional 4 levels. Specifically,
    - some platforms have only one experiment level instead of multiple file levels (10X Xenium ISS and Nanostring CosMx SMI); and
    - some platforms have additional files (auxiliary or annotation metadata) which were not a part of the typical 4 level system (e.g. 10X Visium, Nanostring GeoMx DSP).

Please see the Table below for more information.

| Assay Type | Level |	Definition | Example Data | Notes |
|------------|-------|-------------|--------------|-------|
| Electron Microscopy | 1|	Raw electron microscopy data as one TIFF file per plane for a 3D image stack or per tile for a 2D large area montage. |	tiff ||
||2	|Processed electron microscopy data as one OME-TIFF image per plane or montage. |	ome-tiff ||
||3	|Segmented electron microscopy data. |	am, tiff ||
||4	| Movies or other derived files from electron microscopy data. |	mp4, csv ||
| Imaging | 1 | Raw imaging data requiring tiling, stitching, illumination correction, registration or other pre-processing. | svs, tiff | usually not submitted |
||2	|Imaging data compiled into a single file format, preferably a tiled and pyramidal OME-TIFF. Accompanied by a csv file containing channel metadata. | ome-tiff + csv||
||3	| Segmentation mask, Validated channel metadata, QC checked image. | ome-tiff ||
||4 |An object-by-feature table (typically cell-by-marker) generated from the segmentation mask and image. | csv ||
| Mass Spectrometry | 1	| Raw spectral data. |	mz5,dta,ms2,ms1,mzXML,mzML,mzData ||
||2	| Spectrum match peaks.	| Peptide spectrum match (PSM) in csv format ||
|| 3 |	Peptide Group information | Combined peptide spectrum as csv or tsv files ||
||4	| Protein Abundance. |	csv, tsv ||
| RPPA | 2 | Primary data. Array based protemics. | csv | (No level 1 for RPPA)|
|| 3 | Intra-batch normalized intensities. | txt,csv ||
|| 4 | Intra-batch corrected intensities. | txt ||
| Sequencing | 1	| Raw data	| FASTQs, unaligned BAMs ||
||2	| Aligned primary data |	Aligned BAMs ||
||3	| Derived biomolecular data	| Gene expression matrix files, VCFs, etc. | no level 3 for scDNA-seq and scmC-seq |
||4	| Sample level summary data. |	t-SNE plot coordinates, etc. | no level 4 for scDNA-seq, scmC-seq, Bulk DNA-seq, Bulk RNA-seq, HiC-Seq, Bulk Methylation-Seq |
| Spatial Transcriptomics, Nanostring CosMx SMI | Experiment | RNA and Protein Panel assays applied as part of Nanostring CosMx Spatial Molecular Imager (SMI) | experiment bundle submitted instead of multiple file levels. |
| Spatial Transcriptomics, Nanostring GeoMx DSP| 1 | Files contain raw data output from the NanoString GeoMx DSP Pipeline. These can include RCC or DCC Files. | rcc, dcc||
|| 3 | Files contain processed data from the NanoString GeoMx DSP Pipeline. This level depends on GeoMx Level 1 and Imaging Level 2. | csv | Associated ome-tiff images submitted using the Imaging Level 2 manifest. |
|| DCC ROI Segment Annotation | GeoMx ROI and Segment Metadata Attributes. The assayed biospecimen should be reported one per row with the associated ROI coordinates. | ||
|| RCC ROI Segment Annotation | GeoMx ROI and Segment Metadata Attributes. The assayed biospecimen should be reported one per row with the associated ROI coordinates. | ||
| Spatial Transcriptomics, Slide-Seq | 1 | Raw sequencing files for the Slide-seq assay. | tar.gz (FASTQ) ||
|| 2 | Aligned sequencing files and QC for the Slide-seq assay. | BAM ||
|| 3 | Gene matrices with features and barcodes for Slide-seq as well as spatial information (bead location files). | tsv, mtx.gz ||
| Spatial Transcriptomics, 10x Visium | 1 | Files contain raw RNA-seq data associated with spot/slide data. | FASTQ ||
|| 2 | Alignment workflows downstream of Spatial Transcriptomics RNA-seq Level 1. | Aligned BAMS ||
|| 3 | Processed data files based on Spatial Transcriptomics RNA-seq Level 2 and Spatial Transcriptomics Auxiliary files. | Barcodes, features, filtered and unfiltered matrices ||
|| 4 | Processed data files based on Spatial Transcriptomics RNA-seq Level 3. | Clustering, t-SNE coordinates, h5ad, RDS | |
|| Auxiliary | Auxiliary data associated with spot/slide analysis (aligned Images, quality control files, etc) from Spatial Transcriptomics. Additional data such as imaging, qc, and json scale factors. | TIFF, JPG, PNG, JSON, HTML, etc. ||
| Spatial Transcriptomics, 10X Xenium ISS | Experiment | All data pertaining to the 10X Genomics Xenium In-Situ Hybridization experiment | experiment bundle | experiment bundle submitted instead of multiple file levels. |
===
==- Phase 2 vs Phase 1 Assay Data Levels
### Phase 2 vs Phase 1 Assay Data Levels
As outlined in the [Data Model Introduction](overview.md), the Phase 1 and Phase 2 HTAN Data Models Differ.  In terms of assay data levels, currently, the following differences exist.

| Assay Modules | Example Assays | Phase 1 Levels | Phase 2 Levels | Change |
|-------|--------------|----------------|----------------|--------|
| Bulk DNA/WES | WES | 3 | 3 | No Change to levels. Module name changed from "Bulk DNA" to "WES" |
| DigitalPathology (Phase 2 only) | H&E | NA | level 2 only | DigitalPathology is a new Assay Module. In Phase 1, this data type would have been submitted as "Imaging". |
| Imaging (Phase 1 only)| H&E, CODEX, CyCIF, MIBI, mIF, MxIF, mIHC, IMC |    4 | NA | "Imaging" broken into two separate modules -- Digital Pathology and Multiplexed Tissue Imaging. |
| MultiplexedMicroscopy (Phase 2 only)| CODEX, CyCIF, MIBI, mIF, MxIF, mIHC, IMC, SABER | NA | levels 2-4 only (no level 1) | MultiplexedMicroscopy is a new Assay Module. In Phase 1, this data type would have been submitted as "Imaging".|
| scRNA-seq | single cell or nuclei RNA-seq | 4 | 3 total levels (1, 2, and level 3/4) | Level 3 and 4 combined into one level for submission of standardized h5ad files. See [Specific Assay/Assy Module Requirements](#specific-assayassay-module-requirements) for more information. |
| Spatial Transcriptomics/SpatialOmics | 10X Visium, 10X Xenium, Nanostring CosMX | platform-specific levels | 1 required level (level 3, experiment bundle) with an accompanying spatial panel information file; optional levels 1 and 4 | Change from platform-specific Spatial Transcriptomics models to a unified SpatialOmics model which can accomodate additional -omic data types. Note: level 3 bundles **cannot contain controlled-access data** such as FASTQs or BAMs.| 
===

## Accepted File Formats
In HTAN Phase 2, there are specific requirements for file formats which are checked for each assay type. Please expand the panel below for more information.

==- HTAN Phase 2 Accepted File Formats
| Assay Type | Level |	Accepted File Types |
|------------|-------|----------------------|
| DigitalPathology | 2 | [Bio-Formats](https://www.openmicroscopy.org/bio-formats/) or [openslide python](https://openslide.org/api/python/) compatible format. (e.g. ome-tiff, tiff, qptiff, svs) |
| MultiplexedMicroscopy |2 | ome-tiff preferred, [Bio-Formats](https://www.openmicroscopy.org/bio-formats/) or [openslide python](https://openslide.org/api/python/) compatible format accepted.|
|| 3 | ome-tiff |
|| 4 | csv, h5ad |
|scRNA-seq | 1 | fastq, fastq.gz |
|| 2 | bam, cram ||
|| 3/4 | h5ad |
|SpatialOmics | 1 | gz, tar.gz |
|| 3 | gz, tar.gz |
|| Panel | csv |
|| 4 | gz, tar.gz |
| WES | 1| fastq, fastq.gz |
|| 2 | bam, cram |
|| 3 | vcf, vcf.gz |
===

## Specific Assay/Assay Module Requirements

==- Genomic References and Annotation Versions
### Genomic References and Annotation Versions
HTAN does not restrict data contributors to a specific genomic reference or annotation versions for most sequencing data with the exception of level 3/4 scRNA-seq data. Please see the [Phase 2 Single Cell RNA-seq page](../data_submission/scrnaseq_data_submission.md) for more information regarding the scRNA-seq requirements.

However, HTAN data contributors must provide the genomics reference and annotation version used for any aligned sequencing files. This information can be found in the level 2 metadata.   
===
==- Digital Pathology and MultiplexMicroscopy
### Digital Pathology and MultiplexMicroscopy
HTAN can only accept [de-identified information](../data_submission/Data_Deidentification.md). Imaging equipment will often capture dates and other information and store this in the header of the resulting image file. **HTAN cannot accept image files with any dates in the header**. All image files must have dates or other identifying information removed from the image file header. 
===
==- scRNA-seq
### scRNA-seq
Specific file requirements for single cell RNA-seq h5ad files are modeled after [CELLxGENE's requirements](https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data). Please see the [Phase 2 Single Cell RNA-seq page](../data_submission/scrnaseq_data_submission.md) for more information.  
===