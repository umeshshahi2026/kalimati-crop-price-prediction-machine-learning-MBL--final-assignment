# Literature Review : Crop Price Prediction (Kalimati Market)
### Final Assessment: Comparative Study of ML Algorithms

---

## Nepal-Based Studies (Kalimati Market)

## 1. Analyzing Behavior of Agricultural Commodities in Kalimati Tarkari Market using Machine Learning Technique and Prediction Strategies
**Source:** ICICSET 2025, Nepal College of Information Technology, Kathmandu
**Link:** https://journal.ncit.edu.np/index.php/icicset/article/view/20

- **Method:** Facebook Prophet, Logistic Regression, STL Decomposition, K-means clustering
- **Finding:** Using the same Kalimati Tarkari dataset (2013-2023), found strong seasonal 
  patterns, with peak prices in winter (Hemanta) and lowest prices in monsoon (Barsha). 
  Prophet-based forecasting achieved MAE=32.95, R²=0.42.
- **Relevance:** Uses the exact same dataset as our study. Their seasonal findings match 
  our EDA (Monsoon boxplot showing elevated prices). Our regression-based approach 
  (R²=0.9186) substantially outperforms their Prophet-based result (R²=0.42), 
  highlighting the strength of lag-feature-based regression for short-term price prediction.

---

## 2. Kalimati Vegetable Price Index Forecasting with a Momentum Corrected Online Stacking Ensemble
**Source:** arXiv, 2026
**Link:** https://arxiv.org/abs/2605.30720

- **Method:** 14 models spanning statistical, tree-based, deep learning, hybrid, and 
  transformer architectures; 64 engineered features including lags, rolling statistics, 
  and festival calendar effects
- **Finding:** Tree-based ensembles proved most robust, while complex transformer models 
  struggled with the noisy dataset.
- **Relevance:** Confirms lag features (which we also use) are valuable predictors. 
  However, this study focuses on complex ensemble/deep learning models without a 
  simple, interpretable regression comparison, a gap our study addresses.

---

## 3. Analysis and Price Prediction of Vegetable in Nepal
**Source:** Academia.edu, 2026
**Link:** https://www.academia.edu/145999840

- **Method:** Descriptive statistics, seasonal decomposition, correlation analysis
- **Finding:** Long-term trend and seasonality analysis of Kalimati market prices 
  (2013-2025), confirming persistent price volatility driven by seasonal production 
  and supply-demand imbalance.
- **Relevance:** Provides descriptive context but does not implement predictive ML models, 
  which our study extends by building and comparing regression algorithms.

---

## International Studies

## 4. A Methodology for Crop Price Prediction Using Machine Learning
**Source:** IEEE Conference Publication, 2023
**Link:** https://ieeexplore.ieee.org/document/10031852/

- **Method:** Decision Tree, Neuro-evolutionary algorithms
- **Finding:** ML models improved crop productivity and pricing estimates.

---

## 5. Crop Price Prediction Using Machine Learning Algorithms
**Source:** IEEE Conference Publication, 2024
**Link:** https://ieeexplore.ieee.org/iel8/10674754/10674743/10675197.pdf

- **Method:** ML framework with case study
- **Finding:** Provides a real-world ML framework for crop price decision-making.

---

## 6. A Machine Learning-Based Approach for Crop Price Prediction
**Source:** Journal of Circuits, Systems and Computers, 2024
**Link:** https://www.worldscientific.com/doi/abs/10.1142/S0218126624500543

- **Method:** Decision Tree Regression, using crop name, month, year, rainfall, WPI
- **Finding:** Achieved **97.32% accuracy**; time-based features significantly improve prediction.

---

## 7. Predicting Agricultural Commodities Prices with Machine Learning: A Review of Current Research
**Source:** arXiv, 2023
**Link:** https://arxiv.org/abs/2310.18646

- **Method:** Survey/review of ML techniques
- **Finding:** ML has strong potential for agricultural price prediction, but data quality 
  and feature selection remain key challenges.

---

## 8. Vegetable Price Prediction Against Temperature Changes Using Machine Learning Techniques
**Source:** ResearchGate, 2022
**Link:** https://www.researchgate.net/publication/361867503

- **Method:** Decision Tree, Random Forest, Linear Regression
- **Finding:** Combining weather and price data improved regression model performance.

---

## 9. A Vegetable-Price Forecasting Method Based on Mixture of Experts
**Source:** Agriculture (MDPI journal), 2025
**Link:** https://doi.org/10.3390/agriculture15020162

- **Method:** ANN, SVR, LLM-based methods
- **Finding:** SVR offers simplicity and fast training, but performance varies by vegetable type.

---

## 10. Machine Learning Techniques for Forecasting Agricultural Prices: A Case of Brinjal in Odisha, India
**Source:** PLOS ONE, 2022
**Link:** https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0270553

- **Method:** GRNN, SVR, Random Forest, GBM vs ARIMA
- **Finding:** ML techniques outperformed the traditional ARIMA model.

---

## 11. An Innovative Deep Learning Based Approach for Accurate Agricultural Crop Price Prediction
**Source:** arXiv, 2023
**Link:** https://arxiv.org/abs/2304.09761

- **Method:** Graph Neural Network + CNN, focused on Potato and Tomato
- **Finding:** Potato showed **stable price behavior**, while Tomato showed **volatile price 
  behavior**, consistent with our EDA findings (Onion and Tomato more volatile than Potato).

---

## 🔍 Research Gap Identified

Nepal-specific studies on the Kalimati market (Papers 1-3) either use complex time-series 
or ensemble approaches (Prophet, 14-model stacking) or purely descriptive analysis, without 
a controlled comparison of standard regression algorithms with a dedicated feature-scaling 
experiment. International studies (Papers 4-11) mostly focus on a single crop or use complex 
deep learning/ensemble methods without a systematic comparison of standard regression 
algorithms, including the effect of feature scaling.

> This project fills that gap through a controlled comparison of 4 regression algorithms 
> (Linear Regression, Ridge Regression, Decision Tree Regressor, SVR) with lag-based 
> features and a dedicated scaling-effect experiment on Nepal's Kalimati market data 
> (Tomato, Potato, Onion), achieving R²=0.9186, substantially outperforming prior 
> Prophet-based results (R²=0.42) on the same dataset.