# Stats 209 Final Project: Impact of Analyst Coverage on Market Quality

This repository contains the replication code for a study examining the causal effect of sell-side analyst coverage on market liquidity, price efficiency, and crash risk. The analysis uses brokerage mergers (2008–2023) as an instrumental variable (IV) to isolate exogenous shocks to information availability.

## Project Structure

The analysis pipeline should be executed in the following order:

1.  **`01_data_cleaning_and_matching.ipynb`**: Filters raw M&A data to identify exogenous brokerage closures and matches them to I/B/E/S estimator IDs.
2.  **`02_instrument_construction.ipynb`**: Identifies treated stocks, selects control stocks based on pre-shock coverage, and constructs the monthly regression panel.
3.  **`03_first_stage_event_study.ipynb`**: Verifies the instrument strength and parallel trends assumption (generates Event Study plot).
4.  **`04_wrds_data_preprocessing.ipynb`**: Processes daily CRSP data to calculate monthly market quality metrics (Hou-Moskowitz Price Delay, Amihud Illiquidity, Spread, NCSKEW).
5.  **`05_merge_data.ipynb`**: Merges the instrument panel with market outcomes and Compustat fundamental controls.
6.  **`06_main_regression_analysis.ipynb`**: Performs the primary analysis comparing Naive OLS to 2SLS (IV) regression results.
7.  **`07_robustness_check.ipynb`**: Re-runs the IV analysis using Propensity Score Matching (PSM) to ensure covariate balance.
