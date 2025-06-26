Three-Stage Machine Learning-Based Intrusion Detection System
Project Overview
This project implements a three-stage machine learning pipeline for network intrusion detection and attack classification, designed to improve accuracy, efficiency, and interpretability in cybersecurity.

The pipeline sequentially processes network traffic through:

Traffic Type Classification: Multi-class classification to categorize traffic by protocols such as DNS, HTTP, FTP, etc.

Suspicious Traffic Detection: Binary classification distinguishing benign from potentially malicious traffic.

Attack Type Classification: Multi-class classification identifying specific attacks (e.g., DDoS, Bot, Heartbleed).

Code Structure and Functionality
1. Preprocessing, Feature Selection, and Modeling (Code(preprocessing+feature_selection+modeling).ipynb)
Data Loading:
Multiple CSV files from CICIDS2017 dataset are loaded, covering different days and attack types.

Data Cleaning and Preparation:
Handles missing and infinite values, duplicates, and applies Label Encoding for categorical variables.

Feature Engineering:
Extracts relevant features and prepares datasets for each model.

Model Training:
Trains three separate XGBoost models:

Traffic type classifier

Suspicious traffic detector

Attack type classifier

Model Evaluation:
Computes accuracy, precision, recall, F1-score, and generates classification reports.

Model Persistence:
Saves trained models using joblib for later use.

2. Pipeline and GUI Interface (Code(Pipeline+GUI).ipynb)
Model Loading:
Loads pre-trained models (traffic_type_model.joblib, is_Suspicious_model.joblib, attack_type_model.joblib) from the models directory.

Label Definitions:
Defines class labels for each model corresponding to their classification tasks.

User Interface:
Implements a GUI using Gradio that allows users to input network traffic feature data manually or via files.

Pipeline Execution:
Runs input data sequentially through the three models, displaying predictions for traffic type, suspicious status, and attack category.

Visualization and Interaction:
Provides real-time feedback and allows easy interaction with the model pipeline.

Usage Instructions
Data Preparation:
Prepare or download CICIDS2017 dataset CSV files. Clean and preprocess data as demonstrated in the preprocessing notebook.

Model Training:
Run the preprocessing and modeling notebook to train all three models and save them.

Run Pipeline & GUI:
Execute the pipeline GUI notebook to launch the Gradio interface. Input features to test traffic classification live.

Integration:
Use saved models to integrate into other applications or extend for batch processing.

Dependencies:

Python 3.10

pandas

numpy

matplotlib

seaborn

scikit-learn

xgboost

joblib

gradio



and you can find the dataset here : https://www.unb.ca/cic/datasets/ids-2017.html
