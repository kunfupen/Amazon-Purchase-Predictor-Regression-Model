# Amazon Purchase Predictor Regression Model

This project builds regression models to predict `log_total`, a transformed Amazon purchase total response variable, from customer and order-related features.

The analysis compares multiple modeling approaches, including K-nearest neighbors and random forest regression, with preprocessing, cross-validation, recipe-based feature engineering, and prediction output generation.

## Project Highlights

- Built regression models for Amazon purchase prediction.
- Used `tidymodels` workflows for preprocessing, resampling, tuning, and fitting.
- Evaluated KNN models with cross-validation, regular tuning grids, and feature recipes.
- Built a random forest regression workflow with normalized numeric predictors and dummy-encoded categorical predictors.
- Generated prediction CSV files for model comparison and submission-style output.
- Produced a final regression report PDF.

## Repository Structure

```text
.
├── analysis/
│   ├── knn_baseline_model.Rmd
│   ├── knn_recipe_model.Rmd
│   └── random_forest_model.Rmd
├── data/
│   └── README.md
├── outputs/
│   ├── decision_tree_predictions.csv
│   ├── knn_predictions.csv
│   ├── rf_predictions.csv
│   └── rf_predictions_alt.csv
├── reports/
│   └── amazon_purchase_regression_report.pdf
└── README.md
```

## Data

The analysis notebooks expect:

- `data/train.csv`
- `data/test.csv`

Those source datasets are not included in the current repository snapshot. The included CSV files are model prediction outputs.

See [data/README.md](data/README.md) for expected data placement.

## Analysis Workflow

The main source files are in [analysis](analysis):

- [knn_baseline_model.Rmd](analysis/knn_baseline_model.Rmd): Baseline KNN regression workflow with cross-validation and hyperparameter tuning.
- [knn_recipe_model.Rmd](analysis/knn_recipe_model.Rmd): KNN workflow with normalization, interaction terms, and PCA.
- [random_forest_model.Rmd](analysis/random_forest_model.Rmd): Random forest regression workflow with recipe preprocessing and resampling metrics.

## Outputs

Prediction outputs are stored in [outputs](outputs):

- `decision_tree_predictions.csv`
- `knn_predictions.csv`
- `rf_predictions.csv`
- `rf_predictions_alt.csv`

Each output contains an `id` column and a `predicted_values` column.

## Report

- [Full project report](reports/amazon_purchase_regression_report.pdf)

## Reproducibility

This project was developed in R Markdown. Required R packages:

- `tidyverse`
- `tidymodels`
- `readr`
- `dplyr`
- `knitr`
- `kknn`
- `ranger`

To rerun the analysis, place `train.csv` and `test.csv` in the `data/` folder, then knit the desired notebook in RStudio.

## Notes

The repository has been organized for easier review on GitHub while preserving the original modeling logic.
