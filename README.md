# Treatment Effects: Regression Discontinuity, Double Lasso and Bootstrap

In this project, we will be looking into the topic of Casual Inference and how we can measure the effect of special covariate $d$ in an observational study leveraging techniques such as Double Lasso Regression and Regression Discontinuity. Although a completely randomized experiment is the gold standard for measuring the Treatment Effect(TE), we can also take some actions in an observational study to isolate the actual effect caused by the treatment covariate.

## Casual Inference

Today, we'll try to estimate the effect of a special covariate - Treatment $d$, which we can change independently from $x$. That is, we want to know the causal treatment effect (TE). For example,
* d = 1 if you get the drug, and d = 0 for the placebo (control).
* d is some policy tool, like interest rates or product price.

Our Treatment Effect Model Looks Like: 
$$\mathbb{E}[y|d,x]= \alpha + d\gamma + x'\beta $$

, and we want to interpret the treatment effect $\gamma$ casually. 

A coefficient is structural or casual if it represents a real-world effect i.e. $\gamma$ represents a change in $y$ when $d$ moves independent of any other influencers ( both in $x$ or those we have omitted). In contrast, a reduced model is a simple representation of the effect of $x$ on $y$, without worrying about causal mechanisms. 

## Randomized Control Trials: A/B Tests

* We want to know the effect of $d$ on $y$, that is independent of the change in $x$.
* A completely randomized design draws two random samples of units, then applies $d=0$ to one sample, and $d=1$ to the other.
* Treatment Effect is treatment mean minus control mean: $\hat{\gamma}=\overline{y_{b}} - \overline{y_{a}}$
* If you have the ability to randomize, it is very tough to find a Treatment Effect estimate that is much better than that of an experiment.

## Experimental vs Observational Study 

* Experimental Study: We can randomize for treatment
* Observational Study: We just observe what nature provides
* Casual TE inference requires you to control for all influences on $y$ over which you have not randomized( i.e. those which are correlated with $d$).
* Without an Experiment we haven't randomized over anything: with observational data, we need to control for 'everything'.

## How to Control for Confounders?

With $x$ in the regression model, inference for $\gamma$ is measured from the effect of the bit of $d$ that is not predictable by $x$. For example, say $d = x'\tau + \nu$, where $\nu$ is a random noise (residual). Then: 
$$\mathbb{E}[y|d,x]= d\gamma + x'\beta$$
$$ = (x'\tau + \nu)\gamma + x'\beta $$
$$ = \nu\gamma + x'(\gamma\tau + \beta)$$

