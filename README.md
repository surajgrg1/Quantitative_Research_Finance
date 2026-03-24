# JPMorgan Chase & Co. Quantitative Research Simulation

This repository contains work completed as part of the **JPMorgan Chase & Co. Quantitative Research Virtual Experience Program**. The project covers two core areas: natural gas contract pricing and loan default prediction using machine learning.

---

## Files Overview

### 1. `Natural_Gas_Pricing.ipynb`
**Natural Gas Price Modeling & Extrapolation**

- Loads historical monthly natural gas price data (`Nat_Gas.csv`).
- Plots the raw time series to visualize price trends and seasonality.
- Fits a **linear regression trend** to the data using `scipy.stats.linregress`.
- Fits a **sinusoidal seasonal component** to the detrended residuals via least squares.
- Combines trend + seasonal model to capture the full price behavior.
- **Extrapolates** the fitted model one year into the future.
- Estimates the price for any arbitrary future date using the trained model.

**Key Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`

---

### 2. `Pricing Contract Function.ipynb`
**Natural Gas Storage Contract Valuation**

- Defines a `price_contract()` function that calculates the **net value of a natural gas storage contract**.
- Takes as inputs: injection dates/prices, extraction dates/prices, storage rate, storage cost, max volume, and injection/withdrawal cost.
- Simulates gas flow — injecting when capacity allows, withdrawing when volume is available.
- Computes total revenue from extraction, subtracts purchase cost, injection/withdrawal costs, and monthly storage fees.
- Returns the **net profit/loss** of the contract.

**Key Libraries:** `datetime`, `math`

---

### 3. `Loan_Default_prediction.ipynb`
**Loan Default Prediction using Logistic Regression**

- Loads borrower financial data (`Loan_Data.csv`).
- Engineers two key features:
  - `payment_to_income` = loan amount outstanding / income
  - `debt_to_income` = total debt outstanding / income
- Fits a **Logistic Regression** model using `sklearn` to predict the probability of loan default.
- Evaluates model performance using:
  - **Confusion Matrix**
  - **ROC Curve** with AUC score
- Predicts default probability for individual borrowers.

**Key Libraries:** `pandas`, `numpy`, `sklearn`, `matplotlib`, `seaborn`

---

## Datasets

| File | Description |
|------|-------------|
| `Nat_Gas.csv` | Monthly natural gas prices used for trend and seasonal modeling |
| `Loan_Data.csv` | Borrower financial records used to train the loan default classifier |

---

## How to Run

1. Install the required dependencies:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn
```

2. Launch Jupyter Notebook:

```bash
jupyter notebook
```

3. Open and run each notebook in order (all cells top to bottom).

---

## Skills Demonstrated

- Time series analysis and extrapolation
- Derivative pricing / contract valuation
- Feature engineering for credit risk
- Logistic regression & binary classification
- Model evaluation (ROC-AUC, confusion matrix)
