# Treatment Effects: Regression Discontinuity, Double Lasso and Bootstrap

In this project, we will be looking into the topic of Casual Inference and how we can measure the effect of special covariate $d$ in an observational study leveraging techniques such as Double Lasso Regression and Regression Discontinuity. 

## Casual Inference

Today, we'll try to estimate the effect of a special covariate - Treatment $d$, which we can change independently from $x$. That is, we want to know the causal treatment effect (TE). For example,
* d = 1 if you get the drug, and d = 0 for the placebo (control).
* d is some policy tool, like interest rates or product price.

Our Treatment Effect Model Looks Like: 
$$\mathbb{E}[y|d,x]= \alpha + d\gamma + x'\beta $$

, and we want to interpret the treatment effect $\gamma$ casually. 

A coefficient is structural or casual if it represents a real-world effect i.e. $\gamma$ represents a change in $y$ when $d$ moves independent of any other influencers ( both in $x$ or those we have omitted). In contrast, a reduced model is a simple representation of the effect of $x$ on $y$, without worrying about causal mechanisms. 



