---
layout: post
title: SSC 2019 Poster
categories: [Survey Data, SSC Case Contest, Categorical Analysis]
---

This poster was a winning presentation (delivered by group member Christina Zhou) at the SSC Case Contest 2019.

![Poster](/images/poster final6_CZ_SP.png)

The data and motivation from this study was taken from the 2019 SSC Case Study contest, which can be seen [here](https://ssc.ca/en/case-study/case-study-2-risk-cardiovascular-disease-among-osteoarthritis-patients).

<h2>Objective</h2>
Past research has linked Osteoarthritis, a chronic joint disease, with risk for heart disease, an ongoing problem for the Canadian population. This project seeks to use the PUMF version of the Canadian Community Health Survey (CCHS), a nationwide cross-sectional survey. This data source has high levels of missingness in several variables and lacks sufficient information for more accurate resampling-based variance estimation of parameters. The primary objective of this study is to estimate crude and adjusted measures of association between osteoarthritis (OA) and self-reported heart diseases (HD) the survey sample, ages 20-64. Additionally, the study explored the interaction effect of sex, province, marital status, and time since immigration on the primary relationship, and the results of imputing a variable with significant missingness on effect size estimates.

<h2>Methods</h2>
Weighted logistic regression using sandwich standard error estimates were used to calculate adjusted odds ratio estimates and population attributable risk. Multiple imputation (MI) for the missing values in “household income” was conducted to estimate its effect on the above relationships.
 
<h2>Results</h2>
Following controlling for confounders, a significant link was still found between OA and HD in the survey population. The use of MI reduced the sandwich-estimated standard errors without significantly shifting the point estimates. The interaction term between Quebec and OA returned significant by the likelihood ratio test before MI. The interaction effect of sex and OA, and marital status and OA both became significant after MI.  
 
<h2>Conclusions</h2>
While the modeling for the main outcome of interest produced a significant result, it is difficult to assess how sampling errors, possible unmeasured confounders, and underrepresentation of some populations affected this analysis. The assumption income data being missing at random (MAR), is also potentially not accurate. The lack of information to use bootstrap weights may also lead to systematic bias in the estimation of standard errors.
