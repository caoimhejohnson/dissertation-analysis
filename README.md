# The Algorithm and the Activist

**How Social Media Algorithms Shape Political Movements and Why Ethical Design Matters**

Master's dissertation (First Class Honours), MSc Business Analytics, Trinity College Dublin, 2024.

This repository contains the R code for the quantitative analysis. The dissertation asks: *what influence does social media content, shaped by content-filtering algorithms, have on participation in political movements?*

## Summary

I surveyed 222 respondents about their exposure to political content on social media and their participation in protests and other activism. The study used a mixed-methods design:

1. **Baseline logistic regression:** exposure to political content on social media vs. participation.
2. **Controlled logistic regression:** added demographic, political and media-use controls, selected through iterative model comparison.
3. **Heterogeneity analysis:** the same model repeated for six political issues (migration, the Israeli-Palestinian conflict, the housing crisis, climate change, cost of living and Black Lives Matter).
4. **Exploratory predictive model:** a 70/30 train/validation split with a confusion matrix.
5. **Qualitative analysis** (content and thematic analysis of open-text responses, done outside this repository).

## Key findings

- Greater exposure to political content on social media was associated with a **statistically significant higher likelihood of participation**, both in the baseline model and after adding controls.
- Qualitative analysis showed that respondents' dominant emotions about political content were sadness, helplessness, concern and frustration. Over 13% reported feeling helpless, despite continuing to participate.
- The dissertation proposes guidelines for the ethical design of social media algorithms.

## Methods

| Step | Approach |
|---|---|
| Model | Logistic regression (`glm`, binomial) |
| Dependent variable | Participation in a political movement (binary) |
| Main independent variable | Exposure to political content on social media |
| Model selection | Stepwise removal of controls across 12 specifications, compared using significance, multicollinearity (variance inflation factors) and McFadden's pseudo-R² |
| Final controls | Age, gender, area of residence, same-country residence, political ideology, social media consumption |
| Validation | 70/30 train/validation split (`set.seed(12)`), 0.5 classification threshold, confusion matrix |

## Limitations

- **Sampling:** convenience and snowball sampling (chosen for time and cost) are non-random and likely introduce selection and homophily bias, so results should not be generalised to the wider population.
- **Self-reporting:** survey responses may be affected by social desirability and limited introspection.
- **Predictive model:** the validation set is small (67 respondents) and most respondents participated, so accuracy alone overstates performance. The predictive model should be seen as exploratory.

## Repository structure

```
.
├── README.md
├── Social Media and Politics Research.R      # full analysis script
└── Word Cloud.R                              # part of content/thematic analysis
```

## Requirements

R with the following packages:

`tidyverse`, `readxl`, `car`, `caret`, `modelsummary`, `stargazer`, `skimr`, `sjPlot`

Install with:

```r
install.packages(c("tidyverse", "readxl", "car", "caret",
                   "modelsummary", "stargazer", "skimr", "sjPlot"))
```

## Data

The raw survey data is **not included**, to protect respondent privacy. 


## Author

Caoimhe Johnson | [www.linkedin.com/in/caoimhe-johnson-09bab8210] 
