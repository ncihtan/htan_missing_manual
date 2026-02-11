---
order: 992
---

# Phase 2 sc/snRNA-seq Data Submission

+++ Overview
## Overview
In HTAN Phase 2, the following files are submitted for single cell/single nuclei RNA-sequencing (sc/snRNA-seq) data:

| Level | Data Type | Example Files |
|---|-------------------|----------------------|
| 1 | raw sequence data | fastq, unaligned bam |
| 2 | aligned sequence data | bam |
| 3_4 | sample level summary information, e.g. cell annotations, t-SNE/UMAP coordinates, etc. | h5ad |

Metadata requirements are documented in the HTAN Data Model <a href="https://htan2-data-model.readthedocs.io/en/main/" target="_blank" rel="noopener noreferrer">readthedocs</a> pages. This part of the manual describes **file requirements** for level 3_4 h5ad files.

The HTAN h5ad (AnnData 0.10) requirements are modeled after CELLxGENE's requirements.  They also include three attributes developed by the Human Cell Atlas (HCA). Please see the [Background](#background-h5ad-files-cellxgene-human-cell-atlas) section below for more information about h5ad (AnnData 0.10) files, CELLxGENE and the HCA.

+++ Required File Attributes
### Required File Attributes
Similar to CELLxGENE's <a href="https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data" target="_blank" rel="noopener noreferrer">Dataset Requirements</a>, level 3_4 sc/snRNA-seq h5ad files must contain the following attributes. Please see <a href="https://github.com/ncihtan/h5ad/blob/main/exemplars/HTAN_h5ad_exemplar_2025_03_03.h5ad" target="_blank" rel="noopener noreferrer">rHTAN_h5ad_exemplar_2025_03_03.h5ad</a> for an example file which meets these requirements.

| Attribute | Ontology/Version | Comments/Examples |
|-----------|------------------|-------------------|
| var.index, raw.var.index | GENCODE; Please see <a href="https://chanzuckerberg.github.io/single-cell-curation/latest-schema.html#required-gene-annotations" target="_blank" rel="noopener noreferrer">CELLxGENE's latest schema</a> for version information | ENSEMBL IDs.  For example:  ENSG00000107566.|
| var.gene_is_filtered, raw.var.gene_id_filtered | | no genes filtered in raw data; if gene is filtered in normalized data, count is set to 0 and gene_is_filtered set to 1.|
| obs.organism_ontology_term_id | <a href="https://www.ncbi.nlm.nih.gov/taxonomy" target="_blank" rel="noopener noreferrer">NCBITaxon</a> |  Set to NCBITaxon:9606 for human. |
| obs.donor_id | | Set to the HTAN Participant ID, e.g. HTA201_1.| 
| obs.sample_id | | Set to the HTAN Biospecimen ID, e.g. HTA201_1_B. |
| obs.development_stage_ontology_term_id | <a href="https://www.ebi.ac.uk/ols4/ontologies/HsapDv" target="_blank" rel="noopener noreferrer">Human Development Stages (HsapDv)</a> | use <a href="https://docs.google.com/document/d/1SsHZweG_kqerCAPNbQF7gQHNBDRqOsNZWzaWXZIKwTE/edit?usp=sharing" target="_blank" rel="noopener noreferrer">HHCA recommended terms</a> (p.22) |
| obs.sex_ontology_term_id |  <a href="https://www.ebi.ac.uk/ols4/ontologies/pato" target="_blank" rel="noopener noreferrer">Phenotype and Trait Ontology (PATO)</a> | Use <a href="https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data#dataset-requirements" target="_blank" rel="noopener noreferrer">CELLxGENE Requirements</a> PATO:0000384 for male, PATO:0000383 for female, or unknown if unavailable. |
| obs.self_reported_ethnicity_term_id | <a href="https://www.ebi.ac.uk/ols4/ontologies/hancestro" target="_blank" rel="noopener noreferrer">Human Ancestry Ontology (HANCESTRO)</a> | Use <a href="https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data#dataset-requirements" target="_blank" rel="noopener noreferrer">CELLxGENE Requirements</a>. HANCESTRO multiple comma-separated terms may be used if more than one ethnicity is reported. If information is unavailable, use unknown. Example:  HANCESTRO_0568. Note that CELLxGENE specifically excludes certain HANCESTRO categories.  See <a href="https://chanzuckerberg.github.io/single-cell-curation/latest-schema.html#self_reported_ethnicity_ontology_term_id" target="_blank" rel="noopener noreferrer">full details</a>.|
| obs.disease_ontology_term_id | <a href="https://www.ebi.ac.uk/ols4/ontologies/mondo" target="_blank" rel="noopener noreferrer">Mondo Disease Ontology</a> | |
| obs.tissue_type | CELLxGENE | Use <a href="https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data#dataset-requirements" target="_blank" rel="noopener noreferrer">CELLxGENE Requirements</a>, Permitted values are restricted to: tissue, organoid, or cell culture.|
| obs.tissue_ontology_term_id |  <a href="https://www.ebi.ac.uk/ols4/ontologies/uberon" target="_blank" rel="noopener noreferrer">Uber Anatomy Ontology (UBERON)</a> ||
| obs.cell_type_ontology_term_id | <a href="https://www.ebi.ac.uk/ols4/ontologies/cl" target="_blank" rel="noopener noreferrer">Cell Ontology (CL)</a> | |
| obs.assay_ontology_term_id | <a href="https://www.ebi.ac.uk/ols4/ontologies/efo" target="_blank" rel="noopener noreferrer">Experimental Factor Ontology (EFO)</a> | Use <a href="https://chanzuckerberg.github.io/single-cell-curation/latest-schema.html#assay_ontology_term_id" target="_blank" rel="noopener noreferrer">CELLxGENE Requirements</a> |
| obs.suspension_type | CELLxGENE | Use <a href="https://chanzuckerberg.github.io/single-cell-curation/latest-schema.html#suspension_type" target="_blank" rel="noopener noreferrer">CELLxGENE Requirements</a>. Permitted values are restricted to: cell, nucleus, na. |
| obs.is_primary_data | CELLxGENE.  Used to indicate if this is the canonical data set (True), or data is being reused from another source (False). | Use <a href="https://chanzuckerberg.github.io/single-cell-curation/latest-schema.html#is_primary_data" target="_blank" rel="noopener noreferrer">CELLxGENE Requirements</a>.  Permitted values are restricted to True or False. |
| obs.cell_enrichment | Human Cell Atlas:  “Specifies the cell types targeted for enrichment or depletion beyond the selection of live cells.“ | CL term, followed by + or -.  If no enrichment. Then use CL:00000000. For example, enrichment for fibroblasts would be CL:0000057+ |
| obs.intron_inclusion | Human Cell Atlas: “Were introns included during read counting in the alignment process?” | Permitted values are:  yes, no |
| obs.author_cell_type | Human Cell Atlas: “Encoding of author intuition of cellular annotation in the dataset.” | Free text |
| <a href="https://chanzuckerberg.github.io/single-cell-curation/latest-schema.html#x_suffix" target="_blank" rel="noopener noreferrer">obsm.X_(suffix)</a> | CELLxGENE:  embeddings of at least two dimensions, e.g.  tSNE, UMAP, PCA, spatial coordinates | use <a href="https://chanzuckerberg.github.io/single-cell-curation/latest-schema.html#x_suffix" target="_blank" rel="noopener noreferrer">CELLxGENE terms</a> for suffix (e.g. umap, tsne, pca) |

