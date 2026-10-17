# Two Dice Done Rigorously: Sigma-Algebras, Pushforward Measures, Random Variables, and Why 7 Wins (Part 2 of 3)

*This is the second article in a three-part series. I highly recommend reading the first installment to have the context needed for this article: https://medium.com/@mckenzieben15/two-dice-done-rigorously-sigma-algebras-pushforward-measures-random-variables-and-why-7-wins-0379d5513631*

In this second installment, we will be examining the topics of measurable functions and random variables, show why textbooks say a random variable is a measurable function, and define our random variable for our dice rolls and sum experiment.

## Brief Recap
In the previous article, we went through the steps to formally define a probability space. We defined our sample space, our event space, and our probability measure. We learned that a probability space is a measure space i.e. it is a measurable space equipped with a measure, specifically our probability measure. We showed how the rules of a probability measure prevent any event from our event space from having a probability greater than 1.

## Picking up: Making a Function Explicit
We have an intuitive notion of what a function is, but for this article series we will need to make things explicit and rigid. A function takes the following form:
$$
X:A\rightarrow B,\ X(a\in A)=b\in B
$$
*figure 1*

to define a function we need:
- 1. The domain: our possible input values
- 2. The rule: what our function actually does (for example, adding two dice rolls together)
- The codomain: a set that is large enough to contain every possible output we think our function will produce
- The range: this is a subset of the codomain, and the result of actually applying our function to each element in the domain.