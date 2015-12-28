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

The THYME corpus of notes is available to others involved in NLP research under a data use agreement (DUA) with Mayo Clinic. Please follow [the instructions for getting access to the THYME corpus on the THYME wiki](http://thyme.healthnlp.org/#Getting_access_to_the_THYME_corpus_and_gold_standard_annotations).

When using the corpus, please:

1. Include the Mayo Clinic in your acknowledgements
2. Cite the article: William F. Styler IV, Steven Bethard, Sean Finan, Martha Palmer, Sameer Pradhan, Piet C. de Groen, Brad Erickson, Timothy Miller, Chen Lin, Guergana Savova, James Pustejovsky. Temporal Annotation in the Clinical Domain. Transactions of the Association for Computational Linguistics. Vol 2 (2014). https://tacl2013.cs.columbia.edu/ojs/index.php/tacl/article/view/305

### About the annotations

The annotations in the THYME Corpus were created by annotators and adjudicators at the University of Colorado at Boulder, as well as at Boston's Harvard Children's Medical Center.  There are three different annotation types in our corpus.

#### THYME Temporal Entity and Relation Annotations

These annotations label spans as EVENTs, TIMEX3s, DOCTIME or SECTIONTIME, and then link them temporally using TLINKs and ALINKs.  Our annotation schema is derived from ISO-TimeML, with variations as described in [*Temporal Annotation in the Clinical Domain*](http://www.transacl.org/wp-content/uploads/2014/04/47.pdf), and is fully described in [The THYME Annotation Guidelines](http://clear.colorado.edu/compsem/documents/THYME%20Guidelines.pdf).   

For Clinical (_CLIN) and Radiology (_RAD) notes in both corpora, the Gold Standard notes have been double-annotated for temporal entities (EVENT, TIMEX3, DOCTIME,SECTIONTIME), adjudicated, and then double-annotated for relations (TLINK, ALINK) and adjudicated. Thus, the [docname].Temporal-Relation.gold.completed.xml files for clinical and radiology notes are fully annotated according to the THYME schema.

The Pathology (_PATH) notes, because of their temporally-sparse nature, were not given later relations annotation.  Thus, the [docname].Temporal-Entity.gold.completed.xml files only provide information about temporal entities. Absence of relations does not imply lack of relations in these notes.

#### Coreference Annotations

In addition, for some of the notes within the Colon Cancer corpus, we will have adjudicated Coreference Annotations posted, serving to mark Anaphora throughout the document, alongside a limited number of bridging relations (like SET/SUBSET or PART/WHOLE).

Not all documents have been double-annotated and adjudicated for Coreference. For those that do have Coreference Annotations, [docname].Coreference.gold.completed.xml is adjudicated gold-standard coreference data.

#### UMLS Named Entity Annotations

Finally, a subset of the notes will have UMLS Named Entity tags assigned as well, in a separate XML file.  These tags mark clinical entities and events with their UMLS semantic groups ("hemicolectomy" is marked as a 'procedure', and "fever" is a 'sign/symptom').  Due to limitations in manpower, only a small portion of the corpus was fully annotated for UMLS entities.  For those that do have Coreference Annotations, [docname].UMLS-Entity.gold.completed.xml is adjudicated gold-standard coreference data.

### Annotation Format
<a name="format"/>

All data are provided in the AnaforaXML format, created by (and designed to be read in) the [Anafora Annotation Tool](https://github.com/weitechen/anafora).  The XML data format aims to be both easily human-readable and easy-to-use, and contains no source text (allowing the free distribution of annotations).

Each XML file should be read with its labeled source text file (so doc0002_CLIN.Temporal-Relation.gold.completed.xml would be read with the source file doc0002_CLIN).

### Line Endings

Because all annotations are stored as offsets, *you must be extremely careful not to modify the source text in any way*. The most common source of error comes from Windows machines changing the Unix line endings to Windows line endings when opening or unzipping the source files.  For this reason, we recommend the use of [7-zip](http://www.7-zip.org) for unzipping the source files on Windows machines, and the careful handling of those source files during any time they may spend outside of a *nix system.
