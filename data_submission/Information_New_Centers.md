---
order: 1000
---

# Information for New HTAN Centers

Welcome to the Human Tumor Atlas Network! Please see the [Onboarding Checklist](#onboarding-checklist) on this page for Step by Step instructions to complete onboarding for your Center. 

## General Information
The [Goverance and Policy page](../addtnl_info/governance.md) of this manual provides documentation and applicable policies detailing the requirements for publications, data sharing, and data use.  

All HTAN Institutions must have an executed Human Tumor Atlas Network DMSA  (Internal Data and Materials Sharing Agreement) [(HTAN DMSA)](https://docs.google.com/document/d/1RPFm9MBJv8DjZmYZyIv0jbjtNJ8fnwGjYDjlK4lL4nc/edit) with Sage Bionetworks prior to contributing data to the HTAN Data Coordinating Center [(DCC)](https://humantumoratlas.org/htan-dcc).  See also [HTAN Checklist for Acceptance of Data](../data_submission/checklist.html).  Sean Hanlon from the NCI will be reaching out to new Centers to coordinate collection of DMSA signatures.

HTAN Centers are assigned a [data liaison](../data_submission/Data_Liaisons.md) from the [(DCC)](https://humantumoratlas.org/htan-dcc). Trans-Network Projects (TNPs) are also assigned liaisons. Your liaison will help guide you through setting up a new atlas or project, [creating HTAN identifiers](../data_submission/creating_ids.md), and [submitting metadata and data files](../data_submission/clin_biospec_assay/).  Please keep your liaison informed of publications timelines and new data submissions.  

Please see the appropriate page of this manual for additional details about HTAN center responsibilities for [data de-identification](../data_submission/data_deidentification/), including submitting a data de-identification plan, and specific instructions regarding how to submit data.  Clinical, biospecimen, and assay data submitted to the DCC are distributed to repositories based on access levels.  Information regarding how data are accessed by external users is described more in [other parts of this manual](../overview/data_levels.md).

In order to support the FAIR (Findability, Accessibility, Interoperability, and Reusability) principles for scientific data production, the DCC has developed a [data model](../data_model/overview.md) based on established standards in the scientific research community. The HTAN Data Model is expected to evolve with advances in science.  This evolution is a community-driven, peer-reviewed process, where members of a working group will first assess established community data standards and create a [request for comment (RFC)](../addtnl_info/rfc/) document soliciting community feedback.  We look forward to working with you and learning from your expertise as we improve upon our current model.

## Onboarding Checklist

Step 1 
: Identify your Center’s assigned DCC [Data Liaison](../data_submission/Data_Liaisons.md).  

> The DCC Data Liaison is here to help you through the entire process. Your Liaison will be pleased to have an introductory call with you and your team, and will be at the HTAN face-to-face meeting.

Step 2
: Identify a Center Data Wrangler for your center.  

> The Center Data Wrangler will be the primary point of contact for all data submissions from your Center. Note that while multiple Center members may be performing data submission, the Data Wrangler should be the main point of contact with the DCC.  Please email contact information for your Data Wrangler to Alex Lash at:  alexl@ds.dfci.harvard.edu.

Step 3
: Sign the Internal Data and Materials Sharing Agreement ([HTAN DMSA](https://docs.google.com/document/d/1RPFm9MBJv8DjZmYZyIv0jbjtNJ8fnwGjYDjlK4lL4nc/edit)).

> Sean Hanlon from the NCI will be reaching out to new Institutions to coordinate collection of DMSA signatures. Please contact the [HTAN Help Desk](https://sagebionetworks.jira.com/servicedesk/customer/portal/1) with any DMSA-related questions and the Sage Bionetworks governance team will be available to assist you or your institution’s representatives. 

Step 4
: Review the [HTAN Checklist for Acceptance of Data](../data_submission/checklist.md). 

Step 5
: Review your Center’s responsibilities for [Data De-identification](https://docs.humantumoratlas.org/data_submission/data_deidentification/). 
> Please make sure to have a discussion with your data liason on this topic.

Step 6
: Instruct all indviduals who will need to contribute or view data to create a [Synapse account](https://accounts.synapse.org/register1?appId=synapse.org).

> Center Data Wranglers and any of a Center’s member(s) who will be submitting data must also become [Synapse Certified Users](https://www.synapse.org/#!Quiz:Certification). Certified Users have access to full Synapse functionality, including the ability to upload files and tables as well as create folders. To become certified, take a [short quiz](https://www.synapse.org/#!Quiz:Certification) about the [“Synapse Commons Data Use Procedure”](https://s3.amazonaws.com/static.synapse.org/governance/SynapseCommonsDataUseProcedure.pdf?v=4). This activity ensures that you understand the rules and policies that govern data sharing on Synapse. The quiz is 15 questions and should take approximately 15-20 minutes to complete. If you have any issues becoming a Synapse Certified User please contact the [HTAN Help Desk](https://sagebionetworks.jira.com/servicedesk/customer/portal/1).

Step 7
: The DCC will shortly be sharing with you a form to submit information for each individual about their contact details, role other relevant informatiom. 

> This form may only be submitted by the Center PI or Center Administrator to add a new contact with which they are affiliated. If a new contact is associated with multiple Centers or Atlases, a separate form must be submitted for each affiliation.

Step 8
: Attend [DCC Information Sessions](#coming-soon-dcc-information-sessions)

> Once all Centers have been on-boarded, the DCC will organize a series of information sessions. All Center Data Wranglers and data submitters will be required to attend information sessions. For those unable to attend, the event will be recorded and posted to the Synapse wiki.


## Coming Soon!: DCC Information Sessions

The following DCC Information Sessions are being planned.

|Session | Topics |
|--------|:-------|
|1| Getting Started:  HTAN Identifiers, Basic Demographics, Biospecimens, uploading data to Synapse |
|2| Deeper Dive on Clinical Data, including how to encode longitudinal clinical data |
|3| Submitting Assay Data:  Organizing Synapse Projects and Transferring Data |
|4| Submitting Assay Data:  Single Cell Sequencing Data |
|5| Submitting Assay Data:  Spatial Profiling Data |

To prepare for the first information meeting, all Atlas Wranglers and data submitters should:

- [ ] Review the documentation regarding [Creating HTAN Identifiers](../data_submission/creating_ids.md). Note that atlases create and manage their own identifiers, but must adhere to HTAN identifier conventions.

- [ ] Review the **Clinical Demographics data model**.  Demographics data is required, and usually the first clinical data file submitted to the DCC.  For details, go to the [Clinical Data Model](https://data.humantumoratlas.org/standard/clinical), scroll to the Manifest tab, and select Demographics.  You can also see an [example demographics file](https://www.synapse.org/Synapse:syn39256250) from Phase 1 of HTAN.

- [ ] Review the **Biospecimen data model**.  Biospecimen data is required, and is usually the second metadata file submitted to the DCC.  For details, go to the [Biospecimen Data Model](https://data.humantumoratlas.org/standard/biospecimen), scroll to the Manifest tab, and select Biospecimens.  You can also see an [example biospecimen file](https://www.synapse.org/Synapse:syn39256250) from Phase 1 of HTAN.



