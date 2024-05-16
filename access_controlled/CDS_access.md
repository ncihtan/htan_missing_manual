---
order: 997
---

# Accessing Sequence Data via NCI's Cancer Data Service (CDS)

!!!
**NOTE**: dbGaP approval for HTAN study [phs002371](https://www.ncbi.nlm.nih.gov/projects/gap/cgi-bin/study.cgi?study_id=phs002371.v3.p1) is required in order to access HTAN lower-level genomics data, such as RNAseq FASTQ and BAM files.
!!!

The [CDS Portal](https://dataservice.datacommons.cancer.gov/), within NCI's Cancer Research Data Commons (CRDC), provides an interface to filter and select data from a variety of NCI programs, including controlled-access, primary sequence data from the Human Tumor Atlas Network (HTAN). 

# DRS Manifest Files

To access data via CDS, first generate a CDS Data Repository Service (DRS) manifest containing the files you would like to obtain. DRS manifests are CSV files and require at minimum the **name** and **drs_uri** of each file of interest. For HTAN data, DRS manifests can be generated in one of three ways: 

1. CDS Portal
2. HTAN Data Portal
3. Google BigQuery

## 1. Generating a Manifest File from the CDS Portal

In order to access HTAN imaging data within the [CDS Portal](https://dataservice.datacommons.cancer.gov/), navigate to the portal in a web browser and click on the **Explore CDS Data** button on the landing page.

<p align="center"><img width="364" alt="1" src="https://github.com/ncihtan/htan_missing_manual/assets/123744798/40aff1af-a58f-49dc-9253-6ee5e67ef419">
</p>

&nbsp;

On the Data Explorer page, expand the STUDY section on the left sidebar, scroll down, and check the box next to **Human Tumor Atlas (HTAN) primary sequence data**.

<p align="center"><img width="891" alt="Figure 2" src="https://github.com/ncihtan/htan_missing_manual/assets/123744798/4a3b97f6-97d6-4c99-b782-88c9a8a74fba"></p>

&nbsp;

This action will change the summary panel to reflect selecting HTAN data only.

<p align="center"><img width="891" alt="Figure 3" src="https://github.com/ncihtan/htan_missing_manual/assets/123744798/14e07c72-16d4-463a-b8b2-1ef5f8d72107"></p>

&nbsp;

Scroll down, or click on the **Collapse View** tab on the upper right just below the query summary line in order to see the tabulated view of all of the participants, samples or files in HTAN.

<p align="center"><img width="891" alt="Figure 4" src="https://github.com/ncihtan/htan_missing_manual/assets/123744798/87e90271-a525-4ff7-baeb-4c75ea073a91"></p>

&nbsp;

Click on the **Add All Files** button, or select the check boxes next to all Participants, Samples or Files for a subselection and then click on the **Add Selected** button.  This action will update your cart icon in the upper right corner.

<p align="center"><img width="891" alt="Figure 5" src="https://github.com/ncihtan/htan_missing_manual/assets/123744798/e79dd76d-8eb1-460f-8957-0e07b3898845"></p>

&nbsp;

Clicking on the cart icon, will bring up a list of the selected files.  Click on the **Download Manifest** button in the upper right to download a CSV-formated (Excel compatible) file of this file list.

<p align="center"><img width="891" alt="Figure 6" src="https://github.com/ncihtan/htan_missing_manual/assets/123744798/d3addd28-652d-4320-a109-d0080d1d37df"></p>

&nbsp;


## 2. Generating a Manifest File from the HTAN Data Portal

From the [HTAN Data Portal](https://humantumoratlas.org/), click **CDS/SB-CGC (dbGaP)** under the **Data Access** filter. 

![HTAN Portal: Accessing Genomic Data in CDS](../img/cds_genomics1.png)

Navigate to the **Files** tab, check the box next to **Filename** in upper left, and then click **Download selected files**. 
![HTAN Portal: Selecting Genomic Files](../img/cds_genomics2.png)

Click **Download Manifest**, which will download a local file called `cds_manifest.csv`. 
![HTAN Portal: Download DRS Manifest](../img/cds_genomics3.png)


## 3. Generating a Manifest File from Google BigQuery
HTAN metadata and a mapping of HTAN Data File IDs to CDS DRS URIs are available as Google BigQuery tables via the Institute for Systems Biology Cancer Gateway in the Cloud (ISB-CGC) (see [Google BigQuery](https://docs.humantumoratlas.org/open_access/biq_query/)). These tables can be used to subset data to a cohort of interest, and obtain DRS URIs of files to access. 

For a step-by-step guide on how to generate a DRS manifest file using Google BigQuery, please see the Python notebook [Creating_CDS_Data_Import_Manifests_Using_BQ.ipynb](https://github.com/isb-cgc/Community-Notebooks/blob/master/HTAN/Python%20Notebooks/Creating_CDS_Data_Import_Manifests_Using_BQ.ipynb).



# Accessing Data
Once you have your manifest, follow the instructions on SB-CGC's [Import from a DRS server](https://docs.cancergenomicscloud.org/docs/import-from-a-drs-server#import-from-a-manifest-file) documentation page to import data from a manifest file.