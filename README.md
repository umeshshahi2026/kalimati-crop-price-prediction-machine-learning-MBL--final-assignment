# Kalimati Crop Price Prediction

Comparative study of six regression algorithms for predicting Tomato, 
Potato, and Onion prices at Nepal's Kalimati Tarkari market.

**Author:** Umesh Shahi (026/MDS/07)  
Department of Digital Technology, MBUST

## Dataset

Kalimati Tarkari Dataset (2013–2022), Kaggle:  
https://www.kaggle.com/datasets/nischallal/kalimati-tarkari-dataset

280,862 daily wholesale price records across 136 commodities. After filtering 
to Tomato, Potato, and Onion and aggregating to one record per crop per day, 
10,814 records remain for modelling.

## Requirements

Python 3.10 or later with: pandas, numpy, matplotlib, seaborn, scikit-learn

    pip install pandas numpy matplotlib seaborn scikit-learn

The notebook also contains an install cell, so it can be run without 
installing anything in advance.

## How to run

1. Download the dataset and place `Kalimati_Tarkari_Dataset.csv` in `data/raw/`
2. Open `notebooks/analysis.ipynb`
3. Run all cells (Run All)

Outputs: cleaned data in `data/processed/`, figures in `visuals/`, 
result tables in `report/`.

All random seeds are fixed (`random_state = 42`) and the train-test split is 
chronological rather than random, so every result reproduces exactly on 
re-execution.

## Results

| Model | MAE | MSE | RMSE | R² |
|---|---|---|---|---|
| Linear Regression | 3.965 | 51.547 | 7.180 | 0.9186 |
| Ridge Regression | 3.966 | 51.543 | 7.179 | 0.9186 |
| Lasso Regression | 3.934 | 51.679 | 7.189 | 0.9184 |
| Decision Tree Regressor | 4.496 | 65.280 | 8.080 | 0.8969 |
| SVR | 4.875 | 83.179 | 9.120 | 0.8686 |
| MLP Regressor | 4.622 | 58.212 | 7.630 | 0.9081 |

Linear Regression performed best (R² = 0.9186, MAE = 3.97 NPR/Kg).

## Additional experiments

| Experiment | Finding |
|---|---|
| Feature scaling (on/off) | No effect on linear or tree-based models; small gain for SVR |
| Scaler choice | MinMaxScaler lifts SVR from R² 0.8686 to 0.8908 |
| Feature subset ablation | Lag features alone reach R² 0.9184; calendar features alone reach 0.3358 |
| Hyperparameter tuning | Only the Decision Tree improved materially (0.8969 → 0.9133) |

Result tables for all four experiments are saved in `report/`.

## Repository structure

    data/raw/         raw dataset
    data/processed/   cleaned + feature-engineered data
    notebooks/        analysis.ipynb (full pipeline)
    report/           literature review, result tables, research paper
    visuals/          all generated figures