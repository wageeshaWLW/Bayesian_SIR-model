Bayesian SIR Model

The Bayesian SIR (Susceptible-Infected-Removed) model with change points is an advanced epidemiological model designed to analyze and predict the spread of infectious diseases, such as COVID-19, while accounting for significant changes in transmission dynamics over time. This model incorporates Bayesian inference and change point detection to adapt to varying transmission and removal rates, providing a more flexible and accurate depiction of disease spread compared to traditional SIR models.
Key Components and Concepts

SIR Model: The standard SIR model divides a population into three compartments:
Susceptible (S): Individuals who can contract the disease.
Infected (I): Individuals who have contracted the disease and can spread it.
Removed (R): Individuals who have either recovered from the disease or died, and are no longer infectious.
Each individual is assumed to be in one state at ant time.
Assuming that in-person contacts among individuals follow the Erdos-Renyi model, The model is governed by a set of ordinary differential equations (ODEs) that describe the flow of individuals between these compartments:
𝑑𝑆(𝑡)𝑑𝑡=−𝛽𝑆(𝑡)𝐼(𝑡)/𝑁 
𝑑𝐼(𝑡)𝑑𝑡=𝛽𝑆(𝑡)𝐼(𝑡)/𝑁−𝛾𝐼(𝑡) 
𝑑𝑅(𝑡)𝑑𝑡=𝛾𝐼(𝑡) 
where:
β is the transmission rate.
γ is the removal rate.
( N ) is the total population size.
𝑑𝑆(𝑡)𝑑𝑡+𝑑𝐼(𝑡)𝑑𝑡+𝑑𝑅(𝑡)𝑑𝑡=0, 
For t>= 0, the population size is fixed as
𝑆(𝑡)+𝐼(𝑡)+𝑅(𝑡)=𝑁 
Change Points: In real-world scenarios, factors such as government interventions, behavioral changes, and seasonal effects can cause abrupt changes in the transmission and removal rates. The Bayesian SIR model with change points introduces a mechanism to detect these changes and adjust the model parameters accordingly.
Bayesian Inference: Bayesian inference is used to estimate the parameters of the model (e.g., transmission and removal rates) by updating the probability distributions of these parameters based on observed data. This approach allows for the incorporation of prior knowledge and the quantification of uncertainty in the parameter estimates.
Markov Chain Monte Carlo (MCMC) Algorithm: An MCMC algorithm is developed to sample from the posterior distributions of the model parameters. This algorithm iteratively updates the parameters based on the observed data, providing a comprehensive set of posterior samples that can be used for inference and prediction.
Stochastic SIR Model: The stochastic version of the SIR model accounts for randomness in the infection and removal processes. This model assumes that the numbers of newly infected and removed individuals follow binomial distributions:
Δ𝐼𝑡∼Binomial(𝑆𝑡−1,1−exp(−𝛽𝑡𝐼𝑡−1/𝑁)) 
Δ𝑅𝑡∼Binomial(𝐼𝑡−1,𝛾𝑡) 
𝑆𝑡=𝑆𝑡−1−Δ𝐼𝑡 
𝐼𝑡=𝐼𝑡−1+Δ𝐼𝑡−Δ𝑅𝑡 
𝑅𝑡=𝑅𝑡−1+Δ𝑅𝑡 
where
𝑃𝑡=𝐼𝑡/𝑁 
