---
order: 993
---

# Phase 2 Clinical Data Submission

## Overview
In HTAN Phase 2, there are two clinical metadata tiers. 
- Tier 1 metadata is divided into multiple categories, including Demographics, Diagosis, Family History, Exposure, Molecular Test, Therapy, Follow Up and Vital Status. 
- Tier 2 contains any cancer or study-specific clinical information which is not represented in Tier 1. Tier 2 is a flexible comma-separated value (csv) file. The only required attribute is HTAN Participant ID. All other attributes (columns headers) are determined by the submitting Center. 

Figure 2 provides a general representation of the model. 

![Figure 2. HTAN Phase 2 Clinical Metadata Tiers](../img/Phase2_clinical_data_tiers.svg)

This page provides additional details regarding submission of Phase 2 Clinical Data. 

!!! Terminology:
This document uses the following terms from IEFT RFC 2119

MUST / REQUIRED / SHALL:  ✅ (denotes absolute requirement)

MUST NOT / SHALL NOT: ❌ (denotes absolute prohibition)

SHOULD / RECOMMENDED: 🌟 (denotes recommendation)

SHOULD NOT / NOT RECOMMENDED: 🙅‍♂️ (denotes not recommended)

MAY / OPTIONAL: 🤷‍♀️ (denotes optional) 
!!!

All HTAN data elements that capture time points are expressed as “days to” to obfuscate dates while allowing for longitudinal timelines and relative data analysis.  The index date for all HTAN dates is the participant date of birth.  For example, if a patient has therapy starting at X=365 days, that means the therapy started 365 days after birth. 

The data standards allow for multiple responses for many data elements.  This information may be found in the “Validation” column of the HTAN Data Model documentation. Multiple responses are submitted delimited by commas.

Data elements are aligned with [NCI's caDSR](https://cadsr.cancer.gov/onedata/Home.jsp) where possible.

## Clinical Tier 1: Demographics
Clinical Tier 1 Demographics data includes patient attributes captured at baseline or at the time of the cross-sectional observation. These data include ethnicity, race, etc. </br>
✅	A **single Demographics record** is REQUIRED for **each HTAN participant**. </br>
❌	A single HTAN participant MUST NOT have multiple demographics records. </br> 

## Clinical Tier 1: Diagnosis
Clinical Tier 1 Diagnosis data elements describe the HTAN participant’s incident tumor or premalignant lesion (PML). These data include primary diagnosis, anatomic site of the tumor or PML, and classification and grade of the lesion.</br>
✅	A **single Diagnosis record** is REQUIRED **for each PML or tumor**.</br>
✅	All dates MUST be converted to days from index, where the index is the participant date of birth. (e.g. ‘Age in Days at Diagnosis’, ‘Age in Days at Last Known Disease Status’) </br>
✅	Data elements MUST use the permissible values established by the CRDC, including NCI Thesaurus ID for Primary Diagnosis and UBERON Codes for Tissue or Organ of Origin.  Please see the [HTAN Phase 2 Clinical Data RFC](https://docs.google.com/document/d/14gNmYTEmd5OjLUuut-w4ZTiF5qgxgpekImG3INM9vm8/edit?usp=sharing) for more information and links to the relevant caDSR codes.
🌟	If a participant develops a new lesion or has/had a secondary cancer, a new Diagnosis record (row) SHOULD be added to the Diagnosis manifest. In all other cases, each participant SHOULD have only one Diagnosis record. </br>

## Clinical Tier 1: Exposure
Clinical Tier 1 Exposure data elements describe the HTAN participant’s exposure to tobacco products, alcohol and other environmental exposure. These data include alcohol exposure, smoking history, years smoked, pack years smoked, and environmental exposure type.</br>
🌟	An Exposure record SHOULD be submitted to document the HTAN participant’s smoke or other exposure at baseline or at the time of observation in a cross-sectional study.</br>
🌟	A **single Exposure record** (row) SHOULD be submitted for **each participant**.</br>
🌟	Clinical Tier 2 SHOULD be used to submit additional exposure data consistent with a publication or other documentation, if needed.</br>

## Clinical Tier 1: Family History
Clinical Tier 1 Family History data elements capture the incidence of cancer in an HTAN participant’s family. These data include the family member’s primary diagnosis and age at diagnosis.</br>
🌟	A **single Family History record** (row) SHOULD be submitted for **each participant**.</br>
🌟  All family members affected are provided in a comma-separated list in the participant.</br>
🌟	Clinical Tier 2 SHOULD be used to submit more extensive family history data, if needed.</br>

## Clinical Tier 1: Followup
Clinical Tier 1 Followup data elements capture a participant's status over time, including recurrence and progression (or their absence).</br>
🌟	A **single Followup record** (row) SHOULD be submitted for **each follow-up time point.**</br>
✅  All dates MUST be converted to days from index, where the index is the participant date of birth. (e.g. 'Age in Days at Followup', 'Age in Days at Progression or Recurrence')</br>

## Clinical Tier 1: Molecular Test
Clinical Tier 1 Molecular Test data elements capture descriptions molecular tests completed clinically, in the diagnostic array, for an HTAN participant. It is intended to capture molecular data not represented in assay files, but important to a Center's study. Data elements include gene symbol, molecular analysis method, and copy number.</br>
🌟	A **single Molecular Test record** (row) SHOULD be submitted **for each molecular test being reported** for the HTAN participant.</br>
✅	All dates MUST be converted to days from index, where the index is the participant date of birth. (e.g. 'Age in Days to Molecular Test Start','Age in Days to Molecular Test Stop')</br>
🌟	For longitudinal follow-up, new molecular test annotations SHOULD be added as new records in the Molecular Test manifest.</br>

## Clinical Tier 1: Therapy
Clinical Tier 1 Therapy data elements capture descriptions of each cancer treatment administered for the HTAN participant. These data include the treatment type, treatment outcome, and the anatomic site of the treatment.</br>
🌟	A **single Therapy record** (row) SHOULD be submitted **for each treatment or treatment round** being reported for the HTAN participant. </br> 
✅	All dates MUST be converted to days from index, where the index is the participant date of birth. (e.g. 'Age in Days at Treatment Start','Age in Days at Treatment Stop')</br>
🌟	For longitudinal follow-up, treatments administered since the last data was reported will be captured. New treatments SHOULD be recorded as new records in the Therapy manifest.</br>

## Clinical Tier 1: Vital Status
Clinical Tier 1 Vital Status data elements capture last known patient vital status and cause of death, when applicable.</br>
🌟	A **single Vital Status record** (row) SHOULD be submitted **for each known vital status/interaction** reported for the HTAN participant. In many cases there will be only one Vital Status record per participant. However, additional records can be added up to and including participant death. </br> 

## Clinical Tier 2
Tier 2 will contain any clinical observations not represented in the Tier 1 Clinical Data standard and must be represented as a Comma Separated Value (CSV) file. The only standardized field in the Tier 2 Clinical Data file will be HTAN Participant ID. All other data elements will be determined by the Center, in support of, for example, a publication.   These Tier 2 clinical data elements will be ingested directly into Synapse, and there will be no attempt at further standardizing any of these elements. </br>
✅	Each row in the Clinical Tier 2 csv file MUST contain a valid HTAN Participant ID in the first column.

## Specific Guidance Regarding Longitudinal Data





