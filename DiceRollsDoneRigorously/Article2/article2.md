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

to define a function we need three things:
- 1. The domain: our possible input values
- 2. The rule: what our function actually does (for example, adding two dice rolls together)
- 3. The codomain: a set that is large enough to contain every possible output we think our function will produce

### Step 1: Identify Our Domain
In this experiment, we are adding the result of two dice rolls together. In our case, we want the domain of our function to be the sample space of our experiment:
$$
\Omega=\{(i,j):i,j\in\{1,2,3,4,5,6\}\}
$$
*figure 2*
### Step 2: Identify our Rule
The rule is what we want our function to do to elements in our domain. Since we are adding the result of rolling two dice together, our rule is then:
$$
X((i,j))=i+j
$$
*figure 3*
### Step 3: Identify our Codomain
We need a set that is large enough to contain the result of applying our rule from step 2 to every element in our domain. In this case, we know that adding two natural numbers together will result in a natural number. This means using the set of natural numbers will definitely contain all the possible outputs of our rule from step 2. Our codomain can then be stated as:
$$
\mathbb{N}
$$

One note here: we only require that the codomain is big enough. The natural numbers are an intuitive choice here, but it is equally valid to select the integers, rational numbers, real numbers, or even the set of complex numbers.
### The Range of a Function
We have the codomain of our function, but it is often useful to determine the *range* of our function. The range of a function is the set of possible values that the function can take. The range is a subset of the codomain. We obtain the range by applying our rule to every element of our domain. Using the following symbol for an element of our domain:
$$
\omega=(i,j)\in\Omega
$$
*figure 4*

We can define our range as:
$$
\begin{aligned}
R(X)&:=\{X(\omega),\ \forall\omega\in\Omega\}\\
R(X)&=\{2,3,4,5,6,7,8,9,10,11,12\}\\
&\text{Note that } R(X)\subseteq \mathbb{N}
\end{aligned}
$$
*figure 5*
### Tying it together
With the 3 steps above concluded, we can tie everything together and formally state our function as:
$$
X:\Omega\rightarrow \mathbb{N},\ X((i,j)\in \Omega)=i+j
$$
*figure 6*

with the range of our function described in figure 5.

That was quite a bit for the start of an article! But, defining these things rigidly will help in the following sections, and allow us to gain a deep understanding of what a random variable is.
## Preimages
To move forward with this process, we need to learn about measurable functions. At a high level, a measurable function is simple: *a measurable function from one measurable space to another measurable space that preserves the structures of the two spaces.* This definition is incomplete, and not very helpful for understanding measurable functions. We need to dig deeper.


First, we need to define a concept known as the “preimage” of a set given a function:
$$
\text{Let } f:X\rightarrow Y \text{ be a function from the set }X \text{ to the set }Y.\\ \text{ The preimage of a subset of }Y,B\subseteq Y, \text{ is the set: }\\
f^{-1}[B]=\{x\in X:f(x)\in Y\}
$$
*figure 7*

An example might make this easier to understand. First, let's define a function in the manner that we have described above:
$$
\begin{aligned}
\text{Let }f:\mathbb{Z}\rightarrow\mathbb{Z},\text{ where }f(x\in\mathbb{Z})=x^2
\end{aligned}
$$
*figure 8*

We can compute some preimages as follows:
$$
\begin{aligned}
A=&\{4, 9\}\subseteq\mathbb{Z}.\ f^-1[A]=\{x\in\mathbb{Z}:f(x)\in A\}\\
&\text{so } f^{-1}[A]=\{-2, 2, -3, 3\}\\
B=&\{25\}\subseteq Z.\ f^-1[B]=\{x\in Z:f(x)\in B\}\\
&\text{so } f^{-1}[B]=\{-5, 5\}
\end{aligned}
$$

