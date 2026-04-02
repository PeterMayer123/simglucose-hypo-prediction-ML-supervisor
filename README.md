# Intelligent Hypoglycaemia Prediction and Supervisory Control in a Simulated Closed-Loop Insulin Delivery System

**EE4050 Final Year Project — University College Cork**  
**Discipline of Electrical and Electronic Engineering**

This repository contains the final code developed for a machine-learning-based hypoglycaemia prediction and supervisory control system built on the [SimGlucose](https://github.com/jxx123/simglucose) Type 1 Diabetes simulation framework.

The project investigates whether impending hypoglycaemic events can be predicted from continuous glucose monitor (CGM) data early enough to allow useful supervisory intervention in a simulated closed-loop insulin delivery system. The final pipeline combines synthetic dataset generation, CGM-based feature extraction, machine learning model development, and real-time supervisory validation.

The final implementation includes:

- synthetic dataset generation across 10 virtual adult patients
- feature extraction from CGM trajectories
- leave-one-patient-out model training and evaluation
- selection of the best-performing final model
- supervisory intervention using insulin attenuation, rescue carbohydrate delivery, or hybrid control
- full matched validation against baseline closed-loop simulations

---

## Repository Structure

```text
.
├── 12_Final_dataset_ML_model_v2.ipynb
├── 13_FINAL_Supervisor_v16.ipynb
├── requirements.txt
└── README.md
```

---

## Notebook Overview

### `12_Final_dataset_ML_model_v2.ipynb`

Generates the final synthetic dataset, extracts CGM-based features, trains the prediction models, and performs leave-one-patient-out evaluation. This notebook also saves the trained model and supporting artefacts required for the supervisory stage.

### `13_FINAL_Supervisor_v16.ipynb`

Loads the best model from Notebook 12, implements the supervisory controller, and runs the final validation experiments. This notebook evaluates supervisory strategies such as insulin attenuation, rescue carbohydrate delivery, and hybrid control under matched simulation conditions.

---

## How to Run

### 1. Install dependencies

It is recommended to create a virtual environment first, then install the required packages:

```bash
pip install -r requirements.txt
```

### 2. Run the notebooks in order

Run the notebooks in the following order:

1. `12_Final_dataset_ML_model_v2.ipynb`
2. `13_FINAL_Supervisor_v16.ipynb`

Notebook 12 must be run first, since it generates the trained model and saved artefacts required by Notebook 13.

---

## Outputs

Running the notebooks generates the saved models, intermediate datasets, evaluation results, and figures used in the final project report.

The first notebook produces the machine-learning artefacts needed for the supervisory notebook. The second notebook produces the final supervisory validation outputs.

---

## Pipeline Summary

The final workflow is:

1. simulate disturbed closed-loop glucose-control days in SimGlucose  
2. generate a final synthetic dataset across 10 virtual adult patients  
3. extract time-series features from CGM data  
4. train and evaluate hypoglycaemia prediction models  
5. select the best-performing model  
6. embed the selected model within a supervisory layer  
7. validate supervisory performance against matched baseline simulations  

---

## Important Notes

`13_FINAL_Supervisor_v16.ipynb` depends on files produced by `12_Final_dataset_ML_model_v2.ipynb`.

If Notebook 12 has not been run successfully first, Notebook 13 will not run correctly.

These notebooks are cleaned versions of the final project pipeline. Small numerical differences may occur across fresh reruns because the simulation includes stochastic CGM sensor noise during dataset generation. The overall methodology, model behaviour, and project conclusions are unchanged.

---

## Project Context

This work was completed as part of the **EE4050 Final Year Project** in the Discipline of Electrical and Electronic Engineering at **University College Cork**.

The repository contains the final code associated with the submitted project only.

---

## License

This repository is provided for academic and educational use only.
