# Two Dice Done Rigorously: Sigma-Algebras, Pushforward Measures, Random Variables, and Why 7 Wins (Part 2 of 3)
![alt text](image.png)
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
R(X)&:=\{X(\omega):\omega\in\Omega\}\\
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
f^{-1}[B]=\{x\in X:f(x)\in B\}
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
B=&\{25\}\subseteq \mathbb{Z}.\ f^{-1}[B]=\{x\in \mathbb{Z}:f(x)\in B\}\\
&\text{so } f^{-1}[B]=\{-5, 5\}\\
C=&\{2, 16\}.\  f^-1[C]=\{x\in \mathbb{Z}:f(x)\in C\}\\
&\text{so }f^{-1}[C] = \{-4,4\}
\end{aligned}
$$
*figure 9*

An important note to make regarding figure 9 can be seen in the third preimage example. Since our domain and codomain are both integers, even though
$$
C=\{2,16\}
$$
there is no integer that can be squared to equal 2:
$$
\nexists\ i\in\mathbb{Z}:i^2=2
$$
That is why we don't include it in our preimage. Another way to look at this is:
$$
f^{-1}[\{2\}]=\emptyset
$$

## Measurable Functions

This section will cover what a measurable function is. We will start with the formal definition of measurable function and break it down.

$$
\text{Formally, we define a measurable function as follows: let } (X,\Sigma)\text{ and } (Y,T)\text{ be two measurable}\\
\text{spaces. A function, }f:X\rightarrow Y\text{ is said to be measurable if for every element of the sigma}\\
\text{algebra }T\text{, the preimage of that element under }f\text{ is contained in the sigma algebra }\Sigma.\\
\text{i.e. }f^{-1}[t]\in\Sigma, \forall t\in T
$$
*figure 10*

Don't worry if this seems complicated. Some break down will make things more apparent. First, note the fact that a measurable function is called a *measurable* function and as we learned from part 1 of this series, a *measurable space* is a set equipped with some sigma algebra. This gets us through the statement:
$$
``\text{let }(X,\Sigma)\text{ and }(Y,T)\text{ be two measurable spaces.}"
$$
*figure 10.1*

Next, we have:
$$
``\text{A function, }f: X\rightarrow Y\text{ is said to be measurable...}"
$$
*figure 10.2*

We know the rigid definition of function from this article. In figure 10.2 the portion "*is said to be measurable*" is what we are actively defining, so we don't need to dig deeper on this part.

The next part of the definition reads:
$$
``\text{if for every element of the sigma}
\text{ algebra }T\text{, the preimage of that}\\
\text{element under }f\text{ is contained in the sigma algebra }\Sigma."
$$
*figure 10.3*

We know what preimages are from this article. We also know that the elements of a sigma algebra are sets. So, Figure 10.3 is saying that we need every element contained in the destination's sigma algebra to have its preimage in the source's sigma algebra.

Finally, we simply state what we have above in mathematical symbols:

$$
``f^{-1}[t]\in\Sigma, \forall t\in T"
$$
*figure 10.4*

One thing to note about measurable functions here, we need the attached sigma algebras for the measurable functions to make sense. Since the sigma algebras are inherently tied to the measurable function, we include those in our notation. Using the same symbols as our formal definition in Figure 10, we would notate our measurable function as:
$$
f:(X,\Sigma)\rightarrow(Y,T)
$$
*figure 11*
## Measurable Functions (Visually)
The following image provides a visualization of a measurable function:

![alt text](Images/measurable_function/measurable_function_vis.png)
*Figure 12*

In this image we have the components of a measurable function. In white, we have our sigma algebras, the function between the two, and our preimage direction. The blue circles represent some part of our base sets. The red circles are the specific sets we are current mapping. The green dots are points in the sets we are currently mapping, and the orange dots simply represent points in our base sets. Finally, in red text we have the mathematical symbols for our image and preimage.
## The Random Variable
The reason we have gone through so much effort to define sigma algebras, probability spaces, and now measurable functions is to make the concept of the random variable easier to understand.

Recall from the previous article in this series that a probability space is the tuple:
$$
(\Omega,\mathcal{F},\mathcal{P})
$$
*Figure 13*

where we have:
$$
\begin{aligned}
&\Omega:\text{ The sample space}\\
&\mathcal{F}:\text{ The event space}\\
&\mathcal{P}:\text{ The probability measure}
\end{aligned}
$$
*figure 14*

**Here is where some care is needed.** Let’s start with the formal definition of a random variable (don’t worry, the point of this section is to demystify this):

$$
\begin{aligned}
&\text{Let }(\Omega, \mathcal{F}, \mathcal{P})\text{ be a probability space and }(E,\mathcal{E})\text{ a measurable space. Then, an}\\
&(E,\mathcal{E})-\textbf{valued random variable }\text{ is a measurable function }X:(\Omega,\mathcal{F})\rightarrow(E,\mathcal{E})
\end{aligned}
$$
*Figure 15*

First off, pat yourself on the back for getting this far! We already know what a measurable function is, so we can check that box. The next question is what the *measurable spaces* of both the domain and range are. We already have the domain covered from the first article in this series: *the domain of the random variable is the measurable space of our probability tuple.* All we need to do is drop our probability measure (for now), making a *measurable space*, and we have that covered. **So what is the range?**

The range of a random variable, in general, has two requirements:

1. The range of our random variable needs to be a *measurable space*. This requirement, on it’s own, is pretty easy to understand given what we learned from the previous article in this series: *a measurable space is a set, together with a sigma algebra.* If we examine the definition of random variables given in figure 15, the measurable space our random variable’s range has is:
$$
(E,\mathcal{E})
$$
*figure 16*

