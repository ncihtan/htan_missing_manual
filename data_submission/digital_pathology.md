---
order: 992
---

# Phase 2 Digital Pathology

+++ Overview
# Overview
Digital pathology includes patch, tile, region of interest (ROI) or whole-slide imaging (WSI) derived from hematoxylin and eosin (H&E) or other tissue-based assays. It does not include multiplexed tissue images.  Please see [Phase 2 Multiplex Microscopy](multiplex_microscopy.md) for 2-dimensional (2D) multiplexed and/or cyclic immunofluorescence imaging assays

Metadata requirements are documented in the HTAN Data Model <a href="https://htan2-data-model.readthedocs.io/en/main/" target="_blank" rel="noopener noreferrer">readthedocs</a> pages. This part of the manual describes **file requirements** for Digital Pathology data.

+++ Data Levels
## Data Level
Digital Pathology submissions consist of only one data level. This data level will be called ‘Level 2’ in order to maintain consistency with the HTAN Phase 1 data model.

Table 1: HTAN Data Levels for Digital Pathology

| Data Level | Description | Examples |
|------------|-------------|----------|
| Level 2 | Imaging data compiled into a single file format which is compatible with [Bio-Formats](https://www.openmicroscopy.org/bio-formats/) or [openslide python](https://openslide.org/api/python/). | .ome-tiff, .qptiff, .svs, .tif, .dcm, .ndpi. .vms, .vmu, .scn, .mrxs, .tiff, .svslide, .bit, .czi |

+++ File Formats
## File Formats

All image data must be compiled into a single file format which is compatible with [Bio-Formats](https://www.openmicroscopy.org/bio-formats/) or [openslide python](https://openslide.org/api/python/).  

The HTAN Data Coordinating Committee (DCC) has implemented validation criteria which checks the file extension. A subset of the most common compatible formats is currently a part of that validation.  Please see the Module-Specific Attributes in the HTAN Data Model <a href="https://htan2-data-model.readthedocs.io/en/main/docs/digitalpathology.html#module-specific-attributes" target="_blank" rel="noopener noreferrer">readthedocs</a> for a list of file formats which are currently in the data model. If your file is Bio-Formats or openslide python compatible, but not a part of the current validation list, please contact your [Data Liaison](Data_Liaisons.md).

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

## Digital Pathology Level 2

✅	Images MUST be provided as [Bio-Formats](https://www.openmicroscopy.org/bio-formats/) or [openslide python](https://openslide.org/api/python/) compatible formats.\
✅	Imaging Level 2 data MUST consist of a single file per image/scene.\
✅	Multiple fields of view MUST be separated into individual files.\
🌟	Tissue microarrays SHOULD be de-arrayed into one file per TMA core.\
✅	Images MUST be de-identified before submission according to the center's de-identification plan.\
❌	Images MUST NOT contain patient identifiers including, but not limited to, name, date of birth, all HIPAA-protected identifiers, and any re-identifiable ID code other than HTAN ID.\
❌	Images MUST NOT contain any dates (such as date of acquisition) that could facilitate reconstruction of participant identity in association with other provided metadata such as ‘Days from index to sectioning’.\
❌	Images MUST NOT contain any dates in any image header or other location. This is a strict requirement of our downstream data repositories. Please contact your [DCC liaison](Data_Liaisons.md) with any questions. This includes AcquisitionDate.\
❌	Images MUST NOT contain visible identifying information (such as the edge of an unredacted slide label visible in the macro image).\
✅	The center MUST check redaction by pen or sticker to ensure redacted information is not visible by contrast enhancement or other image manipulation.\
✅	Brightfield images MUST be provided as Imaging Level 2.\
🌟	Brightfield images SHOULD be encoded as SamplesPerPixel = 3 and photometric interpretation RGB or YbCr.\
:no_good: Brightfield images SHOULD NOT be provided as 3-channel images.


+++ :warning: Check File Headers
## Data De-identification
Image files often contain information in their headers, including the date of acquisition. HTAN **cannot accept files with any dates in the header**.  All potentially identifying information must be removed from the header.

* :white_check_mark:  Images **MUST** be de-identified before submission according to the center's de-identification plan.
* :x:	  Images **MUST NOT** contain patient identifiers including, but not limited to, name, date of birth, all HIPAA-protected identifiers, and any re-identifiable ID code other than HTAN ID.
* :x:	  
Images **MUST NOT** contain any dates (such as date of acquisition) that could facilitate reconstruction of participant identity in association with other provided metadata such as ‘Days from index to sectioning’.
* :x:	  
Images **MUST NOT** contain any dates in any image header or other location. This is a strict requirement of our downstream data repositories. Please contact your [DCC liaison](Data_Liaisons.md) with any questions.
