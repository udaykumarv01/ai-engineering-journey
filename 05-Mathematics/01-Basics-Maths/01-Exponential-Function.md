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
