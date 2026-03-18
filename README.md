# Natural Gas Price Modeling (JPMorgan Simulation)

This repository contains a Jupyter notebook (`Task1.ipynb`) that:

1. Loads a natural gas price dataset (`Nat_Gas.csv`).
2. Plots the raw time series of monthly natural gas prices.
3. Fits a **linear trend** to the data using `scipy.stats.linregress`.
4. Fits a **seasonal (annual sinusoidal) component** to the detrended residuals using least squares.
5. Combines trend + seasonal components to create a full model.
6. Plots both the fitted model and the original data.
7. Extrapolates the fitted model one year into the future.

## How to run

1. Ensure you have a Python environment with the required packages:
   - `pandas`
   - `numpy`
   - `matplotlib`
   - `seaborn`
   - `scipy`

2. Open the notebook:

   ```bash
   jupyter notebook Task1.ipynb
   ```

3. Run all cells in order.

## Notes

- The model assumes a **linear trend** plus **one annual sinusoidal cycle**.
- Extrapolating beyond the observed data uses the same fitted model and should be treated as a model-based estimate, not a forecast.
