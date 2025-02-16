![Workflow](https://github.com/user-attachments/assets/b8745e61-aa47-4327-8891-801f809db671)
Differential Contact-Based Machine Learning Classification

Overview

This repository contains a novel AI/ML-based pipeline for identifying key structural features underlying the allosteric regulation of TAK1. By leveraging differential contact-based feature selection and various machine learning (ML) and deep learning (DL) classifiers, this approach provides an efficient framework for structural classification and visualization.

Workflow



Data Preparation & Feature Pre-Screening

Raw datasets capture internal topology from molecular dynamics trajectories.

Contact-based features are extracted based on sidechain distances.

Differential contact identification refines the feature space for ML classification.

Model Training & Feature Scoring

ML classifiers: Random Forest (RF), Support Vector Machine (SVM), XGBoost (XGB)

DL classifiers: Multilayer Perceptron (MLP), Kolmogorov-Arnold Networks (KAN)

Feature importance scores computed across multiple training iterations.

SHAP (Shapley Additive Explanations) method applied for unbiased feature evaluation.

Feature Mapping & Visualization

Top-ranked features mapped onto 2D residue connectivity maps.

3D visualization performed using VMD NetworkView, highlighting critical contact-based interactions.

Repository Structure

├── differential_contact_prescreening.ipynb  # Feature pre-screening
├── XGB.ipynb                                # XGBoost classifier
├── SVM.ipynb                                # Support Vector Machine classifier
├── RF.ipynb                                 # Random Forest classifier
├── CompositeFeatureScore.ipynb              # Composite feature scoring
├── MLP-SHAP.ipynb                           # SHAP-based MLP feature importance
├── KAN-SHAP.ipynb                           # SHAP-based KAN feature importance
├── featureimportance_for_VMD_NetworkView.ipynb  # VMD visualization
├── Workflow.png                             # Pipeline diagram

Key Features

Differential Contact Selection: Identifies key structural deviations between ‘apo’ and ‘regulated’ conformations.

Hybrid AI/ML Approach: Combines traditional ML models with advanced DL techniques.

SHAP-Based Interpretability: Ensures unbiased feature selection across ML and DL models.

Network Visualization: Converts feature importance scores into interpretable molecular contact networks.

Installation & Dependencies

Ensure the following Python packages are installed:

pip install numpy pandas scikit-learn xgboost shap vmd-python

Running the Pipeline

Pre-screen the dataset:

jupyter notebook differential_contact_prescreening.ipynb

Train ML models and compute feature scores:

jupyter notebook XGB.ipynb
jupyter notebook SVM.ipynb
jupyter notebook RF.ipynb
jupyter notebook CompositeFeatureScore.ipynb

Run SHAP-based analysis for DL models:

jupyter notebook MLP-SHAP.ipynb
jupyter notebook KAN-SHAP.ipynb

Visualize in VMD:

jupyter notebook featureimportance_for_VMD_NetworkView.ipynb


