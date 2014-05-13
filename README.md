The THYME Corpus
=========

This is a repository for annotation data for the THYME Project, a clinical natural language processing project dedicated to extracting useful temporal relations from the clinical narrative.  More information on the THYME Project, is available at [http://thyme.healthnlp.org](http://thyme.healthnlp.org), or in [*Temporal Annotation in the Clinical Domain*](http://www.transacl.org/wp-content/uploads/2014/04/47.pdf).

## Release Schedule

Because the THYME data will be used in an upcoming SemEval Task, the data will be released in stages.  

1. TACL Train Subset Release - 5/13/2014 - Colon Cancer Notes only.  Dev subset will be released with SemEval data.
2. SemEval Releases - To Be Determined

## About the THYME Data

For ease of distribution, the THYME corpus is distributed in two parts:

1. De-identified clinical, pathology, and radiology records for a large number of patients, dealing with brain and colon cancer.   This data is only accessible by [completing a data-use agreement](#DUA).
2. Annotation data in the [AnaforaXML format](#format), containing no patient information, which can be combined with the clinical notes to provide a useful resource for natural language processing.  

### Accessing the THYME Clinical Notes
<a name="DUA"/>

The THYME corpus of notes is available to others involved in NLP research under a data use agreement (DUA) with Mayo Clinic. Requests for a copy of the THYME corpus should be made to a Mayo NLP investigator (e.g., Dr. Piet de Groen) in order to complete the DUA. After the DUA has been completed, the THYME corpus is available via a secure download mechanism. Distribution of the corpus is supported by grants GM102282 and LM010090 from the NIH; include the funding acknowledgment in your publications.

The corpus is released to an established or junior NLP investigator, formally associated with an institution; thus it is not released to a student. However, all students working with the investigator can have full access to the corpus under the DUA of the investigator. The investigator is urged to have the students work on the corpus on workstations that stay within the laboratory space of the investigator.

The steps for obtaining a DUA are:

1. Send an email to ClinicalNLP@mayo.edu indicating your interest in the THYME corpus. You will receive a form to fill out. Once that form is returned to ClinicalNLP@mayo.edu, your request will be passed on to the Mayo Clinic’s legal contracts group.
2. Mayo Legal Contracts Office will send you a partially filled-out DUA for you to add information to, and for you to have signed by your site's official signatory.
3. After you return the DUA to Mayo Clinic, Mayo Legal Contracts Office will complete the DUA and send you a copy of the fully executed DUA, and ClinicalNLP@mayo.edu will be copied on the email.
4. A Mayo Clinic NLP investigator will arrange to talk with you.
5. Once the DUA is complete and you have talked with a Mayo Clinic NLP investigator, ClinicalNLP@mayo.edu will send you instructions for obtaining the corpus via the secure downloading mechanism

When using the corpus, please cite:

Styler, William; Bethard, Steven; Finan, Sean; Palmer, Martha; Pradhan, Sameer; de Groen, Piet; Erickson, Brad; Miller, Timothy; Chen, Lin; Savova, Guergana K.; Pustejovsky, James. 2014. Temporal annotations in the clinical domain. Transactions of the Association for Computational Linguistics. http://www.transacl.org/wp-content/uploads/2014/04/47.pdf

### About the annotations

The annotations in the THYME Corpus were created by annotators and adjudicators at the University of Colorado at Boulder, as well as at Boston's Harvard Children's Medical Center.  There are three different annotation types in our corpus.

#### THYME Temporal Entity and Relation Annotations

These annotations label spans as EVENTs, TIMEX3s, DOCTIME or SECTIONTIME, and then link them temporally using TLINKs and ALINKs.  Our annotation schema is derived from ISO-TimeML, with variations as described in [*Temporal Annotation in the Clinical Domain*](http://www.transacl.org/wp-content/uploads/2014/04/47.pdf), and is fully described in [The THYME Annotation Guidelines](http://clear.colorado.edu/compsem/documents/THYME%20Guidelines.pdf).   

For Clinical (_CLIN) and Radiology (_RAD) notes in both corpora, the Gold Standard notes have been double-annotated for temporal entities (EVENT, TIMEX3, DOCTIME,SECTIONTIME), adjudicated, and then double-annotated for relations (TLINK, ALINK) and adjudicated.   The .Gold_Temporal_Relation.xml files for clinical and radiology notes are fully annotated.  

The Pathology (_PATH) notes, because of their temporally-sparse nature, were not given later relations annotation.  Thus, the .Gold_Temporal_Entities.xml files only provide information about temporal entities.  

#### Coreference Annotations

In addition, for many of the notes, we will have adjudicated Coreference Annotations posted, serving to mark Anaphora throughout the document, alongside a limited number of bridging relations (like SET/SUBSET or PART/WHOLE).   

#### UMLS Named Entity Annotations

Finally, a subset of the notes will have UMLS Named Entity tags assigned as well, in a separate XML file.  These tags mark clinical entities and events with their UMLS semantic groups ("hemicolectomy" is marked as a 'procedure', and "fever" is a 'sign/symptom').  Due to limitations in manpower, only a small portion of the corpus was fully annotated for UMLS.

### Annotation Format
<a name="format"/>

All data are provided in the AnaforaXML format, created by (and designed to be read in) the [Anafora Annotation Tool](https://github.com/weitechen/anafora).  The XML data format aims to be both easily human-readable and easy-to-use.

Each XML file should be read with its labeled source text file (so doc0002_CLIN.Gold_Temporal_Relation.xml would be read with doc0002_CLIN.txt).  Please be cautious to avoid changing the line endings of the source text file, as this may change the offsets.
