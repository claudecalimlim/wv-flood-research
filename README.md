# Typhoon-Driven Flood Occurrence Prediction in Western Visayas

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20697452.svg)](https://doi.org/10.5281/zenodo.20697452)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

Code for my research on predicting typhoon-driven flooding across the five provinces of Western Visayas (Aklan, Antique, Capiz, Guimaras, Iloilo) using machine learning and SHAP-based feature analysis.

📄 **Preprint:** [Typhoon-Driven Flood Occurrence Prediction in Western Visayas Using Machine Learning: A Comparative Study with SHAP-Based Feature Analysis](https://doi.org/10.5281/zenodo.20697452), Zenodo, 2026

---

## About

Western Visayas gets hit by typhoons almost every year, and flooding is one of the biggest risks that comes with them. This project looks at whether satellite rainfall and typhoon track data can predict flood occurrence at the province level, and which factors actually drive those predictions.

Four models are compared: Logistic Regression, Random Forest, XGBoost, and SVM. SHAP is used to explain what each model relies on.

- **Data:** CHIRPS v2.0 daily rainfall and IBTrACS typhoon tracks, 25 years
- **Unit:** province-day

**Known limitation:** a "flood" here is defined as rainfall at or above each province's 90th percentile. Since rainfall is also used as a feature, the models end up predicting heavy rain from heavy rain, so the near-perfect scores reflect that circular setup rather than real flood prediction skill. A revised version using observed flood records and terrain features is planned.

---

## Repository structure

```
wv-flood-research/
├── NB1_dataset_construction.ipynb   # builds the dataset from CHIRPS + IBTrACS
├── NB2_training_and_shap.ipynb      # trains the 4 models and runs SHAP
└── README.md
```

---

## Data sources

All data is public. Raw files aren't included because of their size, so download them from the original sources:

| Data | Source |
|---|---|
| Daily rainfall | [CHIRPS v2.0](https://data.chc.ucsb.edu/products/CHIRPS-2.0/) |
| Typhoon tracks | [IBTrACS](https://www.ncei.noaa.gov/products/international-best-track-archive) |
| Province boundaries | [GADM v4.1](https://gadm.org/) |

---

## How to run

The notebooks were built in Google Colab.

1. Open `NB1_dataset_construction.ipynb` in Colab
2. Update the paths in the setup cell to match your own Google Drive
3. Run NB1 to build the dataset
4. Run `NB2_training_and_shap.ipynb` to train the models and generate the SHAP plots

---

## Citation

```bibtex
@misc{calimlim2026flood,
  author    = {Calimlim, Claude L.},
  title     = {Typhoon-Driven Flood Occurrence Prediction in Western Visayas Using Machine Learning: A Comparative Study with SHAP-Based Feature Analysis},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.20697452},
  url       = {https://doi.org/10.5281/zenodo.20697452}
}
```

---

## Author

**Claude L. Calimlim**

Master of Information Technology, West Visayas State University

📧 [codebritain@gmail.com](mailto:codebritain@gmail.com) · 🌐 [claudecalimlim.vercel.app](https://claudecalimlim.vercel.app)
