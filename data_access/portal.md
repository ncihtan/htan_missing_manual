---
order: 998
---

# Using the HTAN Data Portal

The **HTAN Data Portal provides an interactive interface with which to explore HTAN data**. It provides mechanisms to:
- [download metadata](#downloading-metadata);
- [explore available data](#exploring-available-data); and
- [download assay data](#downloading-assay-data). 

To get started, go to: https://data.humantumoratlas.org/explore.

To orient you to the HTAN Data Portal, consider the example of accessing precancerous polyp data from Vanderbilt University, as described in their recent [Cell publication](https://pubmed.ncbi.nlm.nih.gov/34910928/).

By default, HTAN data is organized by research center:

![HTAN Portal: Home Page](../img/portal1.png)

If you scroll down on the page, you will see Vanderbilt University:

![HTAN Portal: Vanderbilt Atlas](../img/portal2.png)

As of this writing, you can see that the Vanderbilt Colon Atlas project has 90 cases and 193 biospecimens.

## Downloading Metadata

Once you have identified the project of interest, you can click the download metadata button:

![HTAN Portal: Download Metadata](../img/portal3.png)

You will then be prompted with a dialog box of all metadata associated with the specified project. For example:

![HTAN Portal: Metadata Table](../img/portal4.png)

Behind the scenes, HTAN leverages the [Synapse Platform](https://www.synapse.org/) created and maintained by [Sage Bionetworks](https://sagebionetworks.org/). Each piece of HTAN data is automatically assigned a unique Synapse identifier, such as syn25010909. In the screenshot above, you can see that the Vanderbilt project has multiple metadata files, each associated with a unique Synapse identifier.

If you click on any of the Synapse links above, you can immediately download a comma separated value (CSV) file associated with the metadata category. There is no need to create a Synapse account or log into Synapse. For example, here we have download the Vanderbilt biospecimen file and loaded it into Excel:

![HTAN Tabular Data within Excel](../img/portal5.png)

Once you have downloaded metadata files, you can parse them in your favorite programming language, such as R or Python. To understand the individual columns within each metadata file, please refer to the HTAN Data Model [Specific Standards page](../data_model/standards.md).

## Exploring Available Data

The HTAN Data Portal provides a unified interface for filtering and exploring HTAN data sets. Each filter is available at the top of the page:

![HTAN Portal:  Filters](../img/portal6.png)

To get started, you can click the Atlas pull-down menu, and select the Vanderbilt HTAN center:

![HTAN Portal:  Filter by HTAN Center](../img/portal7.png)

Your selection will now be reflected in the user interface:

![HTAN Portal:  Filter by Vanderbilt University](../img/portal8.png)

If you click the **Cases** or **Biospecimens** tabs, you can browse available metadata. Clicking the **Files** tab will take you to an interactive table listing all files available for download.

![HTAN Portal:  Files Tab](../img/portal9.png)

At this point, the Files tab is likely to contain hundreds of files, and may be difficult to navigate. You can further refine the files table by clicking on the **Assay Type** or **File Type** filters. This will trigger pop-up windows that describe the assay and file type categories available within the Vanderbilt project. For example, if you click Assay Type you will see:

![HTAN Portal:  Filter by Assay Type](../img/portal10.png)

Data that is available within the Vanderbilt project is set to **bold**. You can therefore see that the Vanderbilt project has Bulk DNA, H&E Images, Multiplex ImmunoFluorescence images and Single Cell RNA Seq Data.

If you click scRNA-seq, the file table will automatically update. You can then select the **File Type** filter to drill-down even further:

![HTAN Portal:  Filter by File Type](../img/portal11.png)

Clicking Level 4 here will now filter the File table to only include Level 4 sequencing data that consists of Single Cell RNA Seq h5ad formatted files:

![HTAN Portal:  Multiple Filters Enabled](../img/portal12.png)

Note that you can remove any existing filters by clicking on any of the “chips” in the page header. For example, if you want to remove the Level 4 filter, just click the Level 4 chip:

![HTAN Portal:  Removing Filters](../img/portal13.png)

Clicking **View Details** on any of these files will pop open a metadata table. For example:

![HTAN Portal:  Metadata Details](../img/portal14.png)

## Downloading Assay Data

!!!
Cancer Data Services (CDS) has changed its name to General Commons (GC). The HTAN Portal will be updated soon to reflect this change.
!!!

Once you have specified your filter criteria, the Files tab will display all matching files. At this point, you may see two types of files:

-   Open Access Files (Data Access = Synapse or CDS/SB-CGC (open access)); or
-   Access-Controlled Files (Data Access = dbGAP)

![HTAN Data Access Types](../img/HTAN_Portal_DataAccess.svg)

!!! Access Requirements
**Synapse** To download open access files, you will need to first create a free account on the Synapse data platform. To register an account, go to https://www.synapse.org/, and click the Register button.

**SB-CGC** Data access via Seven Bridges Cancer Genomics Cloud (SB-CGC) requires a CGC account [[register here](https://docs.cancergenomicscloud.org/docs/sign-up-for-the-cgc)].

**dbGAP** To download access-controlled files, you must first complete a [dbGAP request](db_gap.md).
!!!

To download files, select the files you would like, then click on the "Download selected files" button.

![Select Files and Download](../img/HTAN_Portal_Selected_Files.png)

The pop-up window that appears provides the information you need to access the files, including directions for:
1. accessing [Cancer Research Data Commons (CRDC) data on SB-CGC](cds_cgc.md);
2. directly downloading CRDC data using the [Gen3 Client](cds_gen3.md); and
3. accessing data available on Synapse via either the Synapse web interface or the Synapse CLI. 

![Download pop-up window](../img/HTAN_Portal_Download.png)

In addition to the modes of data access described in the Download pop-up window, open access data can be:
- transferred from [Synapse to SB-CGC](synapse_to_cds.md) for cloud processing and analysis; or
- downloaded from [CELLxGENE](../data_visualization/cell_by_gene.md) (single cell/single nuclei RNA-seq data in h5ad (AnnData) format).