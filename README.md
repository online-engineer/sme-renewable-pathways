# Buying or Generating? Predictors of Renewable Energy Pathways in European SMEs

Code and results for the paper *"Buying or Generating? Predictors of Renewable Energy Pathways in European SMEs: An Explainable Machine Learning Analysis"* by Victor Chimaobi Chukwu.

The notebooks reproduce every table and figure in the paper from the public survey file, including the record-consistency check that led to the 20-country sample.

## Data (not included)

The analysis uses **Flash Eurobarometer 549** (SMEs, resource efficiency and green markets), GESIS study **ZA8869**, data file version 1.0.0, doi:[10.4232/1.14493](https://doi.org/10.4232/1.14493).

The data file is **not** in this repository: GESIS terms of use do not allow it to be redistributed. To rerun the analysis:

1. Register with GESIS and download `ZA8869_v1-0-0.sav` from https://doi.org/10.4232/1.14493.
2. Put the file in the same folder as the notebooks.

Country indicators from Eurostat, with their sources, are in `country_data/`.

## How to run

Run the notebooks in order (Google Colab or local Python 3; see `requirements.txt`):

| Notebook | What it does |
|---|---|
| `Day1_data_preparation` | Sample selection, record-consistency check by country, outcome and predictors, descriptive tables |
| `Day2_models` | Logistic regression, random forest and XGBoost; test AUC and confidence intervals |
| `Day3_explainability` | SHAP importances by pathway; country effects |
| `Day4_country_and_intentions` | Country indicators; adoption intentions among non-users; barriers |
| `Day5_robustness` | Repeated splits, survey weights, unseen countries, other checks |
| `Day6_data_integrity` | Results with the seven excluded countries kept in |

Day 1 writes the prepared dataset (one row per firm) that the later notebooks read. That file is derived from the GESIS microdata, so it is excluded here and created locally when you run Day 1.

All random operations use a fixed seed.

## Contents

- `notebooks/`: the six notebooks, with outputs cleared.
- `results/`: the result workbooks written by the notebooks (aggregate tables only).
- `figures/`: the figures in the paper.
- `country_data/`: country-level indicators and their sources.
- `data_dictionary.csv`: the variables used and the survey items they come from.

## Note on the data file

In version 1.0.0 of the file, answers in eight countries (AT, IE, IT, LU, MT, NL, PT and the UK) are not consistent across question blocks. The main analysis therefore uses 20 EU member states, and Day 6 shows the results with the seven EU countries kept in. GESIS confirmed the pattern in the source data and has referred it to the data provider (October 2026).

## Citation

Please cite the paper (see `CITATION.cff`) and the data: European Commission (2025). Flash Eurobarometer 549. GESIS, Cologne. ZA8869 data file version 1.0.0, doi:10.4232/1.14493.

## Licence

Code: MIT (see `LICENSE`). The survey data remain under the GESIS terms of use.
