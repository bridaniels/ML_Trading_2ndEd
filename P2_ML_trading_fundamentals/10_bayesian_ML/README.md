# **Chapter 10: Bayesian Machine Learning - Dynamic Sharpe Ratios and Pairs Trading**
---

## Classical Statistics: 
- Frequentist Approach of probability = relative frequency over a period of time
- Input Data: assumed as a random sample from a population
- Parameters: fixed output (point estimates of parameter values)
    - at least as many data points as parameters estimated  

## Bayesian Statistics: 
- Probability = measure of confidence in event occurence 
    - more subjective statistical method, good when you have less emperical data 
    - useful for rare or unique events (relevant/historical data + unique circumstances that update in real time)
- Input Data: taken as is
- Parameters: random variables with a distribution from the data
- **Bayesian Assumptions** expressed as **Probability Distributions**

## Bayes' Theorem: 
- updating beliefs by combining prior assumptions with new emperical evidence
- compare resulting parameter estimates with their frequentist counterparts
- **THETA**: parameter or vector of parameters
    - discrete or continuous
> **Two Approaches to Bayesian Statistical Inference:**
>
> 1. **Conjugate Pairs:** facilitate updatng process via a closed-form exact analytical solution 
> 2. **Approximate Inference:** simulates distribution from assumptions and data, then uses samples from the distribution to compute statistical insights 
> - produce insights into unobserved parameters (ex. expected value)

### **Posterior Probability Distribution** computed to update parameter beliefs
- *Prior* distribution = likelihood of each hypothesis
- *Likelihood Function* = probabiity of observing a dataset when given certain values for parameters (THETA) 
    - for a specific hypothesis
- *Evidence* = measures how likely the observed data is
    - given all hypotheses
- **Posterior** = product of *prior distribution* and *likelihood function*, divided by the *evidence*
    - reflects probability distribution of the hypothesis
    - updated by prior assumptions and data
    - *with continuious variables the formulation becomes more complex with multiple integrals*

