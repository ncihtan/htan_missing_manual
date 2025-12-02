---
order: 994
---

# Submitting Assay Data and Metadata

As stated in [Data Submission Introduction](../data_submission/overview.md), data submission involves two key steps:

1. Uploading assay data files to Synapse; and
2. Completing and validating metadata.

This page provides details regarding those steps. 

!!!
**Synapse is no longer using the Data Curator App (DCA) for metadata submission. Currently this page provides a preview of the new metadata submission process. This page will be updated as the new process if finalized.**
!!!

![HTAN Data Submission Process](../img/Data_submission.svg)

## Data Submission Steps
1. [Complete Pre-submission Tasks](#pre-submission-tasks)
2. [Submit Data Files](#submit-data-files)
4. [Submit metadata](#submit-metadata)

Please read the rest of this page for more information about each of these steps.

### Pre-submission Tasks

- [ ] Have at least one user with Certified User status on Synapse.

> To upload files to the Synapse Platform, you need to be a [Synapse Certified User](https://help.synapse.org/docs/Synapse-User-Account-Types.2007072795.html). You can complete your certification by taking a short certification quiz. Please see the Synapse [Certified User Documentation](https://help.synapse.org/docs/Synapse-User-Account-Types.2007072795.html) for more information.

- [ ] Contact your Data Liaison

> When you are ready to upload data, please contact your [data liaison](../data_submission/Data_Liaisons.md). Please have users obtain certified user status prior to contacting your data liaison.

- [ ] Ensure the dataset conforms to the HTAN Data Model and uses HTAN Identifiers.

> The HTAN Data Model is built upon data standards described on the [Data Standards](https://data.humantumoratlas.org/standards) page. All HTAN Centers are required to encode their clinical, biospecimen and assay data and metadata using the HTAN Data Model. If you have a new data type which is not currently represented in the HTAN Data Model, please contact your data liaison.

> All data should be identified using HTAN identifiers. Please see the [Identifiers](../data_model/identifiers.md) and [Creating HTAN Identifiers](../data_submission/creating_ids.md) sections of this manual for more information regarding HTAN identifiers.

- [ ] Ensure that your data does not contain PHI.

> **Please review your data to ensure that it does not contain PHI.** The HTAN DCC cannot accept data with PHI, including dates less than a year. For example, dates in metadata must be converted to days from an [index date](../data_submission/dates.md) and all image files must have PHI removed from file headers.

### Submit Data Files

Data files can be transferred using the Synapse User Interface (Synapse UI) or programmatically. 

- To upload files using the Synapse User Interface, follow Synapse's [Uploading a File (via Synapse UI)](https://help.synapse.org/docs/Uploading-and-Organizing-Data-Into-Projects,-Files,-and-Folders.2048327716.html#UploadingandOrganizingDataIntoProjects,Files,andFolders-UploadingaFileviatheSynapseUI) directions.
- To upload the files programmatically, please follow Synapse's [Uploading a File Programmatically](https://help.synapse.org/docs/Uploading-and-Organizing-Data-Into-Projects,-Files,-and-Folders.2048327716.html#UploadingandOrganizingDataIntoProjects,Files,andFolders-UploadingaFileProgrammatically) directions.  

!!! If you upload files to Synapse programmatically using the python client, please use synapseclient version 3.0.0 or higher. 
!!!

### Submit Metadata

Sage Bionetworks is currently updating the Metadata submission process. The Data Curator App (DCA) is no longer being used and Metadata submission will occur directly on the Synapse platform.  The following video provide a sneak peak for the process. More information will be posted here once a final version and documentation is available from Sage Bionetworks. 

[Metadata submission preview video](https://drive.google.com/file/d/1HvWrV0OGgbPiMugChOhqaWXLEet8m8B_/view?usp=sharing)

## Useful Links and Guides

### Synapse
- Synapse [Portal](https://www.synapse.org)
- Synapse [DOCS](https://help.synapse.org/docs/Getting-Started.2055471150.html)

### Understanding the HTAN Data Model
- To understand the general structure of the HTAN Data Model and HTAN Identifiers, please see the [HTAN Data Model](../data_model/overview.md) section of this manual.
- To understand the Data Model Manifests/Metadata Attributes, please see the [Data Standards](https://humantumoratlas.org/standards) section of the HTAN Portal. There, you can download manifest summaries. These **cannot be used for metadata submission**, but can help you prepare your metadata. :warning: Currently the data standards page only reflects Phase 1 data standards. Updates are coming soon!