# Description of the ERN-common-data-elements rdf data model:


# The set of common data elements for rare diseases registration

_ The figure below shows an illustration of the complete common data elements RDF model

<p align="center"> 
    <img src="https://github.com/LUMC-BioSemantics/ERN-common-data-elements/blob/wiki/0_Patient_role.png">
</p>

This model is based on [the set of common data elements for rare diseases registration](http://www.erare.eu/sites/default/files/SetCommonData-EU%20RD%20Platform_CDS%20_final.pdf) recommended by the European commission joint research centre. There are 16 data elements: ‘Pseudonym’, ‘Date of Birth’, ‘Sex’, ‘Patient’s status’, ‘Date of death’, ‘First contact with specialised centre’, ‘Age at onset’, Age at diagnosis’, ‘Diagnosis of the rare disease’, ‘Genetic diagnosis’, ‘Undiagnosed case’, ‘Agreement to be contacted for research purposes’, ‘Consent to the reuse of data’, ’Biological sample’, ‘Link to a biobank’, ‘Classification of functioning/disability’.

The relationships defined in this data model are all based on assigning characteristics to the patient/person. If multiple forms are filled in per patient/person we need to include clinical visits, including dates etc.

**0. Person:** ...

**1.1. Pseudonym:** is modelled as a string.

**2.1. Date of Birth:** We initially used the predicate foaf:birthday, however here the date of birth is described in mm-dd, but we want to describe it in mm-dd-yyyy. We now created a new instance describing ‘date of birth’ using the NCIT class ‘Birth Date’. To this instance we have then attached xsd:DateTime with the predicate sio:has_value.

**2.2. Sex:** …



*   2.2 Sex (Patient’s sex at birth): Female; Male; Undetermined; Foetus (Unknown)
    *   <span style="text-decoration:underline;">Regarding ‘Undetermined’:</span> What is does this exactly mean? That it is not possible to determine it or that it has not been determined/not asked?

    _	A: We can’t tell what sex it is, e.g. due to sexual disorders_

    *   <span style="text-decoration:underline;">Regarding ‘Foetus (Unknown’:</span> How should this be stored? Is it important that Foetus is included or can this just be stored as ‘Unknown’. In the case of ‘Foetus (Unknown)’ is the whole form filled in for the foetus? Or the mother?

    	_A: If foetus is selected, the questionnaire is about the foetus. After discussion \
 	with Leo still unclear how to fill in the form then. The question whether ‘unknown’ \
 	is sufficient (rather than foetus (unknown)) remains to be answered._


**3.1. Patient's status:** …



*   3.1 Patient’s status (Patient alive or dead): Alive; Dead; Lost in follow-up; Opted-out
    *   <span style="text-decoration:underline;">Regarding ‘Opted-out’:</span> What does this exactly mean? That they have opted-out that their data can be used for research, but data is still collected should they change their mind later on. Or is data also not collected anymore? Is this linked to 7.1/7.2?

    	_A: If patients opt-out, their data can no longer be collected. It is unclear whether \
 	the data already been collected (before patient opted-out) can be left in or needs \
 	to be removed. _


    _	3.1 is linked to 7.1 and 7.2. However, it was still unclear in what way they were \
 	linked exactly. _


**3.2. Date of death:** …

**4.1. First contact with specialised centre:** …



*   4.1 First contact with specialised centre (Date of first contact with specialised centre): Date (dd/mm/yyyy)
    *   <span style="text-decoration:underline;">Regarding the specialised centre:</span> Which specialised centre is this? Is this referring to the specialised centre that is collecting this data? Or could it have been a different specialised centre? Should this information be stored? And how? If it is the same specialised centre then this can be included in the metadata.

    _	A: this refers to the specialised center in the ERN. Only specialized centers can  \
 	fill in the database. What if people move/ go to different specialized centers \
 	because of the absence of a diagnosis? This questions remains to be answered. \
 	For now: clinician fills in form for his specialised center. _


**5.1. Age at onset:** …



*   5.1 Age at onset (Age at which symptoms/signs first appeared): Antenatal; At birth; Date (dd/mm/yyyy); Undetermined
    *   <span style="text-decoration:underline;">Regarding ‘Antenatal’:</span> Is the whole form filled in for the foetus? Or mother? Or is the form filled in after the child is born?

    _	A: refers to the foetus you fill in the form for._

    *   <span style="text-decoration:underline;">Regarding ‘At birth’:</span> Should the description ‘At birth’ be stored here? Or should we include the date of birth here?

    	_A: at birth should be linked to 2.1. 2.1 should be leading. _


**5.2. Age at diagnosis:** …

**6.1. Diagnosis of the rare disease:** …



*   6.1 Diagnosis of the rare disease (Diagnosis retained by the specialised centre): Orpha code (strongly recommended - see link) / Alpha code / ICD-9 code / ICD-9 CM code / ICD-10 code.
    *   In case of non-rare disease, where no Orpha code is available the Disease ontology should be used. Which are these diseases?

    	_A: A few ICD-10 codes should be added (forget ICD-9). Leo should provide the \
 	ICD-10 codes. _


**6.2. Genetic diagnosis:** …

**6.3. Undiagnosed case:** We have added ‘no diagnosis’ as an option to the model for cases where no diagnosis is available. In addition phenotype and genotype can be collected for these patients.

**7.1 Agreement to be contacted for research purposes:** …

**7.2. Consent to the reuse of data:** …

**7.3. Biological sample:** …

**7.4. Link to a biobank:** …

**8.1. Classification of functioning/disability:** For the disability profile/score: We defined an instance describing the ‘Activity’



*   8.1 Classification of functioning/disability (Patient’s disability profile according to International Classification of Functioning and Disability (ICF): Disability profile / Score
    *   By whom is this score calculated, the patient or the doctor? Should this information be captured in the model? Should the details for each of the 12 points be stored? Or just the final score? Do you want the opportunity to fill in the score for each of the 12 points in Castor? Or just the final score?

    _	A: Doctor fills in the scores in Castor. It is still unclear whether the patient \
 	answers the questions him/herself or the doctor asks the questions to the patient. \
 	In addition, it is still unclear  whether only the total score or also the subscores \
 	should be collected. These questions should be asked to Brussels (where the \
 	minimal data set was generated)._


In this data model we have used **snomed**, which has a licence, which considerations do we need to take here when thinking about reusability within multiple countries?
