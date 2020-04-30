## Research Agenda

* **Problem Statement:** The PubChem Bioassay database is a non-curated public repository with data from
64 sources, including: ChEMBL, BindingDb, DrugBank, EPA Tox21, NIH Molecular
Libraries Screening Program, and various other academic, government, and
industrial contributors.  Methods for extracting this public data into quality datasets,
useable for analytical research, presents several big-data challenges for which we
have designed manageable solutions. So, our target and expectation from this project is that we need to prepare the datasets in such a way so as they can be used efficiently for analytical research. 

* **Our Target:** Our target is to reproduce the task that Jason has already done in the form of *ScrubChem* and automate, generalize the pipeline as much as possible. As for kicking off the task, we could peform a case study on the Human Androgen Receptor(hAR) and possibly extend the task to generalize on different datasets. We have identified the tasks at hand as follows.
   * Cleaning and Annotating semi-structured PubChem BioAssay data repository(Need to trace the values for fields like Target,System,Technology,Time,Action Mode,Justification, Dose Response Concentrations, Controls,Averages,Replicates). These cleaning and annotation step was mainly manuel labor.
   * Creating a structured relational database using the data that was cleaned.
   * Creating hit-call datasets that can then be used for modelling and analysis.
   
* **Agenda for the next meeting** 
   * Looking for suggestion in cleaning and annotating semi-structured BioAssay databases so that we can come up with additional fields like 
		1. Target,
		2. System,
		3. Technology - Technology required for detection,
		4. Time, 
		5. Modality of Action - mode of target being tested(antagonist,agonist,inhibitor,activator,etc)[Needs to be processed from unstructured assay fields(which fields to look into?)],
		6. Justification - A field for checking whether TEST IDs contain VALUES in a specific experimental OUTCOME. It is used to flag data points that are most relevant for justifying an experimental outcome.
		7. Dose Response Concentrations
		8. Controls
		9. Average
		10. Replicates
	* As I understand,  deriving all of these additional fields(other fields maybe required as well) will be helpful in structuring our relational database 
	

* **Process of Annotations**
	1. Justification - 
		* PubChem does provide a true or false flag, called an active concentration (AC), for depositors to mark summary dose response values (e.g., IC50, EC50, AC50).
		* Based on the data table.
		* Categorizing TIDs as *max*,*min*,*mid*, *single-dose* concentration value
		* For example in the case of an "inactive" outcome, the justification could be the max-dose value for all the tests. In addition to that, in the case of "active" outcome,  the justification could be set to the min-dose value for all the tests. 
		* What if outcomes "Unspecified?"
	2. Modality of Action
		* Possibly use stemming(Porter's Word Stemming Algorithm) of words for example, "inhibitor" could be brought down to its root word "inhibit". Can classify bioassays as per the modality of actions.
		* Have to parse the BioAssay title and description texts (Anything else?)