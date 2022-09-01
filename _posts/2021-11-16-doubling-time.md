---
toc: true
layout: post
title: Doubling Time
description: One rule of thumb to rule them all
categories: [markdown]
toc: false
tags: [science]
---

Suppose you have a process that can be described by exponential growth.
It could be anything: interests on an investment, the early phases of infection in a pandemic, whatever.

It is often convenient to have an idea how fast is the growth by answering the question:

> How long will it take for $x$ to double in size, given a growth of $n$% per year?

The rule of thumb I learned a while back is the following:

> Doubling time = $\displaystyle\frac{70}{n}$ (in years) 

Of course, the time unit could be anything you like, I'll deal here with years for simplicity's sake.
Specifically, let's answer the question:

> Israel has currently (2021) a population of 9.2 million, and a growth rate of 1.8% per year. How long will it take for the population to double, assuming a fixed growth rate?

The answer is about 39 years (70 divided by 1.8), but why?!

Let's call $x_0$ the population size now, and the growth rate $n$%.
After one year, the population will be

$$
x_1 = x_0 * \left( 1 + \frac{n}{100} \right) \tag{1}
$$


Assume that after $k$ years the population will be double, i.e.:

$$
x_k = x_0 * \left( 1 + \frac{n}{100} \right)^k = 2x_0. \tag{2}
$$

Cancelling $x_0$ we get

$$
\left( 1 + \frac{n}{100} \right)^k = 2. \tag{3}
$$

We now take the natural logarith of both sides:

$$
k\ln\left( 1 + \frac{n}{100} \right) = \ln(2). \tag{4}
$$

Note that we took $k$ out of the exponent and it now multiplies the logarithm on the left-hand side.
Multiplying both sides by 100 yields

$$
100k\ln\left( 1 + \frac{n}{100} \right) = 100\ln(2) \simeq 69.3. \tag{5}
$$

That surely explains the number 70 in the rule of thumb!
Because of the properties of logarithms, we put the number 100 as the exponent of the parenthesis:

$$
 k\ln\left( 1 + \frac{n}{100} \right)^{100} = 100\ln(2). \tag{6}
$$

We are very close to the end!
We now remind ourselves that we learned in Calculus the definition of the exponential function:

$$
\exp(x) = \lim_{m\rightarrow \infty} \left( 1 + \frac{x}{m} \right)^{m}. \tag{7}
$$

Because the number 100 is "quite big", we will approximate the parenthesis inside the logarithm with the exponential function, thus

$$
k\ln\exp(n) = 100\ln(2). \tag{8}
$$

The logarithm is the inverse function of the exponential, therefore

$$
kn = 100\ln(2). \tag{9}
$$

Finally, solving for $k$, we have

$$
k = \frac{100\ln(2)}{n} \simeq \frac{70}{n}. \tag{10}
$$

We have thus shown that the number of years $k$ it will take for Israel to double it's population is about $70/n = 70/1.8 = 38.88$ years!!

The exact number, without any approximations, would be

$$
k = \frac{\ln(2)}{\ln(1+n/100)}\simeq 38.85. \tag{11}
$$


{% include boxed-message.html  title="Conclusion" content="👍 Very impressive rule of thumb 👍" %}
