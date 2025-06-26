# PRISM-Q (Patient Real-World Internet Search Medical Questions) Dataset



**PRISM-Q** is a curated dataset of 500 patient-phrased medical questions sourced from real-world internet searches. It is designed to support research in Large Language Models and clinical reasoning by capturing the authentic language and concerns of patients seeking medical information online.

## Dataset Overview

The dataset is evenly divided into five clinically relevant domains (100 questions each):

- **Symptom Management & Treatment**  
- **Acute Emergency Scenarios**  
- **Medication Safety & Drug Interactions**  
- **Mental Health & Psychiatric Conditions**  
- **Diagnostic Test & Laboratory Result Interpretation**

Each question preserves the original, natural phrasing as typed by users (e.g., _“I can’t stop worrying do I have anxiety?”_ or _“Should I go to the ER if my child swallowed a battery?”_), enabling models to learn from unfiltered, real-world patient language.


## Annotation Information

Every question in PRISM-Q is annotated along the following dimensions:

### Domain Category
Indicates the clinical theme or context of the question:
- Symptom Management & Treatment
- Acute Emergency Scenarios
- Medication Safety & Drug Interactions
- Mental Health & Psychiatric Conditions
- Diagnostic Test & Laboratory Result Interpretation

### Intent Category
Defines the underlying purpose of the question:
- **Symptom Interpretation** – e.g., _“Why do my fingers feel stiff?”_  
- **Diagnosis Interpretation** – e.g., _“My doctor says I have ADHD, what does that mean?”_  
- **Treatment** – e.g., _“How do I treat my spring allergies?”_  
- **Emergency Interpretation** – (event vs. symptom-specific)  
- **Drug Interaction**

### Clinical Concept
Represents the relevant clinical area or diagnosis:
- Includes both general conditions (e.g., “Abdominal Pain”, “ADHD”, “Borderline Personality Disorder”)  
- Diagnostic interpretation entries are labeled with explicit **test result status**:  
  - `Positive`, `Negative`, `Inconclusive`, `Normal`, `Abnormal`

---

## Triage Level (Emergency Scenarios Only)

Acute emergency questions are labeled using a five-point triage scale, adapted from ER protocols:

| **Level** | **Description** | **Examples** |
|----------|------------------|--------------|
| 1        | **Immediate** – Immediate, life-saving intervention required without delay. | Conditions like cardiac arrest; unresponsive patient; or severe respiratory distress.  |
| 2        | **Emergent** – High risk of deterioration | Conditions and symptoms that are potentially life-threatening and require rapid treatment, such as heart attack, or stroke.|
| 3        | **Urgent** – Stable but requires multiple resource types (e.g., labs + imaging).| Conditions that need prompt attention but are not immediately life-threatening, like deep cuts, moderate pain, or signs of infection. |
| 4        | **Semi-Urgent** – Stable with only one resource anticipated (e.g., x-ray or sutures) | Conditions that are not life-threatening and can wait for treatment, such as sprains, minor cuts, or earaches. |
| 5        | **Non-Urgent** – Stable, with no or minimal intervention and resources anticipated |Conditions that just require oral/topical medications or prescriptions.|

## Drug Interaction Categorization (Medication Questions Only)

For medication safety questions, the following additional metadata is included:

- **Interaction Severity**
  - `None`, `Minor`, `Moderate`, `Severe`
  
- **Pharmacological Classes**
  - Each agent is mapped to its drug class (e.g., `ACE inhibitor`, `SSRI`, `Beta-blocker`, `NSAID`, `Herbal supplement`)

---

## File Contents

- `prism_q_dataset.csv` – Main dataset with question text and annotations  
- `annotation_guidelines.csv` – Full explanation of labels and examples  

