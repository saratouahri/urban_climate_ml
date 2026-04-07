# Urban Climate ML Analysis

A machine learning project that analyzes open urban climate data to predict next-day maximum temperatures across major global cities. Built for **Google Colab** with no API keys required.

## Features
- **Data Source:** [Open-Meteo Archive API](https://open-meteo.com/) (Free, CC BY 4.0).
- **Cities:** London, New York, Tokyo, Sydney (easily extensible).
- **Model:** Random Forest Regressor (Scikit-Learn).
- **Feature Engineering:** Time-series lags, rolling statistics, cyclical time encoding.
- **Validation:** Chronological train/test split to prevent data leakage.

##  Quick Start (Google Colab)
1. **Download** the `urban_climate_ml.ipynb` file.
2. **Open** [Google Colab](https://colab.research.google.com/).
3. **Upload** the notebook (`File` → `Upload notebook`).
4. **Run** all cells (`Runtime` → `Run all`).

*No installation required; all dependencies install automatically in the first cell.*

##  Key Results & Insights
Based on the latest model run:

| Metric | Value |
| :--- | :--- |
| **MAE** | ~1.5°C - 2.5°C (varies by season) |
| **Top Feature** | `temp_max_rolling7_mean` (7-day rolling average) |
| **Observation** | Strong temporal autocorrelation; city location has less impact than recent history. |
| **Bias** | Model tends to **underestimate** temperature peaks (see prediction plot). |

![Results Preview](results.png) *(See generated plots in notebook)*

##  Improvements & Next Steps
- **Model:** Switch to **XGBoost** or **LightGBM** for better peak prediction.
- **Features:** Add city-specific seasonal interactions (e.g., `city_London × winter`).
- **Bias Correction:** Apply calibration techniques to fix systematic underestimation.
- **Resolution:** Switch to hourly data for short-term forecasting.

##  License
- **Code:** MIT License
- **Data:** Open-Meteo (CC BY 4.0)