2. Since a random variable is a measurable function, we need to adhere to:
$$
\text{Formally, we define a measurable function as follows: let } (X,\Sigma)\text{ and } (Y,T)\text{ be two measurable}\\
\text{spaces. A function, }f:X\rightarrow Y\text{ is said to be measurable if for every element of the sigma}\\
\text{algebra }T\text{, the preimage of that element under }f\text{ is contained in the sigma algebra }\Sigma.\\
\text{i.e. }f^{-1}[t]\in\Sigma, \forall t\in T
$$
*Figure 10 (again)*

Tying this all together, our random variable allows us to go from the original probability space, to a new one. That new probability space is “induced” by our random variable. Right now, everything is abstract (all the symbols we’ve been using). We can make things concrete with our dice roll experiment.

## Making Our Random Variable Concrete (First Try)

Let's tie this back to our example. We roll two dice, making our sample space:
$$
\Omega=\{(i,j):i,j\in\{1,2,3,4,5,6\}\}
$$
*Figure 17*

We create the event space (which is also a sigma algebra) using the powerset operation:
$$
\mathcal{F}=2^\Omega
$$
*Figure 18*

This makes the domain of our random variable:
$$
(\Omega,\mathcal{F})
$$

Recall that we have three components in a "normal" function: the domain, the codomain, and the rule. Let's define each for the random variable specific to our dice roll experiment:
- Domain: the domain of our (nonmeasurable) function has been stated, it is the sample space, $\Omega$
- Rule: the rule here is we add the resulting values of two dice rolls. In mathematical symbols we can state our rule as $X((i,j))=i+j$
- Codomain: we can choose any set that is big enough, but an intuitive choice ends up being the natural numbers, since we only have positive whole numbers on the faces of the two dice, and we are simply adding them. That makes our codomain $\mathbb{N}$

With the points above, we can state the underlying "normal" function that our random variable will be built from as:
$$
X:\Omega\rightarrow\mathbb{N},\ X((i,j)\in\Omega)=i+j
$$
*Figure 19*

### A Snag: Sigma Algebra for Our Range
The final step in constructing our random variable is to make our "normal" function measurable. *We hit a bit of a snag here though.* In the section, **Picking up: Making a Function Explicit** we learned how to explicitly define functions. In the section **Preimages**, we learned about preimages, and got some examples. In the section **Measurable Functions** we learned what makes a function measurable. **The snag?** we haven't gone over how to construct our sigma algebra for the *range* space of our measurable function. To cover this topic completely would require an entire article series in its own right, but fortunately we don't need to, we can just take one little bit from this topic: **a sigma algebra generated by a function**

We start with a normal function (we know all about these now!):
$$
f:X\rightarrow Y
$$
Next, we construct *some* sigma algebra on the codomain, this is NOT necessarily the sigma algebra we will end up with. In this example, let's simply use the powerset (we learned in the first article that is always a sigma algebra):
$$
\mathcal{F}_{2^Y} = 2^Y
$$
We are almost done! We need the sigma algebra generated by our function now. We have to have some existing sigma algebra to carve this out of though, and that is why we used the powerset above. The sigma algebra generated by our function is:
$$
\sigma(f)=\{f^{-1}[S]:S\in\mathcal{F}_{2^Y}\}
$$
*Figure 20*

*"Okay... but we are trying to make a measurable function, why do we care about this sigma algebra we just made?"* We did this due to a very useful fact of sigma algebras generated by functions:

A function, $f:X\rightarrow Y$, is measurable with respect to a sigma algebra, $\Sigma$ on $X$, if and only if $\sigma(f)\subseteq\Sigma$

*Figure 21*

We are so close to being done! Hang in there, we only have one more section, and in this last section we get to apply everything we have learned in this article and the last. 

## Making Our Random Variable Concrete (actually though this time)
We have all the pieces we need now. Let's just put these lego blocks together!

The domain of our random variable:
$$
\begin{aligned}
&\Omega=\{(i,j):i,j\in\{1,2,3,4,5,6\}\}\text{ (our sample space)}\\
&\mathcal{F}=2^\Omega\text{ (our sigma algebra/event space)}\\
&(\Omega,\mathcal{F})\text{ (our measurable space)}
\end{aligned}
$$
*Figure 22.1*

Our underlying (currently non measurable) function:
$$
f_X:\Omega\rightarrow\mathbb{N},\ f_X((i,j)\in\Omega)=i+j
$$
*figure 22.2*

Our "big" sigma algebra for the range that we will carve out of:
$$
2^\mathbb{N}\ (\text{ just the powerset on }\mathbb{N})
$$
*figure 22.3*

**A random fun fact that is completely irrelevant, but I needed a brain break and I think trees are cool**: "The Pando 'aspen forest' in Utah is a single clonal organism made up of tens of thousands of stems, making it the largest tree in the U.S. by landmass and weight" It's just one giant tree, for real. There are other clonal trees in the world as well.

**Back to the maths**, generating a sigma algebra with our function:
$$
\sigma(f_X)=\{f_X^{-1}[S]:S\in2^\mathbb{N}\}
$$
*figure 22.4*

We need to check that our function generated sigma algebra is a subset of our event space. Since the sigma algebra generated by the function (figures 22.2 and 22.4) contains only those sets of natural numbers that can be a sum of two dice, and our domain sigma algebra is the event space of all possible sets of this nature, we know for a fact that the sigma algebra in figure 22.4 is a subset of the event space from figure 22.1. This gives us the condition we need to satisfy figure 21. 

With these facts, we can now formally state our random variable as the measurable function:
$$
X:(\Omega,2^\Omega)\rightarrow()
$$

todo: figure out what the inverse image of N is since I don't think we can have the range of our random variable be generated sigma algebra and N. N isn't a preimage of our underlying function (I think) since the domain is just the sample space
