---
title:
draft: false
tags:
---
Related: [[Bayes Theorem]]

Probability can be used as a mathematical tool to obtain insights about the behavior of something.
### Environment
This _something_ is our environment, system, or however you'd like to call it. For instance, sometimes we work with dice, cards, people, the weather...

Even for the same entity like people, in some problems we may be interested in their height and others in the number of siblings. So rather than focusing on the entity itself, focus on the particular characteristic we are studying.
### Experiments
Depending on the problem at hand, what an _experiment_ is varies. In common dice problems, carrying out an experiment might be equivalent to rolling the dice once. For card problems it could be selecting a card from the deck. For some problems involving people, sampling a person from the population. And so on.

When we carry out many experiments, we get a sequence of events. Sometimes we can produce as many as we want (e.g. roll the die again). And sometimes, new events follow some intrinsic time step (e.g. the daily weather, where you can only get new events when you wait for the following day).
### State Space
At any given time step, our environment may only be at a specific state from it's [[state space]].
### Random Variables
Carrying out an experiment results in a state. However, often we prefer to map this outcomes to specific numerical values (e.g. "sunny" -> 0, "snowy" -> 1). To do so, we can define a function called a [[random variable]].
### Probability function
Our environment has some underlying model that governs how probable each state $\large s \in S$ is of occurring when we carry out an experiment. For example, each of the six states of a perfect six sided die would have a $\large 1/6$ probability of happening if we roll the die.

The mathematical expression that represents the probability of a specific value of a random variable is:
$$\large
P(x_i) = P(X = x_i)
$$
That is, $\large P(x_i)$ represents the probability of our random variable $\large X$ resulting in the value $\large x_i$ after carrying out one experiment.

At first, we might not know these values. We could try to approximate them by experimentation. For instance, we throw the dice once. It lands on a "5". To our knowledge, we would think $\large P(5) = 1$ and $\large 0$ for the rest. As we keep throwing the dice and calculating the [[relative frequency]] of each state, by the [[law of large numbers]] we will get closer to the actual real probability for each state. This is defined in the following expression, where $\large n$ is the number of experiments we do, and $\large n_{x_i}$ is the number of experiments that resulted in $\large x_i$:
$$\large
P(x_i) = \lim_{n \to \infty} \frac{n_{x_i}}{n}
$$

Let us define some other important axioms fundamental to the field of probability:

$$\large
\large P(x_i) >= 0
$$
$$\large
\large \sum\limits_{i \in S} P(x_i) = 1
$$
This means that the probability of any event taking place can not be negative, that the probability of a certain event taking place is one, and the sum of the probability of all possible values of our random variable must sum up to one.

> [!EXAMPLE]-
> Say our random variable takes values only from states {sunny, rainy}. If we know the probability of sunny is 0.7, then rainy **must** be 0.3 (since 0.7 + 0.3 = 1), as no other states are possible and our environment must take any of the available states during an experiment.
> Decreasing or increasing the probability of sunny will thus then have an impact on the probability of rainy.

### Probability Distributions
There are several ways that we can express the behavior of our system:
###### Probability Mass Functions and Probability Density Functions
We can represent in a graph the possible resulting values of our random variable, and their respective probabilities. The resulting graph is called a [[PMF]] (for discrete random variables) or a [[PDF]] (for continuos random variables).
###### Cumulative Distribution Functions
We can also express the probability of the value of our random variable to be lower or equal to some value $\large x$. The resulting function is called a [[CDF]].