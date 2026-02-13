---
order: 995
---

# AGE_IN_DAYS vs Index Dates

HTAN cannot accept dates because they are considered Protect Health Information (PHI). In order to obfuscate dates, they should be converted to days from birth.  

!!!
:warning: If your center has data indexed to enrollment date, the data needs to be converted to days from birth. 
!!!

In Phase 2, most date-related attributes are named "AGE_IN_DAYS_TO_*" to explicitly indicate that dates should be converted to days from birth. 

In Phase 1, date-related attributes were often described as "days from index date" where the index date is the participant's date of birth.

## Phase 2 AGE_IN_DAYS_*
"AGE_IN_DAYS_TO_* attributes are meant to be days from birth regardless of whether the participant is deceased or alive. The intent is to allow for data to be followed longitudinally without identifying the participant. 

## Phase 1 Index Dates
For most Phase 1 data, the index date is the participant's date of birth.  For example, a participant's therapy start date would be recorded as 365 days if the therapy took place 365 days after a participant's date of birth. 

### Phase 1 "Index" exceptions
For sequencing data, there were four attributes with 'index' in their names for which 'index' was not the date of birth.  These include:

- Single Cell Dissociation Days from Index;
- Library Preparation Days from Index;
- Sequencing Library Construction Days from Index; and
- Nucleic Acid Capture Days from Index.

Please note the descriptions for these fields in the data model.

### Phase 1 Time intervals
The HTAN Phase 1 'Diagnosis' manifest included two attributes which are not indexed to date of birth:

- Days to Last Follow up; and
- Days to Last Known Disease Status.