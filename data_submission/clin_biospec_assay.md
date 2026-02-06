---
order: 994
---

# Submitting Assay Data and Metadata

[Data Submission Introduction](../data_submission/overview.md) provides a general overview for submitting data and metadata to HTAN. This page provides details regarding those steps.

## Data Submission Steps
1. [Complete Pre-submission Tasks](#pre-submission-tasks)
2. [Submit Data Files](#submit-data-files)
4. [Submit Metadata](#submit-metadata)

Please read the rest of this page for more information about each of these steps.
![HTAN Data Submission Process](../img/Data_submission.svg){ style="width: 60%;" }

### Pre-submission Tasks

- [ ] Have at least one user with Certified User status on Synapse.

> To upload files to the Synapse Platform, you need to be a [Synapse Certified User](https://docs.synapse.org/synapse-docs/synapse-user-account-types). You can complete your certification by taking a short certification quiz. Please see the Synapse [Certified User Documentation](https://docs.synapse.org/synapse-docs/synapse-user-account-types) for more information. Please also be aware that use of Synapse requires agreement to the latest Synapse Terms of Service. Synapse users must also enable two-factor authentication (2FA). You can find information about the latest TOS and guidance on enabling 2FA on your account [here](https://sagebionetworks.org/trust-center).

- [ ] Contact your Data Liaison

> When you are ready to upload data, please contact your [data liaison](../data_submission/Data_Liaisons.md). Please have users obtain certified user status prior to contacting your data liaison. If you have not submitted data previously, your Data Liaison may also need to ensure you have the proper access rights for you Synapse Project.

- [ ] Ensure the dataset conforms to the HTAN Data Model and uses HTAN Identifiers.

> The HTAN Data Model is built upon data standards described on the [Data Model](../data_model/overview.md) page. All HTAN Centers are required to encode their clinical, biospecimen and assay data and metadata using the HTAN Data Model. If you have a new data type which is not currently represented in the HTAN Data Model, please contact your data liaison.

> All data should be identified using HTAN identifiers. Please see the [Identifiers](../data_model/identifiers.md) and [Creating HTAN Identifiers](../data_submission/creating_ids.md) sections of this manual for more information regarding HTAN identifiers.

- [ ] Ensure that your data does not contain PHI.

> **Please review your data to ensure that it does not contain PHI.** The HTAN DCC cannot accept data with PHI, including dates less than a year. For example, dates in metadata must be converted to days from an [index date](../data_submission/dates.md) and all image files must have PHI removed from file headers.

### Submit Data Files

Data files can be transferred using the Synapse User Interface (Synapse UI) or programmatically. 

- To upload files using the Synapse User Interface, follow Synapse's [Uploading a File (via Synapse UI)](https://docs.synapse.org/synapse-docs/uploading-and-organizing-data-into-projects-files-and-folders#Uploading-a-File-via-the-Synapse-UI) directions.
- To upload the files programmatically, please follow Synapse's [Uploading a File Programmatically](https://docs.synapse.org/synapse-docs/uploading-and-organizing-data-into-projects-files-and-folders#Uploading-a-File-Programmatically) directions. Contributors are encouraged to use the Python client for programmatic uploads.  

For large file uploads, Synapse also provides guidance regarding uploading data in bulk in [this tutorial](https://python-docs.synapse.org/en/stable/tutorials/python/upload_data_in_bulk/).  

!!! If you upload files to Synapse programmatically using the python client, please use synapseclient version 3.0.0 or higher. 
!!!

### Submit Metadata

Synapse provides a curator within its platform for creating and managing metadata. Please see [their documenation](https://docs.synapse.org/synapse-docs/managing-metadata-with-curator) for information about using the curator.

In the Synapse system, metadata can be **File-based** (associated with a data file) or **Record-based**. Please see [Synapse's Documentation](https://docs.synapse.org/synapse-docs/managing-metadata-with-curator#About) for more information about these terms.

For HTAN: \
**Record-based** metadata includes the Clinical and Biospecimen modules of the HTAN2 Data Model. \
**File-based** metadata includes all other modules in the HTAN2 Data Model.

## Useful Links and Guides

### Synapse
- Synapse [Portal](https://www.synapse.org)
- Synapse [DOCS](https://docs.synapse.org/synapse-docs)

### Understanding the HTAN Data Model
- To understand the general structure of the HTAN Data Model and HTAN Identifiers, please see the [HTAN Data Model](../data_model/overview.md) section of this manual.