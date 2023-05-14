# Data Analytics

Course for Automatic Control and Robotics, specialties:

- Cyber-physical Systems,
- Informatyka w Sterowaniu i Zarządzaniu

## Checklist for project Grading

Remebre, this is the report structure, it does not have to correspond to your actual workflow (for example, second model can be specified after finding what is missing in the first one). Remember in grading we are not looking at benchmarks, but are evaluating the tought process. Model can be performing *badly* as long as there were good reasons to try it in the first place. 

When grading each of criterions you have to **write** justification why the points were given. 

1. Problem formulation [0-5 pts]:
  - is the problem clearly stated [1 pt]
  - what is the point of creating model, are potential use cases defined [1 pt]
  - where do data comes from, what does it containt [1 pt]
  - DAG has been drawn [1 pt]
  - confoundings (pipe, fork, collider) were described [1 pt]
2. Data preprocessing [0-2 pts]:
  - is preprocessing step clearly described [1 pt]
  - reasoning and types of actions taken on the dataset have been described [1 pt]
3. Model [0-4 pts]
  - are two different models specified [1 pt] 
  - are difference between two models explained [1 pt]
  - is the difference in the models justified (e.g. does adding aditional parameter makes sense? ) [1 pt]
  - are models sufficiently described (what are formulas, what are parameters, what data are required ) [1 pt]
4. Priors [0-4 pts] 
  - Is it explained why particular priors for parameters were selected [1 pt]
  - Have prior predictive checks been done for parameters (are parameters simulated from priors make sense) [1 pt]
  - Have prior predictive checks been done for measurements (are measurements simulated from priors make sense) [1 pt]
  - How prior parameters were selected [1 pt] 
5. Posterior analysis (model 1) [0-4 pts] 
  - were there any issues with the sampling? if there were what kind of ideas for mitigation were used [1 pt]
  - are the samples from posterior predictive distribution analyzed [1 pt]
  - are the data consistent with posterior predictive samples and is it sufficiently commented (if they are not then is the justification provided)
  - have parameter marginal disrtibutions been analyzed (histograms of individual parametes plus summaries, are they diffuse or concentrated, what can we say about values) [1 pt]  
6. Posterior analysis (model 2) [0-4 pts] 
  - were there any issues with the sampling? if there were what kind of ideas for mitigation were used [1 pt]
  - are the samples from posterior predictive distribution analyzed [1 pt]
  - are the data consistent with posterior predictive samples and is it sufficiently commented (if they are not then is the justification provided)
  - have parameter marginal disrtibutions been analyzed (histograms of individual parametes plus summaries, are they diffuse or concentrated, what can we say about values) [1 pt]  
7. Model comaprison [0-4 pts]
  - Have models been compared using information criteria [1 pt]
  - Have result for WAIC been discussed (is there a clear winner, or is there an overlap, were there any warnings) [1 pt]
  - Have result for PSIS-LOO been discussed (is there a clear winner, or is there an overlap, were there any warnings) [1 pt]
  - Whas the model comparison discussed? Do authors agree with information criteria? Why in your opinion one model better than another [1 pt]

Total grade will be converted to percentage.



## Project specification

1. Form 2 person teams
1. Select a phenomena to model and find data for it.
2. Propose two models to represent the phenomena.
3. Perform prior analysis and selection.
4. Fit the models and analyze posterior predictive distributions - are they capturing the data. Repeat steps 3-5 if necessary.
5. Perform comparison of models with WAIC and LOO information criteria.
6. Report your findings (written report for grading, can be generated from jupyter + presentation for last classes).

Projects will be graded with a checklist. Each team will grade two randomly assigned teams. 
Final grade will be a weighted average of results (25%-25%-50% Team1-Team2-Teachers).


## Laboratory class requirements

It is recommended to use your own laptop computers.

Class work is realized in Python 3, in order to be able to work smoothly it is required (or at least strongly recommended) to install [Anaconda](https://www.anaconda.com/distribution/) and to ensure that you have up to date versions of following packages:

- [CmdStanPy](https://pystan.readthedocs.io/en/latest/) - installation requires bit of work or [CmdStanPy](https://cmdstanpy.readthedocs.io)
- [Arviz](https://arviz-devs.github.io/arviz/)
- [Matplotlib](https://matplotlib.org)
- [pandas](https://pandas.pydata.org)
- [NumPy](https://numpy.org)
- [SciPy](scipy)

During the course we will be using GitHub, where you will be submiting the results of excercises.

Recommended editor is VSCode with Stan extension.
