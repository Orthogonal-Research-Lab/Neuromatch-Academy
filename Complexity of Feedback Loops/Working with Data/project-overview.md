# Project Idea
Explore the complexities of feedback (e.g. sensorimotor) loops through the use of simulated agents exhibiting different degrees of representation (on a continuum from representation-free to representation-rich). Does an intelligent agent (or organism) require a minimal (or maximum) level of representational complexity (mapping between phenomena and neurons) to produce and act upon feedback? Implementation might include Bayesian models, agent-based models, or something as simple as a pendulum.

<p align="center">
  <img src="https://github.com/Orthogonal-Research-Lab/Neuromatch-Academy/blob/master/Epistemological%20Directory/Bayesian%20Thinking/Tutorial/Slide8.png"><BR>
</p>

### Scientific context 
 We also know that feedback plays a critical role in behavioral regulation, observed in a wide variety of systems: autonomic processes, movement, and social interaction. Using a variety of representational frameworks, how can we characterize this complexity? Does an intelligent agent (or organism) require a minimal level of representational complexity to produce and act upon feedback? 


### Specific question
What is the tradeoff between feedback and performance given representational models at different levels of complexity?

* starting from a zero representational model, what is the tradeoff agents (or organisms) make in terms of performance for a certain level of feedback complexity? 


Representation Type  |  Complexity   |  Function            | Signature                            |
---------------------|---------------|----------------------|--------------------------------------|
Switch               |  Zero-order   | Yes/No decision      | Does not act on prior information    |
Iterative            |  First-order  | Simple feedback      | Acts on immediate prior information  |
Reflexive            |  Higher-order | Integrative feedback | Acts on integration of information   |


#### Subquestions
How can you model top-down feedback in an artificial neural network? How do you model behavioral feedback with different degrees of complexity (e.g. first-order, nonlinear, etc)?

If we increase the degree of representation (mapping between behavioral outcomes or environmental objects and the brain), does this help make use of feedback more efficiently? 


### Data set
IBL Mouse Dataset: [description](https://data.internationalbrainlab.org/)

How to set up data: [Notebook](https://github.com/Orthogonal-Research-Lab/Neuromatch-Academy/blob/master/Complexity%20of%20Feedback%20Loops/how-to-set-up-data.ipynb)

Data set description: [video](https://www.youtube.com/watch?v=NofrFH8FRZU)


### Techniques
Pick one of three types of models: Bayesian model, Agent-based Model, or Reinforcement Learning.

* behavioral feedback is best represented with a Bayesian model or a Reinforcement Learning model. The idea is to pick a few simple representations (or hypotheses about what the brain is doing to process information) and see how they describe the data. 

* agent-based modeling can be used to look at the social component of this question. Agents in the same simulation can possess a heterogeneity of model types, and then can be evaluated at the population level. Are there specific fitness benefits or utilities for a simple representation? A complex representation? A zero-order representation? It will likely depend on the environment.
