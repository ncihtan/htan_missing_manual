---
order: 992
---

# Phase 2 sc/snRNA-seq Data Submission

## Overview
In HTAN Phase 2, the following files are submitted for single cell/single nuclei RNA-sequencing (sc/snRNA-seq) data:

| Level | Data Type | Example Files |
|---|-------------------|----------------------|
| 1 | raw sequence data | fastq, unaligned bam |
| 2 | aligned sequence data | bam |
| 3_4 | sample level summary information, e.g. cell annotations, t-SNE/UMAP coordinates, etc. | h5ad |

Metadata requirements are documented in the HTAN Data Model [readthedocs](https://htan2-data-model.readthedocs.io/en/latest/docs/scrna-seq.html) pages. This part of the manual describes **file requirements** for level 3_4 h5ad files.

## HTAN's h5ad Requirements
HTAN Centers are encouraged to reference the [sc/snRNA-seq RFC](https://docs.google.com/document/d/1XjDLWulYWhnfZrGCg-0_Jh93ytIp3p_01ZrTyymTjoU/edit?usp=sharing) for additional details. The HTAN h5ad (AnnData 0.10) requirements are modeled after CELLxGENE's requirements.  They also include three attributes developed by the Human Cell Atlas (HCA). Please see the [Background](#background-h5ad-files-cellxgene-human-cell-atlas) section below for more information about h5ad (AnnData 0.10) files, CELLxGENE and the HCA.

### Required File Attributes
Similar to CELLxGENE's [Dataset Requirements](https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data), level 3_4 sc/snRNA-seq h5ad files must contain the following attributes. Please see [HTAN_h5ad_exemplar_2025_03_03.h5ad](https://github.com/ncihtan/h5ad/blob/main/exemplars/HTAN_h5ad_exemplar_2025_03_03.h5ad) for an example file which meets these requirements.

| Attribute | Ontology/Version | Comments/Examples |
|-----------|------------------|-------------------|
| var.index, raw.var.index | [Human reference GRCh38.p14 (GENCODE v44/Ensembl 110)](https://github.com/chanzuckerberg/single-cell-curation/blob/main/schema/5.2.0/schema.md#required-gene-annotations) | ENSEMBL IDs.  For example:  ENSG00000107566.|
| var.gene_is_filtered, raw.var.gene_id_filtered | | no genes filtered in raw data; if gene is filtered in normalized data, count is set to 0 and gene_is_filtered set to 1.|
| obs.organism_ontology_term_id | [NCBITaxon](https://www.ncbi.nlm.nih.gov/taxonomy) |  Set to NCBITaxon:9606 for human. |
| obs.donor_id | | Set to the HTAN Participant ID, e.g. HTA201_1.| 
| obs.sample_id | | Set to the HTAN Biospecimen ID, e.g. HTA201_1_B. |
| obs.development_stage_ontology_term_id | [Human Development Stages (HsapDv)](https://www.ebi.ac.uk/ols4/ontologies/HsapDv) | use [HCA recommended terms](https://docs.google.com/document/d/1SsHZweG_kqerCAPNbQF7gQHNBDRqOsNZWzaWXZIKwTE/edit?usp=sharing) (p.22) |
| obs.sex_ontology_term_id | [Phenotype and Trait Ontology (PATO)](https://www.ebi.ac.uk/ols4/ontologies/pato) | Use [CELLxGENE Requirements](https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data#dataset-requirements) PATO:0000384 for male, PATO:0000383 for female, or unknown if unavailable. |
| obs.self_reported_ethnicity_term_id | [Human Ancestry Ontology (HANCESTRO)](https://www.ebi.ac.uk/ols4/ontologies/hancestro) | Use [CELLxGENE Requirements](https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data#dataset-requirements). HANCESTRO multiple comma-separated terms may be used if more than one ethnicity is reported. If information is unavailable, use unknown. Example:  HANCESTRO_0568. Note that CELLxGENE specifically excludes certain HANCESTRO categories.  See [full details](https://github.com/chanzuckerberg/single-cell-curation/blob/main/schema/5.2.0/schema.md#self_reported_ethnicity_ontology_term_id).|
| obs.disease_ontology_term_id | [Mondo Disease Ontology](https://www.ebi.ac.uk/ols4/ontologies/mondo) | |
| obs.tissue_type | CELLxGENE | Use [CELLxGENE Requirements](https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data#dataset-requirements), Permitted values are restricted to: tissue, organoid, or cell culture.|
| obs.tissue_ontology_term_id | [Uber Anatomy Ontology (UBERON)](https://www.ebi.ac.uk/ols4/ontologies/uberon) ||
| obs.cell_type_ontology_term_id | [Cell Ontology (CL)](https://www.ebi.ac.uk/ols4/ontologies/cl) | |
| obs.assay_ontology_term_id | [Experimental Factor Ontology (EFO)](https://www.ebi.ac.uk/ols4/ontologies/efo) | Use [CELLxGENE Requirements](https://github.com/chanzuckerberg/single-cell-curation/blob/main/schema/5.2.0/schema.md#assay_ontology_term_id) |
| obs.suspension_type | CELLxGENE | Use [CELLxGENE Requirements](https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data#dataset-requirements). Permitted values are restricted to: cell, nucleus, na. |
| obs.is_primary_data | CELLxGENE.  Used to indicate if this is the canonical data set (True), or data is being reused from another source (False). | Use [CELLxGENE Requirements](https://github.com/chanzuckerberg/single-cell-curation/blob/main/schema/5.2.0/schema.md#is_primary_data).  Permitted values are restricted to True or False. |
| obs.cell_enrichment | Human Cell Atlas:  “Specifies the cell types targeted for enrichment or depletion beyond the selection of live cells.“ | CL term, followed by + or -.  If no enrichment. Then use CL:00000000. For example, enrichment for fibroblasts would be CL:0000057+ |
| obs.intron_inclusion | Human Cell Atlas: “Were introns included during read counting in the alignment process?” | Permitted values are:  yes, no |
| obs.author_cell_type | Human Cell Atlas: “Encoding of author intuition of cellular annotation in the dataset.” | Free text |
| [obsm.X_(suffix)](https://github.com/chanzuckerberg/single-cell-curation/blob/main/schema/5.2.0/schema.md#x_suffix) | CELLxGENE:  embeddings of at least two dimensions, e.g.  tSNE, UMAP, PCA, spatial coordinates | use [CELLxGENE terms](https://github.com/chanzuckerberg/single-cell-curation/blob/main/schema/5.2.0/schema.md#x_suffix) for suffix (e.g. umap, tsne, pca) |

### HTAN h5ad File Validation
The HTAN Data Coordinating Center (DCC) has released a PyPi package called [HTAN-h5ad-validator](https://pypi.org/project/HTAN-h5ad-validate/) with which Centers can validate their sc/snRNA-seq h5ad files. Sage Bionetworks will run the validator on sc/snRNA-seq h5ad files submitted to Synapse. 

## Background: h5ad files, CELLxGENE, Human Cell Atlas

### h5ad (AnnData 0.10) brief overview
Please see [AnnData’s documentation](https://anndata.readthedocs.io/en/latest/index.html) for a more detailed description of the AnnData object. 

![From https://raw.githubusercontent.com/scverse/anndata/main/docs/_static/img/anndata_schema.svg](../img/anndata_schema.svg)

For HTAN’s purposes, the following parts of the AnnData object are of interest:

* .X - a matrix with counts where rows are cells and columns are genes.
* var - a matrix with gene information (e.g. gene name, gene_is_filtered).
* obs - a matrix with cell-level information.
* obsm - one or more numpy ndarrays with cell embeddings.

CELLxGENE requires that raw data are submitted.  Normalized data may also be submitted.

### CELLxGENE
The HTAN DCC submits sc/snRNA-seq data to [CELLxGENE](https://cellxgene.cziscience.com), a tool developed by the Chan Zuckerberg Initiative (CZI) to visualize and explore single cell and spatial data. The DCC submits data to CellxGene in h5ad (AnnData 0.10) format. CELLxGENE’s schema requires:

* use of Ensembl gene IDs.
* a specific genome reference and annotation version.
* specific h5ad (AnnData 0.10) attributes.
* use of specific ontologies for many of the required attributes (i.e. cell ontology). 

The HTAN requirements for h5ad files are modeled after CELLxGENE's [Dataset Requirements](https://cellxgene.cziscience.com/docs/032__Contribute%20and%20Publish%20Data).

### Human Cell Atlas (HCA)

The Human Cell Atlas (HCA) is a large repository of single cell data from healthy subjects.  It provides [standards for single-cell data submission](https://docs.google.com/document/d/1SsHZweG_kqerCAPNbQF7gQHNBDRqOsNZWzaWXZIKwTE/edit?usp=sharing) which adopt most of the CELLxGENE schema, but also include additional fields.  Aligning HTAN data with CELLxGENE will potentially facilitate data integration with other consortia such as the HCA.  The HTAN requirements include three HCA attributes in addition to CELLxGENE required attributes.


