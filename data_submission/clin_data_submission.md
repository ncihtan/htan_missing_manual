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

## Clinical Tier 1: Demographics
Clinical Tier 1 Demographics data includes patient attributes captured at baseline or at the time of the cross-sectional observation. These data include ethnicity, race, etc. </br>
✅	A single Demographics record is REQUIRED for each HTAN participant. </br>
❌	A single HTAN participant MUST NOT have multiple demographics records. </br> 

## Clinical Tier 1: Diagnosis
Clinical Tier 1 Diagnosis data elements describe the HTAN participant’s incident tumor or premalignant lesion (PML). These data include primary diagnosis, anatomic site of the tumor or PML, and classification and grade of the lesion.</br>
✅	A single Diagnosis record is REQUIRED for each PML or tumor.</br>
✅	All dates (‘Age in Days at Diagnosis’, ‘Age in Days at Last Known Disease Status’) MUST be converted to days from index, where the index is the participant date of birth.</br>
🌟	If a participant develops a new lesion or has/had a secondary cancer, a new Diagnosis record (row) SHOULD be added to the Diagnosis manifest. In all other cases, each participant SHOULD have only one Diagnosis record. </br>

## Clinical Tier 1: Exposure
Clinical Tier 1 Exposure data elements describe the HTAN participant’s exposure to tobacco products, alcohol and other environmental exposure. These data include alcohol exposure, smoking history, years smoked, pack years smoked, and environmental exposure type.</br>
🌟	An Exposure record SHOULD be submitted to document the HTAN participant’s smoke or other exposure at baseline or at the time of observation in a cross-sectional study.  </br>
🌟	Clinical Tier 2 SHOULD be used to submit additional exposure data consistent with a publication or other documentation, if needed.

## Clinical Tier 1: Family History
Clinical Tier 1 Family History data elements capture the incidence of cancer in an HTAN participant’s family. These data include the family member’s primary diagnosis and age at diagnosis.</br>
🌟	A single Family History record SHOULD be submitted for each participant. </br>
🌟  All family members affected are provided in a comma-separated list in the participant.</br>
🌟	Clinical Tier 2 SHOULD be used to submit more extensive family history data, if needed.



