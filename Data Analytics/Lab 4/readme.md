# Lab 4 - Linear models - modelling height of !Kung people

During the excercise, we will be covering design of model for heights of certain population of people.
Specific tasks are in the laboratory notebook, following there are specifications for the required models. 

<hr>

```height_1_ppc.stan```


Generated quantities model, that would sample $\mu$ from normal prior distribution. It is supposed to represent our general knowledge about heights of people so assign reasonable mean height and standard deviation of those values. Our measurement error is unknown, but reasonably it would be on average 15 cm, propose a distribution and parameters for prior of standard deviation $\sigma$. Finally sample measurement of ```height``` from normal distribution with previously sampled $\mu$ and $\sigma$. Use this model to select parameters for priors to provide reasonable spreads of heights. 

<hr>

```height_1_fit.stan```

Create a model for fitting model without predictors. 
For this purpose:

- specify ```data``` block with ```N``` samples, and input real array of size ```N``` called ```heights```
- specify ```parameters``` block with $\mu$ and $\sigma$ (set up appropriate types and constraints)
- in ```model``` block specify priors with appropriately selected parameters and normal likelihood using those parameters.
- in ```generated quantites``` block sample a single height consistent with the model.

<hr>

```height_2a_ppc.stan```

Modify the previous prior predictive check model by:
- adding ```data``` block with ```N``` samples, and input real array of size ```N``` called ```weight```
- new variable $\alpha$ for intercept with same prior as $\mu$ in previous model
- add a standard normal prior for predictor coefficient $\beta$
- create a size ```N``` real array called ```height``` and with a ```for``` loop fill it with normal samples with standard deviation $\sigma$ and mean $\alpha+\beta\cdot\mathrm{weight}[i]$

<hr>

```height_2b_ppc.stan```

Modify the previous prior predictive check model to use lognormal distribution for $\beta$.  

<hr>

```height_2_fit.stan```

Modify previous model for fitting, by:
- adding to ```data``` block an input real array of size ```N``` called ```weight```
- adding to ```parameters``` a new one - $\beta$
- create a new block ```transformed parameters``` where with a ```for``` loop a new real array parameter of size [N] is created with $\mu=\alpha+\beta\cdot\mathrm{weight}[i]$
- in ```model``` add the prior for $\beta$ and evaluate likelihood in a loop over all values of $\mu$ array.
- in ```generated quantites``` block sample ```N``` dimensional array height over all values of $\mu$ array.