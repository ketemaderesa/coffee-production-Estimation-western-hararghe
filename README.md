# Coffee production modelling — reproducibility deposit

## Contents
| # | File | Content | Purpose |
|---|------|---------|---------|
| 1 | `coffee_production_pipeline.ipynb` | Full executable notebook (year-blocked CV folds, 1-SE selection, test metrics, bootstrap, permutation importance, LODO) | Reproducibility |
| 2 | `Coff_Poduction.csv` | Analysis dataset (500 x 17); MD5 `352820e95c947d0da671e4ed66fbe01c` | Data version |
| 3 | `reproducibility_manifest.json` | Seed, features, target, CV type, selection rule, selected model, bootstrap details, NASA POWER parameters | Reproducibility |
| 4 | `leakage_check.json` | Confirms no district/year leakage; train/test years disjoint | Reproducibility |
| 5 | `reconciliation_notes.json` | Explains district-identifier reconciliation | Supports Section 2.3 |
| 6 | `README.md` | This guide | Reproducibility |
| 7 | `outputs/` (CSV files) | Regenerated outputs of Tables 3, 4, 6, 7, 8, 9, 10 and S10, S12, S15 | Verification without running code |

## How to run
1. Open `coffee_production_pipeline.ipynb` in Google Colab.
2. Mount Google Drive (`drive.mount('/content/drive')`).
3. Place `Coff_Poduction.csv` in `MyDrive/` (path set in Part 1: `DATA_PATH`).
4. Run all cells. Outputs are written to `publication_outputs_final`.

## Environment
- Python 3, scikit-learn, XGBoost, pandas, numpy, scipy, matplotlib.
- Random seed: `42` (set in the notebook).
- Selected model: `LinearRegression` (1-SE + parsimony heuristic).

## Notes
- `Coff_Poduction.csv` is the only data input; no external download needed.
- All tables/figures in the manuscript can be regenerated from the notebook.
- Bootstrap CIs: district-year block, percentile, 2000 resamples, seed 42.
