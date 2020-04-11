
## April 10 Meeting Summary

* **Problem Statement:** The PubChem Bioassay database is a non-curated public repository with data from
64 sources, including: ChEMBL, BindingDb, DrugBank, EPA Tox21, NIH Molecular
Libraries Screening Program, and various other academic, government, and
industrial contributors.  Methods for extracting this public data into quality datasets,
useable for analytical research, presents several big-data challenges for which we
have designed manageable solutions. So, our target and expectation from this project is that we need to prepare the datasets in such a way so as they can be used efficiently for analytical research. 

* **Our Target:** Our target is to reproduce the task that Brett has already done in the form of *ScrubChem* and automate, generalize the pipeline as much as possible. As for kicking off the task, we could peform a case study on the Human Androgen Receptor(hAR) and possibly extend the task to generalize on different datasets. We have identified the tasks at hand as follows.
   * Cleaning and Annotating semi-structured PubChem BioAssay data repository(Need to trace the values for fields like Target,System,Technology,Time,Action Mode,Justification, Dose Response Concentrations, Controls,Averages,Replicates). These cleaning and annotation step was mainly manuel labor.
   * Creating a structured relational database using the data that was cleaned.
   * Creating hit-call datasets that can then be used for modelling and analysis.
   
   

