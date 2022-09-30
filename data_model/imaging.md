---
order: 995
---

# Imaging Data

The HTAN data model for imaging data is based upon the [Minimum Information about Tissue Imaging (MITI)](https://www.miti-consortium.org/) reporting guidelines. These comprise minimal metadata for highly multiplexed tissue images and were developed in consultation with methods developers, experts in imaging metadata (e.g., DICOM and OME) and multiple large-scale atlas projects; they are guided by existing standards and accommodate most multiplexed imaging technologies and both centralized and distributed data storage.

For further information on the MITI guidelines, please see the [MITI website](https://www.miti-consortium.org/), [specification on Github](https://github.com/miti-consortium/MITI), and [Nature Methods publication](https://www.nature.com/articles/s41592-022-01415-4).

The HTAN data model for imaging was intended primarily for multiplexed imaging such as CODEX, CyCIF, and IMC, in addition to brightfield imaging of H&E stained tissues.

As with Sequencing data, the imaging data model is split into data levels as follows:

| Level | Description                                                                                                                                        |
| ----- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | Raw imaging data requiring tiling, stitching, illumination correction, registration or other pre-processing.                                       |
| 2     | Imaging data compiled into a single file format, preferably a tiled and pyramidal OME-TIFF. Accompanied by a csv file containing channel metadata. |
| 3     | Segmentation mask, Validated channel metadata, QC checked image.                                                                                   |
| 4     | An object-by-feature table (typically cell-by-marker) generated from the segmentation mask and image.                                              |
