---
order: 997
---

# Creating HTAN Identifiers

This page contains step by step instructions for HTAN Centers and Trans Network Projects (TNPs) to create and manage HTAN identifiers.  HTAN identifiers should be created for all entities (participants, biospecimens and data-files) within individual research projects. 

Changes to the HTAN Identifier schema were introduced in Phase 2. There are separate instructions below for Phase 2 and Phase 1 Centers.  

## Instructions -- Phase 2 Centers 

### Step 1: Determine your HTAN Center ID

Please see [HTAN Centers](../overview/centers.md) to determine your HTAN Center ID.  If the data are part of a Trans Network Project (TNP), use the HTAN Center ID assigned to the TNP.

### Step 2: Assign HTAN Identifiers for all Research Participants.

Create a unique HTAN Identifier for each research participant in the following format:

`<participant_id>`::= `<htan_center_id>_integer`

e.g. HTA209_1

Each HTAN Center/TNP controls their own namespaces, and therefore owns all identifiers that begins with their prefix.  The integer value following `<htan_center_id>` is determined by the HTAN Center/TNP. 

!!! Participant IDs do not need to be consecutive

HTAN Centers/TNPs may choose to use integer blocks to assign groups.  For example, University of San Francisco may have four clinical sites, and may wish to reserve HTA200_1 to HTA200_1000 for all patients from site 1, and HTA200_1001 to HTA200_2000 for all patients from site 2.  These blocks are entirely up to the research project and not managed by the DCC. The assigned integers in a set of identifiers need not be consecutive. 
!!!

