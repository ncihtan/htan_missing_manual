# Phase 2 Multiplex Microscopy

+++ Overview
# Overview
Multiplex Microscopy defines standards for **2-dimensional (2D)** multiplexed and/or cyclic immunofluorescence imaging assays. It focuses exclusively on multiplexed tissue imaging assays that rely on fluorescence, metal-based, or iterative immunostaining approaches.

Metadata requirements are documented in the HTAN Data Model <a href="https://htan2-data-model.readthedocs.io/en/main/" target="_blank" rel="noopener noreferrer">readthedocs</a> pages. This part of the manual describes **file requirements** for Multiplex Microscopy data.

**Assays/Platforms Covered**:
* Multiplexed and/or cyclic immunofluorescence platforms, including:
    * CODEX, CyCIF, MIBI, mIF, MxIF, mIHC, IMC, SABER
* Specific commercial platforms, such as:
    * Lunaphore COMET, RareCyte Orion, Standard Biotools Hyperion XTi, Akoya Phenocycler Fusion

**Out of Scope**:
* Spatial transcriptomics assays. (e.g., GeoMx, Xenium. See [SpatialOmics](spatialomics_submission.md).)
* Imaging covered in the [Digital Pathology standards](digital_pathology.md) (e.g. H&E).
* Mass Spectrometry Imaging. (Standards currently in development.)
* 3D objects comprised of multiplex tissue imaging. 3-dimensional images and registration of multiplexed images as part of a 3-dimensional object (with data from serial sections of the same specimen) will be convered in future standards.

+++ Data Levels
## Data Levels
Multiplex Microscopy data submissions consist of three data levels. The first data level is 'Level 2' in order to maintain consistency with the HTAN Phase 1 data model. Please see Table 1 and the following text for more information.

Table 1: HTAN Data Levels for Multiplexed Microscopy

| Data Level | Description | Examples |
|------------|-------------|----------|
| Level 2 | Imaging data compiled into a single file format, preferably a tiled and pyramidal OME-TIFF. Accompanied by a csv file containing channel metadata. | image: ome-tiff,  channel metadata: csv |
| Level 3 | Segmentation mask. | ome-tiff |
| Level 4 | An object-by-feature table (typically cell-by-marker) generated from the segmentation mask and image. | csv, h5ad |

**Level 2**:
* Images: Images that are ready for reuse and have completed any preprocessing steps required such as stitching, registration, illumination correction, and compilation. 
* Channel Metadata: Standardized channel metadata file in comma-separated value format (csv). Data in this file should be compatible with information in the image header.

**Level 3**: \
Segmentations only – structured mask data following the Phase 1 HTAN segmentation templates (unchanged).\

**Level 4**: \
Cell-level feature arrays – no changes from prior definitions in HTAN Phase 1.

+++ File Requirements
## Imaging Data Requirements
!!! Terminology:
This document uses the following terms from IEFT RFC 2119

MUST / REQUIRED / SHALL:  ✅ (denotes absolute requirement)

MUST NOT / SHALL NOT: ❌ (denotes absolute prohibition)

SHOULD / RECOMMENDED: 🌟 (denotes recommendation)

SHOULD NOT / NOT RECOMMENDED: :no_good: (denotes not recommended)

MAY / OPTIONAL: :woman-shrugging: (denotes optional) 
!!!

### Channel Metadata
✅	Level 2 Multiplexed Tissue Images must be accompanied by a channel metadata file in comma-separated value format (csv).\
✅	Channel metadata must match channel information provided in the ome-tiff header.\
✅	Channel metadata must be submitted prior to Imaging Level 2 data.

