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



# **Posterior Probability Distribution** computed to update parameter beliefs
### **THETA** = parameters or vector of parameters (discrete or continuous)
- *Prior Distribution* = likelihood of each hypothesis
    - probability of a future event based on current data
- *Likelihood Function* = probabiity of observing a dataset when given certain values for parameters (THETA) 
    - for a specific hypothesis
- *Evidence* = measures how likely the observed data is
    - given all hypotheses
    - challenging to compute 
    - normalizing constant
    - aka *marginal likelihood* = requires "marginalizing out" the parameters' distribution by adding or integrating over their distribution (only possible in simple cases)
- **Posterior** = product of *prior distribution* and *likelihood function*, divided by the *evidence*
    - reflects probability distribution of the hypothesis
    - updated by prior assumptions and data
    - *with continuious variables the formulation becomes more complex with multiple integrals*

## **Maximum a Posteriori Probability (MAP)** *estimation*
- leverages *evidence* as a constant factor that scales the *posterior distribution* to meet requirements of a probability distribution
- *evidence* does NOT depend on *THETA*
    - *posterior distribution* = proportional to product of the *prior distribution* and the *likelihood function*
- MAP estimation chooses value of *THETA* that maximizes the *posterior* (mode of *posterior distribution*)

## **Maximum Likelihood Estimation (MLE)** *of parameters defining probability distribution*
- *MLE* = parameter value that maximizes the *likelihood function* for observed training data
- does NOT include the *prior distribution*
    - impact of *prior distribution* on *MAP* estimate = adding data that reflects prior assumptions to the *MLE*
- reflects frequentist: probability estimates should reflect observed ratios 

# **Selecting Priors**
- *prior distribution* = reflect knowledge about the distribution of parameters due to influences on MAP estimate 
    - should know with certainty -> if not: make a choice and justify by testing if alternatives lead to the same conclusion 
- can be viewed as a regularizer
    - limits values a *posterior distribution* can assume
    - parameters with zero prior probabiity are not apart of the *posterior distribution*
> ### Several Types of *Prior Distributions*
>
> 1. **Objective Priors**: maximize impact of data on posterior 
>       - If Parameter Distribution Unknown -> select a:
>           - *Flat Prior*: uninformative *prior* (uniform distribution) over a relative range of parameter values
> 2. **Subjective Priors**: incorporate external information from the model into the estimate 
>       - opinion weighted
> 3. **Emperical Prior**: combines bayesian and frequentist using historical data to eliminate subjectivity 
>       - data centric
>
>> ### Conjugate Prior: posterior with same distribution as the prior
>> 
>> ### P(θ) such that P(θ|D) = P(θ)
>> - chosen *Prior Distribution* for the *Likelihood Function* = a *Posterior Distribution* the same as the *Prior Distribution* 
>> - Allows you to skip `posterior = likelihood * prior` computation (if you know it is a conjugate prior)
>> - implied **Closed-Form Expression** for the *prior disribution* (you already know what the maximum posterior will be)
>>      - *Closed-Form Expression* = finite number of standard operations
>>
>>
>>> Beta Distribution Posterior: 
>>> - Beta Prior * **Bernoulli** Likelihood = Beta Posterior
>>> - Beta Prior * **Binomial** Likelihood = Beta Posterior
>>> - Beta Prior * **Negative Binomial** Likelihood = Beta Posterior 
>>> - Beta Prior * **Geometric** Likelihood = Beta Posterior 
>> 
>>> Gamma Distribution Posterior: 
>>> - Gamma Prior * **Poisson** Likelihood = Gamma Posterior 
>>> - Gamma Prior * **Exponential** Likelihood = Gamma Posterior 
>>
>>> Normal Posterior: 
>>> - Normal Prior * **Normal** Likelihood (mean) = Normal Posterior 
