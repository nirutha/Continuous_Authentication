# Continuous Authentication using Inertial-Sensors of Smartphones and Deep Learning

## Project Description
**Description**<br>
Implementation of a "Continuous Authentication" approach based on inertial sensor data of smartphones. The ensemble model, proposed by Centeno et al. (2018), consists of a Siamese CNN for deep feature learning and an OCSVM for classification. A standard OCSVM with raw data input is used as baseline.

**Goals**<br>
Attempt to reproduce results reported in the original study.<br>
Evaluate approach in scenario closer to real-world setting.<br>
Propose alternative variant of the original approach.<br>


## Project's directory structure

This project's source code is based on the structure and implementation proposed by   
- H. Buech (2019). "Continuous Authentication using Inertial-Sensors of Smartphones and Deep Learning". Master thesis. Hochschule der Medien, Stuttgart. URN:[urn:nbn:de:bsz:900-opus4-65060](https://hdms.bsz-bw.de/frontdoor/index/index/docId/6506)
  

```
├── README.md          <- The top-level README for understanding this project.
├── LICENSE            <- MIT License of the referenced source code.
├── data
│   ├── external       <- Data from third party sources. (Extracted H-MOG CSV files)
│   └── processed      <- The final, canonical data sets for modeling. (Transformed in HDF)
│
├── notebooks          <- Jupyter notebooks. Consists of OCSVM and Siamese CNN scripts for exploring 
                          the continuous authentication. 
│
├── reports            <- Generated exports/reports as HTML
│   ├── optimization   <- HTML exports of Notebooks during parameter tuning
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── environment.yaml   <- The environment file for reproducing the analysis
|                         environment in theAnaconda distribution by executing
|                         `conda continauth create -f environment.yaml`
|
├── pkgs.txt           <- While environment.yaml includes only explicit installed
|                         packages and should be OS agnostic, this file includes
|                         all exact dependencies, but is specific to the OS used on the
|                         developer machine. (Use this, if the one above doesn't work)
|
└── src                <- Source code for use in this project.
    │
    ├── data           <- Scripts to download or generate data
    │
    └── utility        <- Helper scripts

```

## Get it up and running
**Install environment:**
```bash
conda env create -f environment.yml
```
**Enter environment:**
```bash
conda activate continauth
```

> **NOTE:**
All following commands are expected to be executed inside this virtual environment `continauth` and with repository root (`./`) as current working directory!

**Install Jupyterlab Extensions (optional):**
```b
jupyter labextension install @jupyter-widgets/jupyterlab-manager@0.38 @jupyterlab/toc @krassowski/jupyterlab_go_to_definition @ryantam626/jupyterlab_code_formatter jupyter-matplotlib

jupyter serverextension enable --py jupyterlab_code_formatter
```
**Start Jupyter Lab:**
```bash
jupyter lab
```
**Data download**
The preprocessed data folder is available under google drive https://drive.google.com/file/d/1rqZ28o8Gelkaq7NSdBBcMzAEZcXeE1Ow/view?usp=sharing due to size constraints could not be uploaded on blackboard. Extract the hmog_dataset.hdf5.zip to the folder /data/processed/ for further executions.

**Run exploration-hmog-statistics.ipynb:**
The notebook contains detailed description of Hmog dataset and data processing steps for creating the scenarios.

**Run ocsvm.ipynb:**
The notebook contains step wise execution of ocsvm with visualization of the results.

**Run siamese-cnn.ipynb:**
The notebook contains step wise execution of siamese cnn for feature engineering and invokes ocsvm for classification of the authentication

