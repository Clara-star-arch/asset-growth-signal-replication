# Asset Growth and the Cross-Section of Stock Returns

A portfolio project that reconstructs the asset growth signal, evaluates its cross-sectional behavior, and tests its predictive power using portfolio sorts and Fama-French risk adjustment.

## Project goals

This project asks whether firms with higher asset growth subsequently earn lower returns, a classic anomaly in empirical asset pricing. The workflow covers:

- constructing the asset growth signal from Compustat fundamentals
- linking firm identifiers to CRSP securities through CCM
- checking coverage, distributional properties, and outlier sensitivity
- forming equal-weighted and value-weighted portfolios
- evaluating long-short performance and FF3 alpha

## Data

This repository does **not** include WRDS, CRSP, or Compustat raw data.

To run the notebook, you need either:
- institutional WRDS access, or
- locally cached files placed in `data_raw/`:
  - `comp_funda_at.csv.gz`
  - `ccm_linktable.csv.gz`

## Repository structure

A suggested structure:

```text
.
├── notebooks/
│   └── Asset_Growth_Portfolio_Cleaned.ipynb
├── src/
│   ├── asset_growth.py
│   ├── diagnostics.py
│   └── wrds_utils.py
├── data_raw/              # not tracked
├── data_intermediate/     # generated
├── results/               # generated
└── README.md
```

## Main methods

- point-in-time construction of annual asset growth
- exclusion/filtering logic and identifier linking
- winsorization and descriptive diagnostics
- portfolio sorts by signal rank
- equal-weighted and value-weighted long-short backtests
- Fama-French three-factor regression with robust inference

## Key takeaway

The notebook documents a replication in which the asset growth signal exhibits economically meaningful long-short return spreads, with stronger performance in equal-weighted portfolios and positive abnormal performance after risk adjustment.

## What this project demonstrates

- financial data wrangling with panel structure
- signal replication and validation
- portfolio construction and backtesting
- factor-based performance evaluation
- ability to connect technical analysis to finance research questions

## Planned enhancements

1. refactor repeated notebook logic into reusable scripts under `src/`
2. add a small synthetic sample dataset so the pipeline can be demonstrated without restricted data
3. export final charts into a `figures/` folder for easier browsing
4. add a short results summary with key tables and interpretation
5. create a second notebook or script focused on portfolio evaluation only
