# Divorce-Causal
Do "no fault divorce" laws improve income inequality?

In this project, I study whether liberalizing divorce law causally affects national income inequality (Gini index). Because adoption years vary across countries, I use staggered difference-in-differences designs. I code divorce regimes into two categories
(I) no recognition of “irretrievable breakdown/irreconcilable differences” or procedures that are substantively one-sided, and 
(II) no-fault regimes (including recognition of irretrievable breakdown/irreconcilable differences)—in order to assemble an observational country-year panel.

Methodologically, I implement (a) a cohort design that groups countries by decade of adoption and estimates within-cohort TWFE models anchored at each cohort’s modal reform year, and (b) an event-study design that re-indexes outcomes by event time to trace pre-trends and dynamic post-reform effects (while avoiding contamination between treated and control observations, which occurs in the cohort design). 

I assess identification under parallel-trends variants (PT–GT–All baseline, plus PT–GT–Never and PT–GT–NYT as robustness frames) and use frequentist inference via statsmodels, with plans for Bayes-factor sensitivity. I discuss trade-offs between historical comparability (cohorts) and dynamic identification (event time), and outline a combined strategy—event studies within cohorts—to balance both.

# Background:

This study complements my parallel project, CoResidence Analysis (repo: https://github.com/LittleBiggler/CoResidence)

Exploratory visuals from that work show several features with inflection points in the 1970s–1980s and broad shifts toward households that are (1) older and (2) more often female-headed. During this period, the share of female-headed households rose, average number of children per household fell, and household age increased. If household configuration relates to inequality, *something important* appears to change in the 1970s–1980s.

When I consider shocks that plausibly reshape household structure—illness, job loss, and divorce—divorce stands out as both substantively meaningful, and empirically tractable: adoption years are relatively easy to document across countries. Beyond data availability, a society’s willingness to liberalize divorce is signal-rich, reflecting deep shifts in norms and interpersonal arrangements.

Because I analyze countries globally, my hope is that cross-country heterogeneity helps “average out” idiosyncratic parallel trends, sharpening identification on divorce law as a potential causal catalyst rather than on unrelated confounders.
