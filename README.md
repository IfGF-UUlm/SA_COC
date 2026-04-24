# SURGE-Ahead Continuity of Care Algorithm

This GitHub repository contains the code and resources used for the machine learning model to predict discharge destinations for geriatric surgical inpatients, as described in the study "Standard-of-Care vs. Machine Learning–Recommended Discharge Destinations for Geriatric Surgical Inpatients: Algorithm Development and Validation".


## Project Overview

The SURGE-Ahead Continuity of Care Algorithm is a machine learning project developed to support individualized discharge planning for geriatric surgical inpatients.
The model predicts discharge destinations (home, acute geriatric care unit, rehabilitation facility, nursing home) using electronic health record (EHR) and comprehensive geriatric assessment (CGA) data.


## Key Messages

- The model achieves a micro-averaged ROC AUC of 0.94 and an accuracy of 82%, increasing to 85% with a human-in-the-loop strategy.
- Key predictors include Barthel Index, Clinical Frailty Scale, age, and number of medications.
- The model is designed for explainability and integration into clinical workflows.

## Scoring System
For easy implementation, we simplified the SURGE-Ahead Continuity of Care Algorithm to a scoring system.

   Predictor                                      | Points |
 |------------------------------------------------|--------|
 | Barthel Index at admission ≤ 65                | 1      |
 | Barthel Index on postoperative day 3 ≤ 50      | 3      |
 | Clinical Frailty Scale (CFS) ≥ 5               | 1      |
 | Number of Medications ≥ 8                      | 1      |
 | Age ≥ 88                                       | 1      |

A score ≥ 4 indicates suitability for discharge to an acute geriatric care unit.


## Repository Structure

- [`1_AdaBoost_OvO_Sigmoid_Training.ipynb`](./1_AdaBoost_OvO_Sigmoid_Training.ipynb): Model training and validation using AdaBoost with one-vs-one strategy and sigmoid calibration
- [`2_OKIE_analyses.ipynb`](./2_OKIE_analyses.ipynb): Additional analyses and comparisons with the OKIE dataset
- [`3_Scoring_System.ipynb`](./3_Scoring_System.ipynb): Development and evaluation of the simplified scoring system
- [`LICENSE`](./LICENSE): MIT License for this project
- [`OKIE_data.csv`](./OKIE_data.csv): Dataset from the OKIE study for comparative analysis
- [`ROC.png`](./ROC.png): Receiver operating characteristic curve for the model
- [`ROC_scoring_system.png`](./ROC_scoring_system.png): ROC curve for the scoring system
- [`ROC_simple_scoring_system.png`](./ROC_simple_scoring_system.png): ROC curve for the simplified scoring system
- [`SAh_OKIE_DB_20250303.xlsx`](./SAh_OKIE_DB_20250303.xlsx): Database used for comparative analysis
- [`SAh_OKIE_DB_meds_20250217.xlsx`](./SAh_OKIE_DB_meds_20250217.xlsx): Medication data used in the analysis
- [`bar_chart.png`](./bar_chart.png): Bar chart visualizing key predictors
- [`calibration_curves.png`](./calibration_curves.png): Calibration curves for model evaluation
- [`coc.csv`](./coc.csv): Dataset used for model training and validation
- [`coc_data.csv`](./coc_data.csv): De-identified patient data
- [`coc_predictor.joblib`](./coc_predictor.joblib): Serialized trained model for deployment
- [`cut_offs.png`](./cut_offs.png): Visualization of cut-offs and their associated accuracy
- [`data_SA_ATZ.csv`](./data_SA_ATZ.csv): Additional dataset for model training
- [`histogram.png`](./histogram.png): Histogram of model predictions
- [`table1.csv`](./table1.csv): Summary statistics of the study population

## Explore the Analysis

Open [`1_AdaBoost_OvO_Sigmoid_Training.ipynb`](./1_AdaBoost_OvO_Sigmoid_Training.ipynb), [`2_OKIE_analyses.ipynb`](./2_OKIE_analyses.ipynb) and [`3_Scoring_System.ipynb`](./3_Scoring_System.ipynb) in GitHub to inspect the model development, training, and evaluation process.


## License

This project is licensed under the MIT License.


## Citation

The manuscript is currently undergoing peer review and will be added once published.

## Contact

Questions, Feedback, or Concerns? Reach out to thomas.kocar@uni-ulm.de.







