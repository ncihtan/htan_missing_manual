---
order: 999
---

# Metadata Standards

Metadata means data *about* data.  Metadata enables both data searchability and interpretability. For HTAN, this includes sample and case identifiers, patient information (e.g. demographics), biospecimen information (e.g. tumor type), and assay-specific information (e.g. experiment protocol, assay reagents or assay technology). 

Metadata can be further divided into broad categories:
1. clinical metadata;
2. biospecimen metadata; and
3. assay metadata.

[!button text="HTAN Phase 2 Data Model Documentation"](https://htan2-data-model.readthedocs.io/en/main/)

[!button text="HTAN Phase 2 Data Model Github Repository"](https://github.com/ncihtan/htan2-data-model)
+++ HTAN Phase 1 Data Model 
[!button text="HTAN Phase 1 Data Model Github Repository"](https://github.com/ncihtan/data-models)

Where possible, the HTAN Phase 1 Data Model leveraged previously defined data standards across the scientific research community, including the [NCI Genomic Data Commons](https://gdc.cancer.gov/), the [Human Cell Atlas](https://www.humancellatlas.org/), the [Human Biomolecular Atlas Program (HuBMAP)](https://hubmapconsortium.org/) and the [Minimum Information about Tissue Imaging (MITI)](https://www.miti-consortium.org/) reporting guidelines.


+++ Clinical Metadata 
## Tiers
Clinical metadata is organized into tiers. The structure of these tiers differs in Phase 1 and Phase 2 of HTAN. In Phase 1 there were three clinical data tiers.  In Phase 2, there are two. For both phases, Tier 1 represents clinical data which is generally common to all studies and Atlases. Higher tiers are extensions to Tier 1, some of which are cancer or study-specific.  

## Phase 2 Clinical Metadata Tiers
In HTAN Phase 2, there are only two clinical metadata tiers. 
- Tier 1 metadata is divided into multiple categories, including Demographics, Diagosis, Family History, Exposure, Molecular Test, Therapy, Follow Up and Vital Status. 
- Tier 2 contains any cancer or study-specific clinical information which is not represented in Tier 1. Tier 2 is a flexible comma-separated value (csv) file. The only required attribute is HTAN Participant ID. All other attributes (columns headers) are determined by the submitting Center. 

Figure 2 provides a general representation of the model. 

![Figure 2. HTAN Phase 2 Clinical Metadata Tiers](../img/Phase2_clinical_data_tiers.svg)

## Phase 1 Clinical Metadata Tiers
In HTAN Phase 1, Tier 1 clinical metadata was based on the NCI's Genomic Data Commons (GDC) clinical data model.  Phase 1 clinical data was divided into three tiers:
- Similar to HTAN Phase 2, Tier 1 metadata was divided into multiple categories, including Demographics, Diagosis, Family History, Exposure, Molecular Test, Therapy, Follow Up and Vital Status Update. However, the attributes, valid values and requirements differ between Phase 1 and Phase 2 for each of these Tier 1 clinical metadata categories.  
- Phase 1 Tiers 2 and 3 are disease-agnostic (Tier 2) and disease-specific (Tier 3) extensions to the GDC model.

These tiers are shown in figure 3 and are described more on the [Phase 1 Clinical Data Page](https://humantumoratlas.org/standard/clinical). 

![Figure 3. HTAN Phase 1 Clinical Metadata Tiers](../img/Phase1_clinical_data_tiers.svg)

+++ Biospecimen Metadata

+++ Assay File Metadata
+++
