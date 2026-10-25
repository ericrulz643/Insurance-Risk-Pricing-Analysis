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
