
is organized as a sequential, interdependent clinical workflow:  
	Task 1 → Task 2 → Task 3 → Task 4 → Task 5.  
Outputs from earlier stages are explicitly fed into subsequent ones, enforcing cross-stage correlation and sequential consistency across the pipeline. Concretely, the five stage-level tasks and their evaluation metrics are:

• Task 1: Specialty Referral determines case urgency and routes the patient to an appropriate clinical department. We use Accuracy for first-level department and Intersection over Union (IoU) for second-level department assignment. 

• Task 2: Test Ordering specifies examinations/tests to be ordered. We use IoU to measure set overlap between predicted and reference medical items (coverage and precision). 

• Task 3: Examination summarizes the results of requested examinations, including medical image interpretation and report drafting. We use DocLens [45] to assess the quality of generated image interpretation compared to references. 

• Task 4: Diagnosis integrates evidence from Tasks 1–3 to produce a diagnostic conclusion. We use LLM-as-a-Judge to evaluate diagnostic correctness and reasoning coherence. 

• Task 5: Treatment formulates a patient-specific treatment plan under clinical constraints. We use IoU to measure overlap between predicted and reference treatment items.