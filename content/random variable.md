---
title:
draft: false
tags:
---
 It is a function that maps elements from a state space to $\large \mathbb{R}$. Random variables are written with upper case letters such as X, Y or Z. It is possible to map two elements from the state space to the same output.

The output of a random variable can be in a finite or infinite range. In both cases, we have two types:
#### Discrete
We could count the output elements of the random variable. That is, there are no values in between one element and the next (e.g. $\large \mathbb{N}$).

![[randomvariable.svg]]

#### Continuos
The output elements could take any (infinite) values within a range (e.g. $\large \mathbb{R}$).

## Why use random variables?

- **Quantification:** They map qualitative outcomes (e.g. "Sunny") to real numbers ($\mathbb{R}$).

- **Simplification:** They allow us to ignore irrelevant details. If you only care about the _sum_ of two rolled dice, a random variable $X$ treats $(2,4)$ and $(3,3)$ as the same value ($6$), even though they are different states.

- **Functional Power:** Once outcomes are numbers, we can use better use mathematical tools to describe the system behavior.

Overall, I think one of the strongest reasons why random variables are so useful is because of their **abstraction** power. We can say "this process follows a [[Normal Distribution]]" without needing to know if the underlying states are heights of people, errors in a clock, or light particles. It provides a universal language for different phenomena.
