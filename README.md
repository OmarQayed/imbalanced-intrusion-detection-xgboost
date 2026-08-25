# Cost-Sensitive versus Resampling-Based XGBoost for Imbalanced Network Intrusion Detection

## Overview

This repository supports an EM08DS Research Methods project investigating how imbalance-handling strategies influence minority-class network intrusion detection. The work compares cost-sensitive XGBoost with unweighted XGBoost and training-only SMOTE-XGBoost on the corrected CICIDS2017 dataset.

This repository currently contains the **research design and reproducibility scaffold**, not completed experimental results.

## Research Question

> To what extent does cost-sensitive XGBoost improve minority-class intrusion detection compared with unweighted XGBoost and training-only SMOTE-XGBoost on the corrected CICIDS2017 dataset, when evaluated using Macro-F1, per-class recall and false-positive rate?

## Proposed Experimental Conditions

1. Unweighted XGBoost
2. Cost-sensitive XGBoost
3. Training-only SMOTE-XGBoost

XGBoost is kept constant across conditions so that the principal experimental factor is the imbalance-treatment strategy rather than the choice of learning algorithm.

## Proposed Evaluation

- Primary metric: Macro-F1
- Supporting metrics:
  - per-class precision;
  - per-class recall;
  - per-class F1;
  - false-positive rate;
  - confusion matrix.

Overall accuracy will not be treated as the primary criterion because class imbalance can inflate accuracy while concealing poor minority-class detection.

## Data

The study uses the corrected/improved CICIDS2017 dataset. Raw data is **not** included in this repository. Excluding the dataset avoids unnecessary redistribution of large research data and follows reproducible-research practice: code and documentation are versioned here, while data remain at their original source.

Dataset provenance and download/access instructions should be documented here once verified.

Corrected CICIDS2017 access link: [TO BE VERIFIED BEFORE FINAL SUBMISSION]

## Proposed Methodology

1. Inspect and clean the corrected CICIDS2017 data.
2. Identify minority attack classes.
3. Create stratified training, validation and test partitions.
4. Apply imbalance treatment only to training data.
5. Train the three XGBoost conditions.
6. Evaluate all conditions on the same untouched test data.
7. Compare Macro-F1, minority-class performance and false-positive behaviour.

SMOTE must be applied only to training data to avoid information leakage into validation or test sets.

## Project Structure

- `data/raw/` — original data location; the raw dataset is not committed
- `data/processed/` — cleaned or transformed data produced during analysis
- `data/external/` — third-party data that is not part of the core raw dump
- `notebooks/` — numbered analysis notebooks
- `src/` — reusable Python modules
- `outputs/figures/` — generated figures
- `outputs/reports/` — generated analytical outputs
- `tests/` — future tests

## Environment and Reproducibility

The intended environment uses Python and packages such as:

- numpy
- pandas
- scikit-learn
- imbalanced-learn
- xgboost
- matplotlib
- jupyter / jupyterlab

`environment.yml` and `requirements.txt` document the reproducible software environment.

## Repository Status

**Current status:** Research proposal and reproducibility scaffold. The experimental implementation and results have not yet been completed.

## Author

Omar Qayed

Contact: Via GitHub profile

## License

This repository is distributed under the license contained in the `LICENSE` file.