### Level 2
Imaging Level 2 data is for images that have completed any pre-processing steps required and are ready for reuse.\
🌟	Images SHOULD be provided as OME-TIFF.\
✅  Imaging Level 2 data MUST consist of a single file per image/scene.\
✅	Multiple fields of view MUST be separated into individual files.\
🌟	Tissue microarrays SHOULD be dearrayed into one file per TMA core.\
✅	Multi-channel, timepoint, and z-plane images MUST  be provided as a single file.\
✅	Images MUST be de-identified before submission according to the center's de-identification plan.\
❌	Images MUST NOT contain patient identifiers including, but not limited to, name, date of birth, all HIPAA-protected identifiers, and any re-identifiable ID code other than HTAN ID.\
❌	Images MUST NOT contain any dates (such as date of acquisition) that could facilitate reconstruction of participant identity in association with other provided metadata such as ‘Days from index to sectioning’.\
❌	Images MUST NOT contain any dates in any image header or other location. This is a strict requirement of our downstream data repositories. Please contact your [DCC liaison](Data_Liaisons.md) with any questions.\
🌟	OME-TIFF images SHOULD contain an image pyramid.\
🌟	OME-TIFF images SHOULD be tiled.\
:no_good:	The smallest pyramid layer of the OME-TIFF SHOULD NOT be smaller than the tile size.\
✅	OME-TIFF images MUST contain a valid OME-XML in the ImageDescription tag of the first IFD.\
🌟	OME-TIFF images SHOULD have informative Channel Names that match the channel metadata file.\
:no_good:	OME-TIFF images SHOULD NOT contain Structural Annotations in the OME-XML.\
❌	OME-TIFF images MUST NOT contain AcquisitionDate in the OME-XML.\
❌	OME-TIFF images MUST NOT contain DateTime or any other field representing the date of acquisition in the OME-XML Structural Annotations.\
❌	OME-TIFF images MUST NOT contain First Name, Last Name, or Email in the OME-XML Experimenters.\
:no_good:	If you cannot provide OME-TIFF images as described above, you MUST contact your [DCC liaison](Data_Liaisons.md) before submitting data or metadata.

### Level 3
Imaging Level 3 Segmentation data derived from Imaging Level 2 that represents cell or object segmentation.\
✅	Imaging Level 3 Segmentation data MUST be provided as OME-TIFF or TIFF images.\
🌟	Imaging Level 3 Segmentation data SHOULD be a single channel with integer values representing individual objects.\
:woman-shrugging:	Imaging Level 3 Segmentation data MAY contain multiple object types with an object type per channel.\
❌	Imaging Level 3 Segmentation data MUST NOT contain dates or other information that could be used in conjunction with other data or metadata to reconstruct participant identity.

### Level 4
Imaging Level 4 data is an object-by-feature array derived from Imaging Level 2 and Imaging Level 3 Segmentation data.\
✅	Imaging Level 4 data MUST be a CSV or H5AD file.\
✅	Imaging Level 4 data MUST contain a column, columns, or attribute representing object centroid.
🌟	CSV Imaging Level 4 data SHOULD use the columns `X_centroid` and `Y_centroid` to specify object coordinates.\
✅	Imaging Level 4 data MUST contain a column or attribute representing a unique object ID.\
✅	The unique object ID MUST match the ID that is used in the Imaging Level 3 Segmentation data that the Imaging Level 4 data is derived from.\
🌟	CSV Imaging Level 4 data SHOULD use the header `CellID`.\
🌟	Imaging Level 4 data SHOULD use column headers or attribute names that match the channel metadata file provided in Imaging Level 2 metadata. \
:woman-shrugging:  Imaging Level 4 data MAY contain information about object morphology or other characteristics.\
🌟	If information about object morphology is provided it MUST be clear which attributes represent information about markers and which represent information about morphology. This may be done by clear names or positions in the table (e.g. separated by the centroid columns).\
:woman-shrugging:	Imaging Level 4 data MAY summarize information from multiple Imaging Level 2 and Imaging Level 3 Segmentation data.\
✅	If Imaging Level 4 data is derived from multiple parent files, a column or attribute distinguishing which rows correspond to which parent file MUST be included in the table.

+++ :warning: Check File Headers
## Data De-identification
Image files often contain information in their headers, including the date of acquisition. HTAN **cannot accept files with any dates in the header**.  All potentially identifying information must be removed from the header.

* :white_check_mark:  Images **MUST** be de-identified before submission according to the center's de-identification plan.
* :x:	  Images **MUST NOT** contain patient identifiers including, but not limited to, name, date of birth, all HIPAA-protected identifiers, and any re-identifiable ID code other than HTAN ID.
* :x:	  
Images **MUST NOT** contain any dates (such as date of acquisition) that could facilitate reconstruction of participant identity in association with other provided metadata such as ‘Days from index to sectioning’.
* :x:	  
Images **MUST NOT** contain any dates in any image header or other location. This is a strict requirement of our downstream data repositories. Please contact your [DCC liaison](Data_Liaisons.md) with any questions.
