---
sort: 1
---

# Methods


source: `{{ page.path }}`


There are four popular molecular phylogenetic methods.

:link: The following is a summary of information from a number of resources, workshops and other bits I have come across during my data analysis learning. As with the rest of this webpage it is certainly not extensive and written in a context relevent to the work I do (i.e. parasite identification and a dabble in taxonomy and systematics).

* Australian National Postgraduate Training Workshop in Systematics support by the [Society of Australian Systematic Biologists](https://www.sasb.org.au), [The Australian Biological Resources Study](http://www.environment.gov.au/science/abrs) and [Australian Centre for Evolutionary Biology and Biodiversity](https://www.adelaide.edu.au/environment/acebb/)
* [Sydney Phylo Workshop](https://github.com/simon-ho/SydneyPhyloWorkshop) by Simon Ho.


## 1. Maximum parsimony

Identifies the tree topology that can explain the sequence data, using the smallest number of inferred substitution events. It is commonly used for morphological data, and now days is rarely used for analysing genetic data. It cannot estimate evolutionary rates or timescales and does not correct for multiple substitutions at the same site which leads to what is known as "long-branch attraction".

## 2. Distance-based methods

Clustering algorithms
  - Unweighted Pair Group Method with Arithmetic Mean (UPGMA)
  - Neighbour joining (NJ)

Tree searching using optimality criteria
  - Minimum evolution
  - Least-squares inference

*Pros*

  - Able to take into account multiple substitutions and long-branch attraction
  - Useful for analysing very large data sets with a lot of taxa (1000's +)

*Cons*

  - Does not use all information in alignment
  - Loss of information in pairwise comparisons
  - Unable to implement sophisticated evolutionary models

## 3. Maximum likelihood (ML)

  - Search through the space of possible trees and parameter values
  - Calculate the likelihood for these
  - Find best tree and model parameter values
  - Multivariate optimisation

*Pros*

  - Rigorous statistical method
  - Deals with multiple substitutions and long-branch attraction
  - Highly robust to violations of assumptions

*Cons*

  - Not feasible to implement very parameter-rich models
  - Searching tree space can be difficult

*ML Analysis*

* RAxML = Randomized Axelerated Maximum Likelihood. Rapid bootstrapping and can run sequentially or in parallel.
* PhyML
* MEGA
* PAML
* IQ-Tree

## 4. Bayesian inference

Bayesian phylogenetic analysis was developed in the mid 1990s, and it now  one of the most widely used methods for molecular phylogenetics.

Key features of Bayesian paradigm

  - Contrast with frequentist statistics (likelihood)
  - Parameters have distributions
  - Before the data are observed, each parameter has a prior distribution
  - The likelihood of the data is computed
  - The prior distribution is combined (updated) with the likelihood to yield the posterior distribution

*Priors*

  - Priors are chosen in the form of probability distributions
  - Reflect our prior expectations (and uncertainty) about values of parameters (without knowledge of the data)
      * Past observations
      * Personal beliefs
      * Use of a biological model
  - Uninformative priors

*'Prior options'*

1. Use a flat prior for tree topology (MrBayes)
    - All trees have equal probability
    - Also need a prior for branch lengths or node times

2. Use a biological model to generate prior distribution (BEAST and MrBayes)
    - Among species: speciation model
    - Within species: coalescent model

*Markov Chain Monte Carlo Sampling*

It is impossible to obtain the posterior directly.  Instead, the posterior can be estimated using Markov chain Monte Carlo simulation. This is usually done using the Metropolis-Hastings algorithm. There is a wealth of literature available for more information on this topic. It can get super technical - we've just covered the basics.

*Pros*

  - Able to implement highly parameterised models
  - Estimating tree uncertainty is straightforward
  - Can only do this indirectly in likelihood (via bootstrapping)
  - Posterior probabilities have an intuitive interpretation
  - Can incorporate independent information (in the prior)

*Popular software and programs for Bayesian analysis*

  - MrBayes
    * Primarily designed for species-level data
    * Simultaneous estimation of tree and node times
    * Range of clock models
    * Range of tree priors
    * Multiple chains and MCMC diagnostics

  - RevBayes
    * Uses its own R-like language, Rev
    * Interactive construction of graphical model
    * Flexible and can be used for simulation and inference
    * Ongoing development

  - BEAST1 = Bayesian Evolutionary Analysis by Sampling Trees
    * Analyse population- or species-level data
    * Simultaneous estimation of tree and node times
    * Range of clock models
    * Range of tree priors and demographic models

  - BEAST2
    * Re-write of BEAST to increase modularity
    * Users can extend BEAST by adding packages
    * Additional tree priors not available in BEAST 1
    * Capacity to perform simulations
    * For a comparison of BEAST 1 and 2: www.beast2.org/beast-features


## Bootstrapping

Felsenstein (1985) Evolution 39(4):783-791 ([Pub med](https://www.ncbi.nlm.nih.gov/pubmed/28561359))
Bootstrapping provides a confidence interval that contains the phylogeny that would be estimated from repeated sampling of many characters from the underlying set of all characters. Bootstrap values are measures of repeatability. High when the data set is large. Not meaningful when analysing genome-scale data.
