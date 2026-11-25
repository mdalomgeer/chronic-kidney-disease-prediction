# Chronic kidney disease prediction

Code for predicting chronic kidney disease (CKD) from routine clinical measurements using classical machine learning models.

## Data

`data/kidney_disease.csv` is the public CKD dataset from the UCI repository: 400 patient records with clinical features such as blood pressure, specific gravity, serum creatinine, blood urea and hemoglobin, labelled `ckd` or `notckd`.

Two derived files are kept next to it:

- `kidney_disease_new.csv`: after cleaning and imputing missing values
- `kidney_disease_PCA.csv`: PCA-transformed features

## Running it

```
pip install -r requirements.txt
python train_model.py --data_path data/kidney_disease.csv --output_dir results
```

`python train_model.py --help` lists the other options (ensemble method, feature selection, saving the model, plots).

## What is in src/

- `preprocessing.py`: cleaning, imputation, encoding
- `feature_engineering.py`: derived features and feature selection
- `models.py`: logistic regression, random forest, XGBoost, LightGBM, plus voting and stacking ensembles
- `evaluation.py`: metrics and plots

## A note on the numbers

The dataset is small (400 records) and fairly easy to separate, so most models score very high on it. Treat the scores as a property of this dataset. Nothing here has been validated on external or clinical data.

## Contact

Md Alomgeer Hussein, mdalomh1@umbc.edu
