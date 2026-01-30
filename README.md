# Electricity_forecasting
Time series forecasting of electricity load using PatchTST transformer model. Predicts consumption 24h ahead using OPSD data with attention visualization. Features: patch-based encoding, multi-head attention, seasonal pattern detection (daily/weekly cycles).

# Mini README 


# France Load Transformer Lab (OPSD / ENTSO-E mirrored)

## Data
- OPSD Time Series (public mirror of ENTSO-E load) — no API token required
- France actual total load (hourly). (Wind/Solar columns may be present depending on the OPSD file.)

## How to run
1. `pip install pandas numpy matplotlib scikit-learn statsmodels torch tqdm holidays`
2. Run the notebook end-to-end (downloads OPSD CSV).

## Outputs
- Load + train/test split
- Baseline (t-24) vs Patch Transformer (24h horizon)
- Error heatmap (dow x hour)
- STL decomposition (trend/seasonal/residual)
- Error vs ramping/renewable_proxy (net_import requires ENTSO-E API token)
- Day-type clustering (24h profiles)

## Key findings (expected)
- Errors spike during high ramping periods (morning/evening) and atypical days.
- Net import / renewable share correlate with forecast difficulty (system stress proxy).
- Attention often focuses near lag ~24h and ~168h (daily/weekly patterns).
