---
order: 994
---

# Submitting Assay Data and Metadata

As stated in [Data Submission Introduction](../data_submission/overview.md), data submission involves two key steps:

1. Uploading assay data files to Synapse; and
2. Completing and validating metadata using the Data Curator App (DCA).

This page provides details regarding those steps. 

!!!
**Please note that the manual currently reflects the data submission process used in HTAN Phase 1. Changes will be implemented for HTAN Phase 2, including replacement of the DCA with a new tool.**
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

Organize your data using the **flattened data layout** described in Synapse's [Data Ingress Docs](https://dca-docs.scrollhelp.site/DCA/Working-version/HTAN/organize-your-data-upload#OrganizeyourDataUpload-FlattenedDataLayoutExample)

Data files can be transferred using the Synapse User Interface (Synapse UI) or programmatically. 

- To upload files using the Synapse User Interface, follow Synapse's [Quick Overview: Uploading a File (via Synapse UI)](https://dca-docs.scrollhelp.site/DCA/Working-version/HTAN/uploading-data#UploadData-QuickOverview:UploadingaFile(viatheSynapseUI)) directions.
- To upload the files programmatically, please follow Synapse's directions to [Upload Data Using the Command Line](https://dca-docs.scrollhelp.site/DCA/Working-version/HTAN/uploading-data#UploadData-UploadDataUsingtheCommandLine).  This involves using Synapse Client. 

!!! If you upload files to Synapse programmatically, please use synapseclient version 3.0.0 or higher. 
!!!

## Submit Metadata

!!!
1. Only the DCA should be used to obtain manifests (metadata templates). 
2. Always upload data files to Synapse first before submitting assay metadata.
!!!

The DCA contains HTAN-specific manifests (metadata templates) which can be 

1. completed on the app, or 
2. downloaded, completed and uploaded back to the DCA.  

Manifests for assay data will be pre-populated with assay file entityIDs once they are associated with a particular Synapse dataset folder. 

Once the manifests are completed by your center, they should then be validated and submitted via the DCA. The DCA will perform validation checks for a subset of common errors. If any of these errors are found, you can edit the metadata, revalidate and submit. 

!!!  Please note: If you have added assay files to a Synapse folder where there is a pre-existing manifest or you are adding records to a pre-existing clinical data or biospecimen manifest, **please update the existing manifest on the DCA app or download the existing manifest from the DCA** to make updates. **Do not use a local copy of the manifest at your center to make updates**. Local copies may be out of sync with the data in Synapse. 
!!!

Please see Synapse's [Data Ingress Docs](https://dca-docs.scrollhelp.site/DCA/Working-version/HTAN/validate-and-submit-your-metadata) for more details regarding the web app.

## Useful Links and Guides

### Synapse and the DCA
- Synapse [Portal](https://www.synapse.org)
- [DCA](https://dca.app.sagebionetworks.org/), developed and maintained by [Sage Bionetworks](https://sagebionetworks.org/)

### Understanding the HTAN Data Model
- To understand the general structure of the HTAN Data Model and HTAN Identifiers, please see the [HTAN Data Model](../data_model/overview.md) section of this manual.
- To understand the Data Model Manifests/Metadata Attributes, please see the [Data Standards](https://humantumoratlas.org/standards) section of the HTAN Portal. There, you can download manifest summaries. These **cannot be used for metadata submission**, but can help you prepare your metadata.