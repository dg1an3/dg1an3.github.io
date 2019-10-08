## Federated learning pt I
One of the recurring themes at CMIMI were attempts at implemented federated or distributed learning.  The motivation was simple: need lots of data, but HIPAA.  Therefore let’s learn without giving up data.  
Different techniques: Coefficient averaging | Round robin | Gradient contrib
Gradient contrib is reminiscent of the computational argument...

But it also raised the possibility of "hyper-federated" learning.
    * Estonia coordinates all health data access through a distributed ledger, with revocation by the patient
    * FHIRChain is an example of a model that combines block chain with a common interop standard, FHIR, to achieve distributed tumor board
    * Proof of interop is another example, in this case with proof of work being replaced by a (somewhat ill-defined) proof of interop.
    
Which raises the question what other architectural problems can be solved like federated learning?
