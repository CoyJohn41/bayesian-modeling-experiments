# Bayesian Modeling & MCMC

> Bayesian inference from prior to posterior — including a custom Metropolis-Hastings sampler built from scratch.

**Live Project Page:** [coyjohnson25.github.io/bayesian-modeling-experiments](https://coyjohnson25.github.io/bayesian-modeling-experiments)  
**Portfolio:** [coyjohnson25.github.io](https://coyjohnson25.github.io)

---

## Overview

Bayesian inference treats probability as a measure of belief, not just frequency. Instead of a single point estimate, it produces a full posterior distribution — capturing what we know, what we don't, and how both change as evidence accumulates. This project implements the full Bayesian pipeline from conjugate priors to a custom MCMC sampler, validated against PyMC.

---

## What's Inside

```
bayesian-modeling-experiments/
├── README.md
├── requirements.txt
├── notebooks/
│   ├── 01_conjugate_priors.ipynb    ← Beta-Binomial, Normal-Normal updates
│   ├── 02_mcmc_sampler.ipynb        ← Metropolis-Hastings from scratch
│   └── 03_prior_sensitivity.ipynb   ← How priors affect conclusions
├── src/
│   ├── conjugate.py                 ← Analytical posterior updates
│   ├── mcmc.py                      ← Metropolis-Hastings sampler
│   └── diagnostics.py               ← Trace plots, R-hat, autocorrelation
├── results/
│   ├── prior_posterior.png
│   ├── mcmc_trace.png
│   └── prior_sensitivity.png
└── docs/
    └── index.html                   ← Project detail page
```

---

## Modules Implemented

| Module | Description |
|--------|-------------|
| Conjugate Priors | Beta-Binomial, Normal-Normal, Gamma-Poisson exact updates |
| Metropolis-Hastings | Custom MCMC sampler with Gaussian random walk proposals |
| Convergence Diagnostics | Trace plots, autocorrelation functions, R-hat statistic |
| Prior Sensitivity | Posterior behavior under weak vs strong priors across sample sizes |

---

## Key Math

```
# Bayes' Theorem
p(θ | x) ∝ p(x | θ) · p(θ)
posterior ∝ likelihood × prior

# Beta-Binomial conjugate update
Prior:     θ ~ Beta(α, β)
Posterior: θ | x ~ Beta(α + x, β + n - x)

# Metropolis-Hastings acceptance ratio
A(θ*, θ) = min(1, p(θ*|x) / p(θ|x))
```

---

## Quickstart

```bash
git clone https://github.com/coyjohnson25/bayesian-modeling-experiments.git
cd bayesian-modeling-experiments
pip install -r requirements.txt
jupyter notebook notebooks/01_conjugate_priors.ipynb
```

---

## Results

- M-H sampler achieved ~24% acceptance rate (theoretically optimal)
- Posterior means matched PyMC NUTS output within 1%
- 95% credible intervals matched within 0.8 percentage points
- Prior sensitivity: with n > 100 observations, even a misspecified prior is overwhelmed by the likelihood

---

## Tech Stack

`Python` `NumPy` `SciPy` `Matplotlib` `PyMC` `Jupyter`

---

## Author

**Coy Johnson** — [coyjohnson25@gmail.com](mailto:coyjohnson25@gmail.com)  
M.S. Mathematics Candidate | Applied Mathematician# bayesian-modeling-experiments