+++ HTAN h5ad File Validation
### HTAN h5ad File Validation
The HTAN Data Coordinating Center (DCC) has released a PyPi package called <a href="https://pypi.org/project/HTAN-h5ad-validate/" target="_blank" rel="noopener noreferrer">HTAN-h5ad-validator</a> with which Centers can validate their sc/snRNA-seq h5ad files. Sage Bionetworks will run the validator on sc/snRNA-seq h5ad files submitted to Synapse. 

+++ Background: h5ad files, CELLxGENE, Human Cell Atlas
## Background: h5ad files, CELLxGENE, Human Cell Atlas

### h5ad (AnnData 0.10) brief overview
Please see <a href="https://anndata.readthedocs.io/en/latest/index.html" target="_blank" rel="noopener noreferrer">AnnData’s documentation</a> for a more detailed description of the AnnData object. 

![From https://raw.githubusercontent.com/scverse/anndata/main/docs/_static/img/anndata_schema.svg](../img/anndata_schema.svg)

For HTAN’s purposes, the following parts of the AnnData object are of interest:

* .X - a matrix with counts where rows are cells and columns are genes.
* var - a matrix with gene information (e.g. gene name, gene_is_filtered).
* obs - a matrix with cell-level information.
* obsm - one or more numpy ndarrays with cell embeddings.

CELLxGENE requires that raw data are submitted.  Normalized data may also be submitted.

### CELLxGENE
The HTAN DCC submits sc/snRNA-seq data to <a href="https://cellxgene.cziscience.com" target="_blank" rel="noopener noreferrer">CELLxGENE</a>, a tool developed by the Chan Zuckerberg Initiative (CZI) to visualize and explore single cell and spatial data. The DCC submits data to CellxGene in h5ad (AnnData 0.10) format. CELLxGENE’s schema requires:

* use of Ensembl gene IDs.
* a specific genome reference and annotation version.
* specific h5ad (AnnData 0.10) attributes.
* use of specific ontologies for many of the required attributes (i.e. cell ontology). 

The HTAN requirements for h5ad files are modeled after CELLxGENE's <a href="https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data" target="_blank" rel="noopener noreferrer">Dataset Requirements</a>.

### Human Cell Atlas (HCA)

The Human Cell Atlas (HCA) is a large repository of single cell data from healthy subjects.  It provides  <a href="https://docs.google.com/document/d/1SsHZweG_kqerCAPNbQF7gQHNBDRqOsNZWzaWXZIKwTE/edit?usp=sharin" target="_blank" rel="noopener noreferrer">standards for single-cell data submission</a> which adopt most of the CELLxGENE schema, but also include additional fields.  Aligning HTAN data with CELLxGENE will potentially facilitate data integration with other consortia such as the HCA.  The HTAN requirements include three HCA attributes in addition to CELLxGENE required attributes.
+++

