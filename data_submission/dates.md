---
order: 993
---

# What is the index date?

HTAN cannot accept dates because they are considered Protect Health Information (PHI). In order to obfuscate dates, they should be converted to days from an index date.  For most data, the index date is the participant's date of birth.  For example, a participant's therapy start date would be recorded as 365 days if the therapy took place 365 days after a participant's date of birth. 

!!!
:warning: If your center has data indexed to enrollment date, the data needs to be converted to days from birth. 
!!!

## "Index" exceptions
For sequencing data, there are four attributes with 'index' in their names for which 'index' is not the date of birth.  These include:

- Single Cell Dissociation Days from Index;
- Library Preparation Days from Index;
- Sequencing Library Construction Days from Index; and
- Nucleic Acid Capture Days from Index.

Please note the descriptions for these fields in the data model.

## Time intervals
The 'Diagnosis' manifest includes two attributes which are not indexed:

- Days to Last Follow up; and
- Days to Last Known Disease Status.

Please provide these time intervals as described in the data model.