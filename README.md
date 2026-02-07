# Divorce-Causal
This repo contains data, an analysis in a Jupyter Notebook, and artifacts (tables and charts) created by running the notebook. 

## Project Summary
- **Question:** Does the passage of "no fault divorce" laws affect national income inequality?
- **Design:** Staggered DiD with country/year FE; clustered SEs by country. Inference uses cluster-robust (sandwich) SEs by country (statsmodels) and a cluster pairs bootstrap over countries as a robustness check.
- **Treatment:** First year of no-fault divorce (see “Treatment Coding”)
- **Target:** Gini (0–100), inverted (higher = more equal).

- **Assumptions:** Parallel trends, no anticipation; tails binned.





## How to Run
```bash
conda env create -f environment.yml
conda activate divorce-did
jupyter lab  # open notebooks/analysis.ipynb

