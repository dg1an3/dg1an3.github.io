## RTPhysicianIntentERDiagram
```plantuml
@startuml
title RT Physician Intent ER Diagram
hide methods
hide stereotypes
class Patient << (T,#FFAAAA) >>
class Study << (T,#FFAAAA) >>
class Equipment << (T,#FFAAAA) >>
class FrameOfReference << (T,#FFAAAA) >>
class Series << (T,#FFAAAA) >>
class RTPhysicianIntent << (T,#FFAAAA) >>
class RTSegmentAnnotation << (T,#FFAAAA) >>
Patient --> "1..N" Study : is_subject_of
Study --> "1..N" Series : contains
Equipment --> "1..N" Series : creates
FrameOfReference --> Series : spatially_defines
FrameOfReference --> Series : temporally_defines
Series --> "0..N" RTPhysicianIntent : contains
Series --> "0..N" RTSegmentAnnotation : contains
@enduml
```

|IE      |Module |Reference |Usage
|--------|-------|----------|--------
|Patient |[Patient](#PatientModule) |[C.7.1.1]   |M
|        |Clinical Trial Subject    |[C.7.1.3]   |U
|Study   |[General Study](#GeneralStudyModule)|[C.7.2.1]   |M
|        |[Patient Study](#PatientStudyModule)|[C.7.2.2]   |U
|        |Clinical Trial Study      |[C.7.2.3]   |U
|Series  |General Series            |[C.7.3.1]   |M
|        |Clinical Trial Series     |[C.7.3.2]   |U
|        |Enhanced RT Series        |[C.36.3]    |M
|Equipment|General Equipment        |[C.7.5.1]   |M
|        |Enhanced General Equipment|[C.7.5.2]  |M
|RT Physician Intent|General Reference|[C.12.4] |M
|        |[RT Physician Intent](#RTPhysicianIntentModule)|[C.36.5]   |M
|        |[RT Enhanced Prescription](#RTEnhancedPrescriptionModule)|[C.36.6]   |U
|        |[RT Treatment Phase Intent](#RTTreatmentPhaseIntent)|[C.36.7]   |C - Required if<br>RT Treatment Phase Intent<br>Presence Flag (3010,0045)<br>equals YES.
|        |SOP Common                |[C.12.1]   |M
|        |Common Instance Reference |[C.12.2]   |M
|        |Radiotherapy Common Instance|[C.36.4] |M


## PatientModule
```plantuml
@startuml
hide methods
class PatientModule << (M,#FFCC44) >> {
    PatientsName : PN
    PatientID : US
}
@enduml
```



## GeneralStudyModule
```plantuml
@startuml
class GeneralStudyModule << (M,#FFCC44) >> {
    StudyInstanceUID : UI
    StudyDate : DT
    StudyTime : TM 
    ReferringPhysiciansName : option<PN>
}
@enduml
```


## PatientStudyModule
```plantuml
@startuml
class PatientStudyModule << (M,#FFCC44) >> { 
    PatientWhat : UN
}
@enduml
```


## GeneralSeriesModule
```plantuml
@startuml
class GeneralSeriesModule << (M,#FFCC44) >> {
    Modality : CS
    SeriesInstanceUID : UI
}
@enduml
```


## EnhancedRTSeriesModule
```plantuml
@startuml
class EnhancedRTSeriesModule << (M,#FFCC44) >> {
    Modality : CS
    SeriesInstanceUID : UI
    SeriesNumber : IN
    SeriesDate : DT
    SeriesTime : TM
}
@enduml
```



## RTPhysicianIntentModule
```plantuml
@startuml
class RTPhysicianIntentModule << (M,#FFCC44) >> {
    RTTreatmentPhaseIntentPresenceFlag : CS
}
RTPhysicianIntentModule *--> "1..N" RTPhysicianIntentSequenceItem : RTPhysicianIntentSequence
class RTPhysicianIntentSequenceItem << (T,#FFCC44) >> {
    RTPhysicianIntentIndex : IS
    TreatmentSite : SS
    RTPhysicianIntentNarrative : LO
    RTTreatmentIntentType : CS
    RTTreatmentApproachLabel : string
}
RTPhysicianIntentSequenceItem *--> CodeSequenceMacro : TreatmentSiteCodeSequence 
RTPhysicianIntentSequenceItem *--> "1" RTPhysicianIntentPredecessorSequenceItem : RTPhysicianIntentPredecessorSequence 
RTPhysicianIntentSequenceItem *--> CodeSequenceMacro : RTProtocolCodeSequence 
RTPhysicianIntentSequenceItem *--> CodeSequenceMacro : RTDiagnosisCodeSequence 
class RTPhysicianIntentPredecessorSequenceItem {
    ReasonForSuperceding : US
}
RTPhysicianIntentPredecessorSequenceItem *--> SOPInstanceReferenceMacro
class CodeSequenceMacro << (V,#FFFF00) >> { 
}
class SOPInstanceReferenceMacro << (V,#FFFF00) >> {
}
@enduml
```



## RTEnhancedPrescriptionModule
```plantuml
@startuml
class RTEnhancedPrescriptionModule << (M,#FFCC44) >> { 
}
RTEnhancedPrescriptionModule *--> RTPrescriptionSequenceItem

class RTPrescriptionSequenceItem {
    RTPrescriptionLabel : string
    RTPrescriptionIndex : int
    ReferenceRTPhysicianIntentIndex : int
    ReferencedDosimetricObjectiveSequence : SQ
    ReferencedDosimetricObjectiveUID : UI
    ReferenceRTTreatmentPhaseSequence : SQ
}
RTPrescriptionSequenceItem *--> "0..n" RTAnatomicPrescriptionSequenceItem : RTAnatomicPrescriptionSequence
class RTAnatomicPrescriptionSequenceItem {
    ConceptualVolumeOptimizationPrecedence : int
    ConceptualVolumeBlockingConstraint : CS
    ConceptualVolumeDescription : string
}
RTAnatomicPrescriptionSequenceItem *--> EntityLabelingMacro
RTAnatomicPrescriptionSequenceItem *--> CodeSequenceMacro : TherapeuticRoleCategoryCodeSequence
RTAnatomicPrescriptionSequenceItem *--> CodeSequenceMacro : TherapeuticRoleTypeCodeSequence
RTAnatomicPrescriptionSequenceItem *--> CodeSequenceMacro : ConceptualVolumeCategoryCodeSequence
RTAnatomicPrescriptionSequenceItem *--> CodeSequenceMacro : ConceptualVolumeTypeCodeSequence
RTAnatomicPrescriptionSequenceItem *--> CodeSequenceMacro : ConceptualVolumeTypeModifierCodeSequence
RTAnatomicPrescriptionSequenceItem *--> "1" ConceptualVolumeSegmentationReferenceAndCombinationMacroAttributes : ConceptualVolumeSequence
class ConceptualVolumeSegmentationReferenceAndCombinationMacroAttributes {
}
class EntityLabelingMacro {    
    EntityLabel : string
    EntityName : string
    EntityDescription : string
}
class CodeSequenceMacro << (V,#FFFF00) >> { 
}
@enduml
```



## RTTreatmentPhaseIntent
```plantuml
@startuml
class RTTreatmentPhaseIntentModule << (M,#FFCC44) >> { 
}
@enduml
```


[C.7.1.1]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.7.html#sect_C.7.1.1 "Patient Module"
[C.7.1.3]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.7.html#sect_C.7.1.3 "Clinical Trial Subject Module"
[C.7.2.1]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.7.2.html#sect_C.7.2.1 "General Study Module"
[C.7.2.2]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.7.2.html#sect_C.7.2.2 "Patient Study Module"
[C.7.2.3]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.7.2.html#sect_C.7.2.3 "General Study Module"
[C.7.3.1]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.7.3.html#sect_C.7.3.1 "General Series Module"
[C.7.3.2]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.7.3.html#sect_C.7.3.2 "Clinical Trial Series Module"
[C.36.3]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.36.3.html#sect_C.36.3 "Enhanced RT Series Module"
[C.36.5]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.36.5.html#sect_C.36.5 "Enhanced RT Series Module"
[C.36.6]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.36.6.html#sect_C.36.6 "Enhanced RT Series Module"
[C.36.7]: http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.36.7.html#sect_C.36.7 "Enhanced RT Series Module"