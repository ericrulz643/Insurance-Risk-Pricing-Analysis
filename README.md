# Insurance-Risk-Pricing-Analysis

## Project Overview

This project analyzes French motor third-party liability insurance data to investigate claim frequency, claim severity, and factors associated with insurance risk. The goal is to apply exploratory data analysis and actuarial concepts to identify patterns that may be useful for insurance pricing.

## Objectives

- Measure overall claim frequency using policy exposure.
- Investigate how claim frequency varies by driver age, vehicle age, and population density.
- Examine the distribution of claim amounts and the impact of large claims.
- Develop a foundation for further insurance risk and pricing analysis.

## Data

The project uses two datasets:

- **Frequency data:** Policy characteristics, exposure, and claim counts.
- **Severity data:** Individual claim amounts.

The datasets are from the French motor third-party liability insurance dataset commonly known as `freMTPL2`. Raw data files are not stored in this repository.

## Preliminary Findings

- Overall claim frequency was approximately **10.07 claims per 100 policy-years**.
- Drivers aged 18–24 had a higher observed claim frequency than the other age groups examined.
- Claim frequency generally decreased across older vehicle-age groups.
- Claim frequency increased across the population-density groups examined.
- The largest approximately 1% of severity records accounted for **37.96% of the total recorded claim amount**, highlighting the importance of large losses.

These findings are descriptive and do not establish that any particular factor causes higher claim frequency.

### Claim Frequency Modeling

A Poisson generalized linear model (GLM) was developed to analyze motor insurance claim frequency using driver age group, vehicle age group, and log-transformed population density. Policy exposure was included as an offset to account for differences in time at risk.

The model identified adjusted associations between these risk factors and claim frequency. Younger drivers had higher estimated claim frequencies than older driver groups, while policies covering newer vehicles also showed higher estimated frequencies than those covering older vehicles. Claim frequency tended to increase with population density, holding the other included factors constant.

### Model Validation

Model performance was evaluated using five-fold cross-validation and mean Poisson deviance. The risk-factor GLM achieved an average held-out deviance of **0.32535**, compared with **0.33109** for a baseline model that predicted claim counts using the overall training-set claim rate.

This represents an approximately **1.74% reduction in average Poisson deviance**, with the GLM outperforming the baseline in all five folds. The improvement was modest but consistent across folds.

The analysis is exploratory. The model exhibits evidence of overdispersion, and the results do not establish causal relationships or constitute a complete insurance pricing model.

## Tools

- Python
- pandas
- NumPy
- Matplotlib
- Google Colab

## Next Steps

- Complete additional claim severity analysis.
- Investigate the relationship between policy characteristics and claim frequency.
- Develop a pure premium analysis combining claim frequency and severity.
- Explore statistical modeling approaches for insurance pricing.
