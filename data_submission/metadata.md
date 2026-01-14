---
order: 996
---

# What is Metadata?

Metadata means data *about* data.  Metadata enables both data searchability and interpretability. For HTAN, this includes sample and case identifiers, patient information (e.g. demographics), biospecimen information (e.g. tumor type), and assay-specific information (e.g. experiment protocol, assay reagents or assay technology). 

![Example HTAN Metadata vs Assay Data](../img/metadata.svg)

HTAN's [Data Model](../data_model/overview.md) is a framework for collecting and storing metadata.  The Data Model in turn supports effective searching for data on [HTAN's Data Portal](https://humantumoratlas.org/explore).

Metadata is submitted to HTAN via Synapse which is developed and maintained by [Sage Bionetworks](https://sagebionetworks.org/).  

!!! Terminology Alert
In the Synapse system, metadata can be **File-based** (associated with a data file) or **Record-based**. Please see [Synapse's Documentation](https://docs.synapse.org/synapse-docs/managing-metadata-with-curator#About) for more information about these terms.

For HTAN: \
**Record-based** metadata includes the Clinical and Biospecimen modules of the HTAN2 Data Model. \
**File-based** metadata includes all other modules in the HTAN2 Data Model.
!!!