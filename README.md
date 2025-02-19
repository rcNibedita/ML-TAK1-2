![Workflow](https://github.com/user-attachments/assets/b8745e61-aa47-4327-8891-801f809db671)
# Differential Contact-Based Machine Learning Classification

## Overview

This repository contains an AI/ML-based pipeline for identifying key structural features underlying the multifaceted allosteric regulation of TAK1. By leveraging differential contact-based feature selection and various machine learning (ML) and deep learning (DL) classifiers, this approach provides an efficient framework for structural classification and visualization of important features in VMD network representation.

## Workflow

1. **Data Preparation & Feature Pre-Screening**
   - Raw datasets capture internal topology from molecular dynamics trajectories.
   - Contact-based features are extracted based on sidechain distances.
   - Differential contact identification refines the feature space for ML classification.

2. **Model Training & Feature Scoring**
   - ML classifiers: **Random Forest (RF), Support Vector Machine (SVM), XGBoost (XGB)**
   - DL classifiers: **Multilayer Perceptron (MLP), Kolmogorov-Arnold Networks (KAN)**
   - Feature importance scores computed across multiple training iterations for ML classifiers.
   - SHAP (Shapley Additive Explanations) method applied for unbiased feature evaluation of DL classifiers.

3. **Processing Feature Importance Outputs for 3D Visualization**
   - Two-body feature (distance) selection output processed in a three-column x-y-z format (columns = [residue1, residue2, featureimportance]).
   - x-y-z format data converted into a contact-based 2D array of scaled feature scores (as edge weights), compatible for VMD NetworkView visualization.

## Repository Structure

```
├── differential_contact_prescreening.ipynb  # Feature pre-screening
├── XGB.ipynb                                # XGBoost classifier
├── SVM.ipynb                                # Support Vector Machine classifier
├── RF.ipynb                                 # Random Forest classifier
├── CompositeFeatureScore.ipynb              # Composite feature scoring
├── MLP-SHAP.ipynb                           # SHAP-based MLP feature importance
├── KAN-SHAP.ipynb                           # SHAP-based KAN feature importance
├── featureimportance_for_VMD_NetworkView.ipynb  # Generating contact array for VMD visualization
├── Workflow.png                             # Pipeline diagram
```

## Key Highlights

- **Differential Contact Selection**: Identifies residue pairs contributing to key contact deviations between ‘apo’ and ‘regulated’ conformations.
- **Hybrid AI/ML Approach**: Combines traditional DL models with SHAP scoring technique.
- **SHAP-Based Interpretability**: Ensures unbiased feature selection across DL models.
- **Network Visualization**: Converts feature importance scores into interpretable molecular contact networks.

## Installation & Dependencies

Ensure the following Python packages are installed:

```bash
pip install numpy pandas scikit-learn xgboost shap imodelsx
```
## Running the Pipeline
1. Pre-screen the dataset:
   ```
   jupyter notebook differential_contact_prescreening.ipynb
   ```
3. Train ML models and compute feature scores:
   ```
   jupyter notebook XGB.ipynb
   jupyter notebook SVM.ipynb
   jupyter notebook RF.ipynb
   jupyter notebook CompositeFeatureScore.ipynb
   ```
5. Run SHAP-based analysis for DL models:
   ```
   jupyter notebook MLP-SHAP.ipynb
   jupyter notebook KAN-SHAP.ipynb
   ```
7. Generate contact matrix for VMD:
   ```
   jupyter notebook featureimportance_for_VMD_NetworkView.ipynb
   ```
