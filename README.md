# Intelligent Hypoglycaemia Prediction and Supervisory Control in a Simulated Closed-Loop Insulin Delivery System

**EE4050 Final Year Project — University College Cork**  
**Discipline of Electrical and Electronic Engineering**

This repository contains the final code used for a machine-learning-based hypoglycaemia prediction and supervisory control system built on the [SimGlucose](https://github.com/jxx123/simglucose) Type 1 Diabetes simulation framework.

The project uses continuous glucose monitor (CGM) data generated in simulation to predict impending hypoglycaemia and applies a supervisory safety layer to reduce its severity. The final implementation includes:

- synthetic dataset generation across 10 virtual adult patients
- feature extraction from CGM trajectories
- leave-one-patient-out model training and evaluation
- real-time supervisory intervention using the best trained model
- full validation across matched baseline and supervised simulations

---

## Repository Structure

```text
.
├── 12_Final_dataset_ML.ipynb
├── 13_FINAL_Supervisor_v15.ipynb
├── requirements.txt
└── README.md