!!!
[Leading zeros](https://en.wikipedia.org/wiki/Leading_zero) (e.g. HTA209_**0**1) should **not** be used in the ID. 
!!!

### Step 2b [optional]: If needed, assign HTAN identifiers for external controls

Each external control participant or blank biospecimen in your atlas, if present,  must also have a unique HTAN Identifier.  These identifiers are meant only for participants without precancerous or cancerous lesions, and therefore explicitly indicate lack of HTAN-relevant clinical data within the identifier itself.  These participant identifiers look like:

`<participant_id>`		::= `<htan_center_id>_EXTinteger`

For example, if you are part of the Yale research center, and you have three external control research participants, you will need to create three HTAN Identifiers.  For example:

HTA209_EXT1\
HTA209_EXT2\
HTA209_EXT3

As with regular research participants, the HTAN Center/TNP controls their own namespace, and therefore owns all identifiers that begin with the prefix e.g.  HTA209_EXT.  The integer value following HTA209_EXT is determined entirely by the HTAN Center/TNP.

### Step 3: Assign HTAN Identifiers for all HTAN Biospecimen and Data Files

Biospecimens such as samples, tissue blocks, slides, aliquots and analytes obtained from a research participant have identifiers which follow the pattern:

```
<biospecimen_entity_id>	::= <participant_id>_Binteger
```

where the "B" before the integer denotes "Biospecimen".

For example, if research participant 1 within the Yale Lymphoma atlas (HTA209) provided three samples, you would have three biospecimen HTAN IDs:

HTA209_1_B1\
HTA209_1_B3\
HTA209_1_B8

Data files that result from those biospecimens have identifiers which follow the pattern:

```
<datafile_entity_id>	::= <participant_id>_Dinteger
```
where the "D" before the integer denotes "Data File".

For example, if an assay was performed on a biospecimen from the same Yale Lymphoma atlas (HTA209) participant, the data files would have HTAN IDs such as:

HTA209_1_D12\
HTA209_1_D15

Analogous to research participant IDs, the unique integer value following `<participant_id>` is determined entirely by the source HTAN Center/TNP.  The ID must not have [leading zeros](https://en.wikipedia.org/wiki/Leading_zero). 

!!! Special Case Identifers
If a single biospecimen or data file is derived from multiple participants, the file identifier must contain a wildcard string, e.g. ‘0000’, after the HTAN center identifier. For example:

HTA209_0000_B1\
HTA209_0000_D23\
HTA209_0000_D67

If a data file is derived from an external control participant, the biospecimen and file identifiers will contain the string ‘EXT’ before the external control participant integer (see Step 2b, above). For example:

HTA209_EXT1_B1\
HTA209_EXT2_D58\
HTA209_EXT3_D90
!!!

### Step 4: Keep Track of all Metadata Associated with Entities

Complex relationships among entities can emerge in any research study. For example, one or more samples may be collected from a research participant at multiple times, and each of those samples may be processed through a variety of analytic workflows. It is recommended that each HTAN Center/TNP maintain their own mechanism for storing annotation of entities and relationships among those --- for example, many atlases already have in place LIMs systems or spreadsheet-based systems. 

## Instructions -- Phase 1 Centers

### Step 1: Determine your HTAN Center ID

Please see [HTAN Centers](../overview/centers.md) to determine your HTAN Center ID.  If the data are part of a Trans Network Project (TNP), use the HTAN Center ID assigned to the TNP.

### Step 2: Assign HTAN Identifiers for all Research Participants.

Create a unique HTAN Identifier for each research participant in the following format:

`<participant_id>`::= `<htan_center_id>_integer`

e.g. HTA3_1

Each HTAN Center/TNP controls their own namespaces, and therefore owns all identifiers that begins with their prefix.  The integer value following `<htan_center_id>` is determined by the HTAN Center/TNP. 

!!! Participant IDs do not need to be consecutive

HTAN Centers/TNPs may choose to use integer blocks to assign groups.  For example, CHOP may have four clinical sites, and may wish to reserve HTA4_1 to HTA4_1000 for all patients from site 1, and HTA4_1001 to HTA4_2000 for all patients from site 2.  These blocks are entirely up to the research project and not managed by the DCC. The assigned integers in a set of identifiers need not be consecutive. 
!!!

!!!
[Leading zeros](https://en.wikipedia.org/wiki/Leading_zero) (e.g. HTA3_01) should **not** be used in the ID. 
!!!

### Step 2b [optional]: If needed, assign HTAN identifiers for external controls

Each external control participant, if present, in your atlas must also have a unique HTAN Identifier.  These identifiers are meant only for participants without precancerous or cancerous lesions, and therefore explicitly indicate lack of HTAN-relevant clinical data within the identifier itself.  These participant identifiers look like:

`<participant_id>`		::= `<htan_center_id>_EXTinteger`

For example, if you are part of the Duke research center, and you have three external control research participants, you will need to create three HTAN Identifiers.  For example:

HTA6_EXT1\
HTA6_EXT2\
HTA6_EXT3

As with regular research participants, the HTAN Center/TNP controls their own namespace, and therefore owns all identifiers that begin with the prefix e.g.  HTA6_EXT.  The integer value following HTA6_EXT is determined entirely by the HTAN Center/TNP.

### Step 3: Assign HTAN Identifiers for all HTAN Biospecimen and Data Files

Derivative entities include anything derived from a research participant, including biospecimens such as samples, tissue blocks, slides, aliquots, analytes, and data files that result from assaying those biospecimens. Each derivative entity in your atlas must also have a unique HTAN Identifier.  These identifiers look like:

`<derivative_entity_id>`	::= `<participant_id>_integer`

Analogous to research participant IDs, the unique integer value following `<participant_id>` is determined entirely by the source HTAN Center/TNP.  The ID must not have [leading zeros](https://en.wikipedia.org/wiki/Leading_zero). 

!!! Special Case Identifers
If a single data file is derived from multiple participants, the file identifier can contain a wildcard string, e.g. ‘0000’, after the HTAN center identifier. For example:

HTA4_0000_1\
HTA4_0000_2\
HTA4_0000_3

If a data file is derived from an external control participant, the biospecimen and file identifiers will contain the string ‘EXT’ before the external control participant integer (see Step 2b, above). For example:

HTA6_EXT1_1\
HTA4_EXT2_2\
HTA4_EXT3_3
!!!

### Step 4: Keep Track of all Metadata Associated with Entities

Complex relationships among entities can emerge in any research study. For example, one or more samples may be collected from a research participant at multiple times, and each of those samples may be processed through a variety of analytic workflows. It is recommended that each HTAN Center/TNP maintain their own mechanism for storing annotation of entities and relationships among those --- for example, many atlases already have in place LIMs systems or spreadsheet-based systems.  







