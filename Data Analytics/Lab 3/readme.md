# Lab 3 - Prior and Posterior predictive distributions

The goal of this excercise is to create a binomial model, use prior predictive distributions to select a proper prior and then using posterior predictive distributions.

We will be considering a following case:

Typical effects of administering certain vaccine result in an allergic reaction in 20% cases on average. This is what we know a priori

We are testing a new vaccine, for which we performed a trial on 50 patients registering 7 allergic reactions. We want to verify what is the allergic reaction probability for new trial and what is the probability that it is lower than for normal vacine. We assume that each patient treatment is exchangeable. 

## Modeling prior predictive distribution

Because prior predictive distribution does not use data it can often be realized just using random number generators. 

1. Create a Stan model, which will consist of only ```generated quantites``` block.
2. In this block define integer variable ```N``` for number of trials equal to 50, integer variable ```y``` for number of successes and real ```p``` for probability of allergic reaction. Remember to use necessary constraints.
3. Assign a prior for  ```p``` (appropriate random number generator) that will represent our knowledge about typical cases. You can do it either analytically or by using simulations. 
4. Sample from binomial distribution, that will use ```N``` and sampled ```p``` to generate number of allergic reactions ```y```.
5. Generate 1000 samples (pair of ```p``` an ```y```) by calling appropriate method in ```cmdstanpy```. Remeber to set ```fixed_param=True```.
6. Compute ratio of allergic reactions for each sample and create a histogram.
7. Verify if mean of the ratio is consistent with prior knowledge, otherwise modify prior parameters. Describe your reasoning in the report. 

## Modeling posterior and posterior predictive distribution

1. Create a Stan model in which:
   - ```N``` and ```y``` are appropriately defined in the ```data``` block.
   - ```p``` is defined in the parameters block. 
   - binomial likelihood and prior (selected using prior predictive distribution) are defined in the model block.
   - new integer variable ```y_pred``` in the generated quantities block. 
   - sample ```y_pred``` using values of parameter ```p``` and input variable ```N```
2. Generate default number of samples from appropriate method in ```cmdstanpy```.
3. Compute ratio of predicted allergic reactions for each sample and create a histogram.
4. Compute the expected value and 94% density interval of the predicted ratio, compare it with expected value and 94% density interval of parameter ```p```. Use ```arviz``` package.
5. Compute the probability that ratio is lower than the average probability from traditional vaccines (count the number of simulated ratios that are smaller).


