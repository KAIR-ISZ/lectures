# Lab 5 - Using link functions to create generalized linear models

We consider the dataset from the lecture considering Airline accidents and deaths.
Now the dataset is provided in ```Airline_data.csv``` file and you can create your own model. This time you dont get a jupyter notebook to fill so create your own. 

During the lecture we have tried Poisson models with varying degrees of success. Our considered models were (assuming $y_i$ is the number of accidents in given year):
- $y_i\sim\mathrm{Poisson}(\lambda)$ that is one fixed $\lambda$ for all years i.e. number of accidents is random independent on year where it happens
-  $y_i\sim\mathrm{Poisson}(\theta n_i)$ where $n_i$ is the ammount of miles flown that year. 

We will now try to improve upon those models using new structures and parameters. Lets add an additional mean ammount of accidents i.e model with intercept $\lambda_i=\alpha+\theta n_i$. This might be problematic, as coefficient $\lambda$ has to be positive, without appropriate carefulness it could create errors in sampling. Typical approach is to use a *link function*, i.e. function that would transform domain of parameter to one that is applicable. For Poisson distributions it is popular to use logarithm:

$$\log \lambda_i=\alpha+\theta n_i$$

which translates to the following sampling statement

$$ y_i\sim\mathrm{Poisson}(\underbrace{\exp(\alpha+\theta n_i)}_{\lambda_i})$$

Create such model and perform prior predictive analysis to choose priors. 

**Important** chose priors wisely, as exponential function can become quite large and return errors in sampling when it becomes too big. Perhaps before sampling of Poisson try to find what kind of values for $\lambda_i$ come from priors. 

After testing priors fit the model to data and evaluate its efficiency by by posterior predictive distribution and comparing histograms of accidents for entire period and for each year.

Try to improve the model by replacing single intercept $\alpha$ with individual intercepts of $\alpha_i$ for each year. It can be easily done, by declaring $\alpha$ as an array of appropriate dimension. Then only one prior is needed as it will be used for all the elements of the array.

Again perform the prior predictive distribution analysis to select prior parameters, fit the model and analyze its output. 
