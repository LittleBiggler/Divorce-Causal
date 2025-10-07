# Divorce-Causal
Do "no fault divorce" laws improve income inequality?

In this project, I study whether liberalizing divorce law causally affects national income inequality (Gini index). Because adoption years vary across countries, I use staggered difference-in-differences designs. I code divorce regimes into two categories
(I) no recognition of “irretrievable breakdown/irreconcilable differences” or procedures that are substantively one-sided, and 
(II) no-fault regimes (including recognition of irretrievable breakdown/irreconcilable differences)—in order to assemble an observational country-year panel.

Methodologically, I implement (a) a cohort design that groups countries by decade of adoption and estimates within-cohort TWFE models anchored at each cohort’s modal reform year, and (b) an event-study design that re-indexes outcomes by event time to trace pre-trends and dynamic post-reform effects (while avoiding contamination between treated and control observations, which occurs in the cohort design). 

I assess identification under parallel-trends variants (PT–GT–All baseline, plus PT–GT–Never and PT–GT–NYT as robustness frames) and use frequentist inference via statsmodels, with plans for Bayes-factor sensitivity. I discuss trade-offs between historical comparability (cohorts) and dynamic identification (event time), and outline a combined strategy—event studies within cohorts—to balance both.

![Event study line with 95% CI zone](artifact/att_in_event_time.png)
[Significant Cohorts table](artifact/cohort_table_rounded.csv)
![Event study scatterplot with bar CI](artifact/event_study_bar.png)

# Background:

This study complements my parallel project, CoResidence Analysis (repo: https://github.com/LittleBiggler/CoResidence)

Exploratory visuals from that work show several features with inflection points in the 1970s–1980s and broad shifts toward households that are (1) older and (2) more often female-headed. During this period, the share of female-headed households rose, average number of children per household fell, and household age increased. If household configuration relates to inequality, *something important* appears to change in the 1970s–1980s.

When I consider shocks that plausibly reshape household structure—illness, job loss, and divorce—divorce stands out as both substantively meaningful, and empirically tractable: adoption years are relatively easy to document across countries. Beyond data availability, a society’s willingness to liberalize divorce is signal-rich, reflecting deep shifts in norms and interpersonal arrangements.

Because I analyze countries globally, my hope is that cross-country heterogeneity helps “average out” idiosyncratic parallel trends, sharpening identification on divorce law as a potential causal catalyst rather than on unrelated confounders.

# Conclusion

|   Event Time |   Effect (ATT) |   Observations |   Countries |   P-Value |   T-Value |   Standard Error |
|-------------:|---------------:|---------------:|------------:|----------:|----------:|-----------------:|
|          -5 (tail) |          0.417 |           2050 |          65 |     0.451 |     0.753 |            0.186 |
|           -4 |          0.013 |             65 |          65 |     0.767 |    -0.296 |            0.154 |
|           -3 |          0.335 |             65 |          65 |     0.097 |     1.657 |            0.191 |
|           -2 |          0.012 |             64 |          64 |     0.87  |     0.163 |            0.246 |
|           -1 (baseline) |          0     |             63 |          63 |   nan     |   nan     |          nan     |
|            0 |          0.073 |             62 |          62 |     0.735 |     0.338 |            0.222 |
|            1 |          **0.371** |             62 |          62 |     **0.049** |     1.967 |            0.189 |
|            2 |          0.259 |             62 |          62 |     0.248 |     1.156 |            0.237 |
|            3 |          0.386 |             60 |          60 |     0.151 |     1.436 |            0.302 |
|            4 |          0.266 |             59 |          59 |     0.24  |     1.175 |            0.265 |
|            5 (tail) |          **0.133** |           1548 |          58 |     **0.053** |     1.931 |            0.273 |
