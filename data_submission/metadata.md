---
order: 996
---

# Metadata Requirements

Metadata Requirements are explicitly outlined in the <a href="https://htan2-data-model.readthedocs.io/en/main/" target="_blank" rel="noopener noreferrer">HTAN Phase 2 Data Model (Metadata) Documentation</a>. This documentation is directly linked to the underlying github repository code and will be updated as additional assays are added to the Phase 2 Data Model. <a href="https://htan2-data-model.readthedocs.io/en/main/" target="_blank" rel="noopener noreferrer">HTAN Phase 2 Data Model (Metadata) Documentation</a> includes attribute descriptions, requirements and valid values. Metadata is submitted to HTAN via Synapse which is developed and maintained by <a href="https://sagebionetworks.org/" target="_blank" rel="noopener noreferrer">Sage Bionetworks</a>.  

General requirements include the following:
- All assay data must be linked to their respective HTAN participants and biospecimens. If an assay file cannot be linked to validated participant demographic and biospecimen records, it will trigger an error when the HTAN DCC prepares data for data release.
- A participant must only have one demographics record. Duplicate HTAN Participant ID records will trigger an error. Other clinical metadata also have restrictions in the number of records per participant. Please see [Phase 2 Clinical Data Submission](clin_data_submission.md) for more information.

!!! Terminology Alert
In the Synapse system, metadata can be **File-based** (associated with a data file) or **Record-based**. Please see <a href="https://docs.synapse.org/synapse-docs/managing-metadata-with-curator#About" target="_blank" rel="noopener noreferrer">Synapse's Documentation</a> for more information about these terms.

For HTAN: \
**Record-based** metadata includes the Clinical and Biospecimen modules of the HTAN2 Data Model. \
**File-based** metadata includes all other modules in the HTAN2 Data Model.
!!!