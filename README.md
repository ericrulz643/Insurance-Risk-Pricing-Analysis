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

### Claim Frequency Model Interpretation

A Poisson generalized linear model was fitted using a 150,000-policy sample, with policy exposure included as an offset. Predictors included driver age group, vehicle age group, vehicle power, vehicle brand, fuel type, bonus-malus score, and log-transformed population density. Robust standard errors were used for coefficient inference.

The model estimated meaningful adjusted differences in claim frequency across several risk characteristics. Compared with vehicles aged 0–1 year, vehicles aged 21 years or older had an estimated claim frequency approximately 69.6% lower. Drivers aged 25–34 had an estimated frequency approximately 20.3% lower than drivers aged 18–24. Higher bonus-malus scores and population density were positively associated with estimated claim frequency.

These findings represent adjusted associations rather than causal effects. The model also exhibited overdispersion relative to the standard Poisson variance assumption, indicating that alternative count-model specifications should be evaluated. Results are preliminary and should be assessed using held-out calibration and further model validation before drawing pricing conclusions.

## Tools

- Python
- pandas
- NumPy
- Matplotlib
- Google Colab

## Next Steps

- **Refine claim frequency modeling:** Evaluate alternative count models to address overdispersion and compare predictive performance.
- **Strengthen model validation:** Assess calibration on held-out data by comparing observed and predicted claim frequencies across risk deciles.
- **Complete claim severity analysis:** Investigate claim amount distributions, large claims, and suitable severity modeling approaches.
- **Develop a pure premium analysis:** Combine claim frequency and severity estimates to calculate exploratory expected claim costs across risk profiles.
- **Document findings and limitations:** Summarize key risk associations, model performance, and considerations for insurance pricing.
