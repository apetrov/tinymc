# tinymc
Tiny version of MCMC sampler with tinygrad under the hood

Idea is to have a production version of MCMC sampler

### Do
* Output compatible with Arviz
* Syntax similar to PyMC
* Implement basic continues distributions (Normal, Beta, Exponential)
* Implement basic likelihoods (Bernoulli, Binominal, Normal)
* Deterministic variables
* Prior and Posterior predictive checks
* NUTS

### Don't
* Use first gen autograds like Theano
* Impelement anything other NUTS sampler
* Support Discrete Random Variables


```
import tinymc as mc

with mc.Model() as model:
   p = mc.Normal('p', mu=0, sd=5) # prior
   y = mc.Binomial('y', n=100, p=p, observed=30)
   
   idata = model.sample()
```
