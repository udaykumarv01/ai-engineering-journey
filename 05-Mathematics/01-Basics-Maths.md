1. Exponential Functions

The general exponential function is

$$ f(x)=a^x,\qquad a>0,\ a\neq1 $$

There are two fundamentally different cases.

Case 1: \(a>1\)

Example:

$$ f(x)=2^x $$

The function grows exponentially.

Case 2: \(0<a<1\)

Example:

$$ f(x)=\left(\frac12\right)^x=2^{-x} $$

The function decays exponentially.

Exponential growth and decay

Notice the important property:

$$ a^0=1 $$

So every valid exponential function passes through \((0,1)\).

2. Why \(e^x\) is special

The most important exponential function in AI is

$$ f(x)=e^x $$

where

$$ e\approx2.718281828... $$

The remarkable property is:

$$ \boxed{\frac{d}{dx}e^x=e^x} $$

The function is its own derivative.

That makes it extremely convenient in calculus, probability, optimization and machine learning.

For a general exponential:

$$ f(x)=a^x $$

we have

$$ \boxed{\frac{d}{dx}a^x=a^x\ln a} $$

because

$$ a^x=e^{x\ln a} $$

and applying the chain rule:

$$ \frac{d}{dx}e^{x\ln a} =e^{x\ln a}\ln a =a^x\ln a. $$

That is the kind of derivation I want you to understand—not simply memorize.

3. Exponential identities

These become extremely useful later.

Product
$$ a^x a^y=a^{x+y} $$
Quotient
$$ \frac{a^x}{a^y}=a^{x-y} $$
Power
$$ (a^x)^y=a^{xy} $$
Negative exponent
$$ a^{-x}=\frac1{a^x} $$
Fractional exponent
$$ a^{1/n}=\sqrt[n]{a} $$

Therefore:

$$ a^{m/n}=\sqrt[n]{a^m} $$

These identities aren't just algebra tricks. They are part of the structure that makes exponential models mathematically tractable.



4. Logarithm — the inverse of exponentiation

If

$$ a^x=y $$

then

$$ \boxed{\log_a y=x} $$

So exponentiation and logarithms are inverse operations:

$$ a^x\longleftrightarrow\log_a x $$

For example:

$$ 2^5=32 $$

therefore:

$$ \log_2(32)=5 $$
5. The most important logarithmic identities

These are worth knowing cold.

Product rule
$$ \boxed{\log_a(xy)=\log_a x+\log_a y} $$
Quotient rule
$$ \boxed{\log_a\left(\frac{x}{y}\right) =\log_a x-\log_a y} $$
Power rule
$$ \boxed{\log_a(x^r)=r\log_a x} $$

That third one is particularly important in ML.

For example:

$$ \log(x^5)=5\log x $$
6. Change of base

For any valid bases:

$$ \boxed{ \log_a x= \frac{\log_b x}{\log_b a} } $$

In particular:

$$ \boxed{ \log_a x= \frac{\ln x}{\ln a} } $$

This explains why Python can calculate:

import math

math.log(32, 2)

even though the natural logarithm is the fundamental implementation.

7. The graph of logarithm

The logarithm is the inverse of the exponential.

If

$$ y=e^x $$

then its inverse is

$$ y=\ln x. $$

Their graphs are reflections of each other about

$$ y=x. $$
Exponential and logarithmic functions

The curves y=e^x and y=ln(x) are inverse functions and are reflections across y=x.

0
6
12
18
24
-2
-1
0
1
2
3

For the logarithm itself, remember:

$$ \ln x $$

has:

domain: \(x>0\)
range: all real numbers
vertical asymptote: \(x=0\)
\(\ln 1=0\)
\(\ln e=1\)

The logarithm grows very slowly.

8. A deeper identity: \(e^{\ln x}=x\)

Because exponentiation and logarithms are inverse functions:

$$ \boxed{e^{\ln x}=x} $$

and

$$ \boxed{\ln(e^x)=x} $$

for their appropriate domains.

This identity becomes incredibly useful in differentiation.

9. Deriving the derivative of \(\ln x\)

We know:

$$ y=\ln x $$

Therefore:

$$ x=e^y $$

Differentiate both sides with respect to \(x\):

$$ 1=e^y\frac{dy}{dx} $$

But:

$$ e^y=x $$

Therefore:

$$ 1=x\frac{dy}{dx} $$

and hence:

$$ \boxed{\frac{d}{dx}\ln x=\frac1x} $$

This is much more valuable than memorizing the formula because now you understand where it comes from.

10. Why logs appear everywhere in AI

Here's where this becomes interesting.

Suppose we have probabilities:

$$ p_1,p_2,\ldots,p_n $$

and a likelihood:

$$ L=\prod_{i=1}^{n}p_i $$

Products can become extremely tiny.

Take logarithms:

$$ \ln L = \ln\left(\prod_{i=1}^{n}p_i\right) $$

Using the log-product identity:

$$ \boxed{ \ln L=\sum_{i=1}^{n}\ln p_i } $$

A difficult product becomes a much easier sum.

This is one of the fundamental reasons log-likelihood is used throughout machine learning and statistics.

12. Another beautiful connection: Softmax

Later, you'll encounter:

$$ \boxed{ P_i=\frac{e^{z_i}} {\sum_j e^{z_j}} } $$

This is the softmax function.

Why exponential?

Because \(e^{z_i}>0\), so every resulting probability is positive.

And because we divide by:

$$ \sum_j e^{z_j} $$

the probabilities sum to 1:

$$ \sum_iP_i=1. $$

So the exponential function you just learned is directly sitting inside one of the most important functions in modern ML and neural networks.

13. One more powerful property: log turns multiplication into addition

This is a major mathematical idea:

$$ \boxed{\log(ab)=\log a+\log b} $$

Therefore:

Multiplication
      ↓ log
Addition

and:

Exponentiation
      ↓ log
Multiplication

This transformation is incredibly useful in:

likelihood optimization
numerical stability
probability
information theory
ML loss functions
