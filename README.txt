Physics-Constrained Spectral Surrogate Model (PC-SSOR) for Cp Prediction
=======================================================================

This repository contains the code used for the manuscript:

"Explainable Physics-Constrained Spectral Surrogates for Pressure Coefficient Prediction on Symmetric and Cambered Airfoils"

The project implements a physics-constrained spectral surrogate operator regression framework, referred to as PC-SSOR, for pressure coefficient (Cp) prediction on symmetric and cambered NACA airfoils using open-access wind-tunnel pressure data.

Repository link
---------------
https://github.com/najmulmowla1/Physics-Constrained-Spectral-Surrogate-Model-PC-SSOR-for-Cp-Prediction

Dataset
-------
The experimental pressure-coefficient data used in this study are publicly available from the University of Bristol data repository:

J. Branch, N. Zang, and M. Azarpeyvand, "Aeroacoustic data for four NACA series aerofoils" (2024).
DOI: https://doi.org/10.5523/bris.30c8q39wi1mxf205flnun3l5rl
Dataset page: https://data.bris.ac.uk/data/dataset/30c8q39wi1mxf205flnun3l5rl

The dataset includes aeroacoustic wind-tunnel data for four NACA airfoils:
- NACA 0012
- NACA 0024
- NACA 16-506
- NACA 16-616

Code organization
-----------------
The code is organized in modular form so that each stage of the workflow can be checked independently:

src/pcssor/
- preprocessing.py       Data loading, cleaning, coordinate handling, and surface labeling
- basis.py               Chordwise transformation, Chebyshev basis, and Gaussian radial basis functions
- model.py               PC-SSOR constrained model and KKT-based solution
- training.py            Hyperparameter selection and final model training
- metrics.py             MSE, RMSE, MAE, R2, relative L2 error, interval coverage, and width
- uncertainty.py         Validation-calibrated residual uncertainty intervals
- dense_inference.py     Anchor-grid and PCHIP-based dense-surface inference
- plotting.py            Cp distribution and comparison plots
- xai.py                 SHAP and permutation feature-importance analysis

scripts/
- run_training.py
- run_additional_inference.py
- run_xai.py


Python environment
------------------
A typical environment requires:

- Python 3.9 or newer
- numpy
- pandas
- scipy
- scikit-learn
- matplotlib
- shap
- openpyxl

Install dependencies using:

pip install -r requirements.txt

Google Colab
------------
The repository also includes Colab-compatible notebooks. These notebooks are intended for step-by-step verification of preprocessing, model training, evaluation, additional dense-surface inference, and explainability analysis.

Data and code availability statement
------------------------------------
The experimental pressure-coefficient data are publicly available from the University of Bristol data repository: Branch, Zang, and Azarpeyvand, "Aeroacoustic data for four NACA series aerofoils" (2024), DOI: 10.5523/bris.30c8q39wi1mxf205flnun3l5rl. The source code is available at: https://github.com/najmulmowla1/Physics-Constrained-Spectral-Surrogate-Model-PC-SSOR-for-Cp-Prediction.

Citation
--------
If you use the dataset, please cite:

J. Branch, N. Zang, and M. Azarpeyvand, "Aeroacoustic data for four NACA series aerofoils" (2024). DOI: 10.5523/bris.30c8q39wi1mxf205flnun3l5rl.

License
-------
Please follow the license terms of the original University of Bristol dataset and the license selected for this repository.
