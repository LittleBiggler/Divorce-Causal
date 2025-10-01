# Divorce-Causal
Do "no fault divorce" laws improve income inequality?

In this project, I study whether liberalizing divorce law causally affects national income inequality (Gini index). Because adoption years vary across countries, I use staggered difference-in-differences designs. I code divorce regimes into two categories
(I) no recognition of “irretrievable breakdown/irreconcilable differences” or procedures that are substantively one-sided, and 
(II) no-fault regimes (including recognition of irretrievable breakdown/irreconcilable differences)—in order to assemble an observational country-year panel.

Methodologically, I implement (a) a cohort design that groups countries by decade of adoption and estimates within-cohort TWFE models anchored at each cohort’s modal reform year, and (b) an event-study design that re-indexes outcomes by event time to trace pre-trends and dynamic post-reform effects (while avoiding contamination between treated and control observations, which occurs in the cohort design). 

I assess identification under parallel-trends variants (PT–GT–All baseline, plus PT–GT–Never and PT–GT–NYT as robustness frames) and use frequentist inference via statsmodels, with plans for Bayes-factor sensitivity. I discuss trade-offs between historical comparability (cohorts) and dynamic identification (event time), and outline a combined strategy—event studies within cohorts—to balance both.
