---
order: 999
---

# Identifiers

All research participants, biospecimens and derived data within HTAN are associated with a unique HTAN identifier.

Research participants are identified with the following pattern:

```
<participant_id> ::= <htan_center_id>_integer
```

Where the `htan_center_id` is derived from the identifier prefix table below.

| HTAN Center ID | Pilot Project or Contact PI Institution |
| -------------- | --------------------------------------- |
| HTA1           | HTAPP Pilot Project                     |
| HTA2           | PCAPP Pilot Project                     |
| HTA3           | Boston University                       |
| HTA4           | Children's Hospital of Philadelphia     |
| HTA5           | Dana-Farber Cancer Institute            |
| HTA6           | Duke University                         |
| HTA7           | Harvard Medical School                  |
| HTA8           | Memorial Sloan Kettering Cancer Center  |
| HTA9           | Oregon Health Sciences University       |
| HTA10          | Stanford University                     |
| HTA11          | Vanderbilt University                   |
| HTA12          | Washington University                   |
| HTA13          | TNP SARDANA                             |
| HTA14          | TNP TMA                                 |

Derivative data includes anything derived from a research participant, including biospecimens such as samples, tissue blocks, slides, aliquots, analytes, and data files that result from assaying those biospecimens. These identifiers follow the pattern:

```
<derivative_entity_id>	::= <participant_id>_integer
```

For example, if research participant 1 within the CHOP project has provided three samples, you would have three HTAN IDs, such as:

```
HTA4_1_1
HTA4_1_3
HTA4_1_8
```

If a single data file is generated from one of those samples, that file could have an HTAN ID such as:

```
HTA4_1_42
```

Note that the explicit linking of participants to biospecimens to assays is not encoded in the HTAN Identifier. Rather, the linking is encoded in explicit metadata elements (see [Relationship Model](relationships.md)).
