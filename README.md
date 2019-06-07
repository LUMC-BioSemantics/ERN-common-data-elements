# Semantic data model of the set of common data elements for rare disease registration
_To make rare disease registry data Interoperable (the 'I' in FAIR). Version 2.0. License CC0._

Here, we present a semantic data model of [the set of common data elements for rare diseases registration](http://www.erare.eu/sites/default/files/SetCommonData-EU%20RD%20Platform_CDS%20_final.pdf) recommended by the European commission joint research centre. There are 16 data elements: ‘Pseudonym’, ‘Date of Birth’, ‘Sex’, ‘Patient’s status’, ‘Date of death’, ‘First contact with specialised centre’, ‘Age at onset’, Age at diagnosis’, ‘Diagnosis of the rare disease’, ‘Genetic diagnosis’, ‘Undiagnosed case’, ‘Agreement to be contacted for research purposes’, ‘Consent to the reuse of data’, ’Biological sample’, ‘Link to a biobank’, ‘Classification of functioning/disability’.

The semantic data model is presented below in 11 modules describing the different 16 data elements. Central to each module is the 'person'. Each module has in addition different characteristics assigned to the person.

## Module: person

<p align="center"> 
    <a href="https://drive.google.com/open?id=1HXyAfde8vmhn6yPiwlm37FpysIt9YqOS" target="_blank">
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/0_Patient_role.png"> 
    </a>
</p>


## Module: Pseudonym

Notes: Pseudonym is modelled as a string.

<p align="center"> 
    <a href="https://drive.google.com/open?id=1c_13PbOMnmM7gt-0JH10q0pcFHLDdiXE" target="_blank">
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/1_Pseudonym.png">
    </a>
</p>


## Module: Personal information

Notes:
- For 'Date of birth': We initially used the predicate foaf:birthday, however here the date of birth is described in mm-dd, but we want to describe it in mm-dd-yyyy. We now created a new instance describing ‘date of birth’ using the NCIT class ‘Birth Date’. To this instance we have then attached xsd:DateTime with the predicate sio:has_value.
- For 'Sex': We consider the patient's sex at birth. These can be 'Female', 'Male', 'Undetermined', or 'Foetus' (unknown). Undetermined means that it is not possible to determine the sex, e.g. due to sexual disorders.

<p align="center"> 
    <a href="https://drive.google.com/open?id=1AOZLvur8nIQxq40Cntql4ZIFctdJc3XT" target="_blank">
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/2_Personal_information.png">
    </a>
</p>


## Module: Patient status

Notes:
- 'Patient’s status' (Patient alive or dead). These can be 'Alive', 'Dead', 'Lost in follow-up', or 'Opted-out'. If patients opt-out, their data can no longer be collected. It is unclear whether the data already been collected (before patient opted-out) can be left in or needs to be removed. 'Opted-out' should also be somehow linked to 7.1. (Agreement to be contacted for research purposes) and 7.2. (Consent to the reuse of data) under 'Module: Consent', but it is unclear how this link should look like.

<p align="center">
    <a href="https://drive.google.com/open?id=1w8yakn-boqg5-A_AvzKmsrWgiymADDtn" target="_blank">    
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/3_Patient_status.png">
    </a>
</p>

## Module: Care pathway

Notes:
- 'First contact with specialised centre' (Date of first contact with specialised centre): Date (dd/mm/yyyy). This refers to the specialised center in the ERN. Only specialized centers can fill in the database. Open questions: ehat if people move or go to different specialized centers?

<p align="center">
    <a href="https://drive.google.com/open?id=10kokKPHOK6v63yirSlccEnzBdHGjj8Pf" target="_blank">
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/4_Care_pathway.png">
    </a>
</p>


## Module: Disease history and diagnosis

Notes:
- 'Age at onset' (Age at which symptoms/signs first appeared). These can be 'Antenatal', 'At birth', 'Date (dd/mm/yyyy)', or 'Undetermined'.
- 'Diagnosis of the rare disease' (Diagnosis retained by the specialised centre): Orpha code (strongly recommended - see link) / Alpha code / ICD-9 code / ICD-9 CM code / ICD-10 code. In case of non-rare disease where no Orpha code is available the Disease ontology should be used.

<p align="center"> 
    <a href="https://drive.google.com/open?id=1Rzl0ZGIEODhfhcnzRoP3xiD_7TfkiX5U" target="_blank">
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/5_Disease_history_and_diagnosis.png">
    </a>
</p>


## Module: Genetic diagnosis

<p align="center">
    <a href="https://drive.google.com/open?id=126NesjSHHaZk7kNSqtlFbDLZnKFDgywd" target="_blank">
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/6_Genetic_diagnosis.png">
    </a>
</p>


## Module: Undiagnosed

Notes: We have added ‘no diagnosis’ as an option to the model for cases where no diagnosis is available. In addition phenotype and genotype can be collected for these patients.

<p align="center">
    <a href="https://drive.google.com/open?id=16S5cdmcYPiFzlzpicky6eNm_20HXaYfX" target="_blank">
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/7_Undiagnosed.png">
    </a>
</p>


## Module: Consent

<p align="center"> 
    <a href="https://drive.google.com/open?id=1KXsXcmG_M2v6iQOEHzbHym9yZJL6nLNO" target="_blank">
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/8_Consent.png">
    </a>
</p>


## Module: Biobanks

<p align="center">
    <a href="https://drive.google.com/open?id=1xslS1uMj25wypD16UROol2jC6yf2TeK6" target="_blank">
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/9_Biobanks.png">
    </a>
</p>


## Module: Disability

Notes:
- For the 'Classification of functioning/disability' (Patient’s disability profile according to International Classification of Functioning and Disability (ICF): Disability profile / Score. Open question: who calculates this score (the doctor or the patient)? 
- Here, we have only modelled the final score and not all the subscores.
- Here, We defined an instance describing the ‘Activity’ of collecting the score.
- todo: take a look at the domain-range of score-wasGeneratedBY-questionnaire

<p align="center">
    <a href="https://drive.google.com/open?id=16O6jryBPCtwgrn3mC9q5mB2hflRX2Ux3" target="_blank">
        <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/10_Disability.png">
    </a>
</p>


## General notes
- The relationships defined in this semantic data model are all based on assigning characteristics to the patient/person. If multiple forms are filled in per patient/person we need to include clinical visits, including dates etc.
- In this data model we have used **snomed**, which has a licence, which considerations do we need to take here when thinking about reusability within multiple countries?
