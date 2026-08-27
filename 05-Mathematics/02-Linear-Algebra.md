🧮 Mathematics for AI — Linear Algebra

Now we move to the first major topic:

Vectors

Since you're following 3Blue1Brown, focus on building the geometric intuition while I give you the mathematical depth and later the software connection.

1. What is a vector?

Don't think of a vector merely as:

$$ \begin{bmatrix}2\\3\end{bmatrix} $$

A better interpretation is:

A vector represents a direction and magnitude in a vector space.

For example,

$$ \mathbf v = \begin{bmatrix} 3\\ 2 \end{bmatrix} $$

can represent an arrow starting at the origin and ending at \((3,2)\).

Its magnitude is:

$$ \|\mathbf v\| = \sqrt{3^2+2^2} = \sqrt{13} $$
2. Vector vs Point

This distinction becomes important later.

A point represents a location:

$$ P=(3,2) $$

A vector represents displacement:

$$ \mathbf v=(3,2) $$

They can be represented using the same coordinates, but conceptually they are different.

If:

$$ A=(1,2),\qquad B=(4,5) $$

then the vector from \(A\) to \(B\) is:

$$ \overrightarrow{AB} = B-A = (4-1,5-2) $$

so:

$$ \boxed{\overrightarrow{AB}=(3,3)} $$
3. Vector addition

Suppose:

$$ \mathbf u= \begin{bmatrix} 2\\ 3 \end{bmatrix} $$

and

$$ \mathbf v= \begin{bmatrix} 4\\ 1 \end{bmatrix} $$

Then:

$$ \mathbf u+\mathbf v = \begin{bmatrix} 2+4\\ 3+1 \end{bmatrix} = \boxed{ \begin{bmatrix} 6\\ 4 \end{bmatrix}} $$

Geometrically, you can think of placing the second arrow at the end of the first.

This is the parallelogram rule.

4. Scalar multiplication

Take:

$$ \mathbf v= \begin{bmatrix} 2\\ 3 \end{bmatrix} $$

Multiply by \(3\):

$$ 3\mathbf v= \begin{bmatrix} 6\\ 9 \end{bmatrix} $$

The direction remains the same, but the magnitude becomes three times larger.

If we multiply by a negative number:

$$ -2\mathbf v= \begin{bmatrix} -4\\ -6 \end{bmatrix} $$

the direction reverses.

Linear Combination — Deep Understanding

Suppose we have two vectors:

$$ \vec u= \begin{bmatrix} 2\\ 1 \end{bmatrix}, \qquad \vec v= \begin{bmatrix} -1\\ 2 \end{bmatrix} $$

Now consider:

$$ \boxed{\vec w=3\vec u+2\vec v} $$

This is a linear combination of \(\vec u\) and \(\vec v\).

1. What does "combination" mean?

We are combining vectors.

We take some amount of \(\vec u\) and some amount of \(\vec v\).

Here:

$$ 3\vec u+2\vec v $$

means:

Take 3 copies/units of \(\vec u\), and 2 copies/units of \(\vec v\), then add them.

First:

$$ 3\vec u = 3 \begin{bmatrix} 2\\ 1 \end{bmatrix} = \begin{bmatrix} 6\\ 3 \end{bmatrix} $$

And:

$$ 2\vec v = 2 \begin{bmatrix} -1\\ 2 \end{bmatrix} = \begin{bmatrix} -2\\ 4 \end{bmatrix} $$

Now add:

$$ \vec w= \begin{bmatrix} 6\\ 3 \end{bmatrix} + \begin{bmatrix} -2\\ 4 \end{bmatrix} $$

Therefore:

$$ \boxed{ \vec w= \begin{bmatrix} 4\\ 7 \end{bmatrix}} $$

So we created a new vector from the original vectors.

2. Why is it called "linear"?

This is the important part.

A linear combination has the form:

$$ \boxed{ a_1\vec v_1+a_2\vec v_2+\cdots+a_n\vec v_n } $$

where:

$$ a_1,a_2,\ldots,a_n $$

are scalars.

The scalars are called coefficients.

For example:

$$ 5\vec u-3\vec v $$

has coefficients:

$$ 5,\;-3 $$

Notice what we don't have:

$$ \vec u^2 $$

or

$$ \vec u\vec v $$

or

$$ \sin(\vec u) $$

Those aren't linear combinations.

The vector itself appears only to the first power and is multiplied by scalar coefficients.

3. The coefficients are incredibly important

Consider:

$$ \vec w=a\vec u+b\vec v $$

Here, \(a\) and \(b\) control how much of each vector we use.

For our vectors:

$$ \vec u= \begin{bmatrix} 2\\1 \end{bmatrix}, \qquad \vec v= \begin{bmatrix} -1\\2 \end{bmatrix} $$

Try different coefficients.

Case 1
$$ a=1,\quad b=0 $$

Then:

$$ \vec w=\vec u $$

We get:

$$ \begin{bmatrix} 2\\1 \end{bmatrix} $$
Case 2
$$ a=0,\quad b=1 $$

Then:

$$ \vec w=\vec v $$

We get:

$$ \begin{bmatrix} -1\\2 \end{bmatrix} $$
Case 3
$$ a=2,\quad b=1 $$

Then:

$$ \vec w=2\vec u+\vec v $$ $$ = \begin{bmatrix} 4\\2 \end{bmatrix} + \begin{bmatrix} -1\\2 \end{bmatrix} = \begin{bmatrix} 3\\4 \end{bmatrix} $$
Case 4
$$ a=-1,\quad b=2 $$

Then:

$$ -\vec u+2\vec v $$ $$ = \begin{bmatrix} -2\\-1 \end{bmatrix} + \begin{bmatrix} -2\\4 \end{bmatrix} = \begin{bmatrix} -4\\3 \end{bmatrix} $$

So by changing \(a\) and \(b\), we're able to create different vectors.

4. Here's the big idea 🔥

Suppose I ask:

Can we create the vector \((10,5)\) using \(\vec u=(2,1)\) and \(\vec v=(-1,2)\)?

We need to find \(a,b\) such that:

$$ a \begin{bmatrix} 2\\1 \end{bmatrix} + b \begin{bmatrix} -1\\2 \end{bmatrix} = \begin{bmatrix} 10\\5 \end{bmatrix} $$

Expand:

$$ \begin{bmatrix} 2a-b\\ a+2b \end{bmatrix} = \begin{bmatrix} 10\\5 \end{bmatrix} $$

Therefore:

$$ 2a-b=10 $$

and

$$ a+2b=5 $$

Now we have a system of equations.

From the first:

$$ b=2a-10 $$

Substitute into the second:

$$ a+2(2a-10)=5 $$ $$ a+4a-20=5 $$ $$ 5a=25 $$ $$ a=5 $$

Then:

$$ b=2(5)-10=0 $$

So:

$$ \boxed{ 5\vec u+0\vec v= \begin{bmatrix} 10\\5 \end{bmatrix}} $$

Of course—that makes sense because:

$$ 5 \begin{bmatrix} 2\\1 \end{bmatrix} = \begin{bmatrix} 10\\5 \end{bmatrix} $$
5. Now the REALLY important question

What if I give you:

$$ \vec u= \begin{bmatrix} 1\\ 0 \end{bmatrix}, \qquad \vec v= \begin{bmatrix} 0\\ 1 \end{bmatrix} $$

Can you create:

$$ \begin{bmatrix} 17\\ -4 \end{bmatrix} $$

using a linear combination?

Absolutely.

We need:

$$ a \begin{bmatrix} 1\\0 \end{bmatrix} + b \begin{bmatrix} 0\\1 \end{bmatrix} = \begin{bmatrix} 17\\-4 \end{bmatrix} $$

which gives:

$$ \begin{bmatrix} a\\b \end{bmatrix} = \begin{bmatrix} 17\\-4 \end{bmatrix} $$

Therefore:

$$ \boxed{ 17\vec u-4\vec v= \begin{bmatrix} 17\\-4 \end{bmatrix}} $$

And here's the conceptual jump:

The two basis vectors \((1,0)\) and \((0,1)\) can generate every vector in \(\mathbb R^2\).

That brings us directly to span.

6. Linear combination → Span

This distinction is extremely important.

One particular combination
$$ 3\vec u+2\vec v $$

is a linear combination.

But if I say:

"Take every possible linear combination of \(\vec u\) and \(\vec v\)."

Then we're talking about their:

$$ \boxed{\text{span}} $$

Formally:

$$ \operatorname{span}(\vec u,\vec v) = \{a\vec u+b\vec v\mid a,b\in\mathbb R\} $$

Read this as:

The span is the set of every vector that can be produced by choosing any real \(a\) and \(b\).

This distinction should become automatic:

3u + 2v
   ↓
ONE linear combination

all possible au + bv
   ↓
SPAN

9. The AI connection 🔥

Now let's connect this to something you'll eventually use.

Imagine a dataset with three features:

$$ x_1=\text{age} $$ $$ x_2=\text{income} $$ $$ x_3=\text{experience} $$

A data point can be represented as:

$$ \mathbf x= \begin{bmatrix} 21\\ 50000\\ 2 \end{bmatrix} $$

But ML models don't simply "look at" these numbers.

They often construct weighted combinations:

$$ z=w_1x_1+w_2x_2+w_3x_3+b $$

For example:

$$ z=0.2x_1+0.00001x_2+0.5x_3+b $$

Look carefully:

$$ \boxed{ w_1x_1+w_2x_2+w_3x_3 } $$

is a linear combination of features.

This idea is foundational to:

Linear regression
Logistic regression
Neural networks
Linear transformations
Matrix multiplication
Deep learning

So the concept you're learning now isn't an isolated mathematical definition.

You are learning the mathematical language used to build ML models.

10. Linear combination as "coordinates"

Here's another beautiful way to think about it.

Suppose:

$$ \vec e_1= \begin{bmatrix} 1\\0 \end{bmatrix}, \qquad \vec e_2= \begin{bmatrix} 0\\1 \end{bmatrix} $$

Then:

$$ \begin{bmatrix} 7\\3 \end{bmatrix} = 7\vec e_1+3\vec e_2 $$

So the coordinates:

$$ (7,3) $$

are actually telling us:

Use 7 units of the first basis vector and 3 units of the second basis vector.

This is a much deeper interpretation of coordinates.

Coordinates are essentially coefficients in a linear combination relative to a chosen basis.

🔥 That's an important idea to take away.
---------------------------------------------------------------------------------------------------------------------------------------

Linear Algebra — Next Concept: Linear Independence

We have reached exactly the next step:

$$ \boxed{\text{Linear Combination} \rightarrow \text{Span} \rightarrow \text{Linear Independence}} $$


1. The central question

Suppose we have two vectors:

$$ \mathbf v_1= \begin{bmatrix} 1\\ 2 \end{bmatrix}, \qquad \mathbf v_2= \begin{bmatrix} 3\\ 1 \end{bmatrix} $$

We already know we can form linear combinations:

$$ a\mathbf v_1+b\mathbf v_2 $$

Now ask:

Does each vector provide a genuinely new direction?

This is the heart of linear independence.

2. First, understand dependence

Consider:

$$ \mathbf v_1= \begin{bmatrix} 1\\ 2 \end{bmatrix} $$

and

$$ \mathbf v_2= \begin{bmatrix} 2\\ 4 \end{bmatrix} $$

Notice:

$$ \mathbf v_2=2\mathbf v_1 $$

So \(\mathbf v_2\) isn't giving us a new direction.

Everything we can make using both:

$$ a\mathbf v_1+b\mathbf v_2 $$

becomes:

$$ a\mathbf v_1+b(2\mathbf v_1) $$ $$ =(a+2b)\mathbf v_1 $$

So effectively, we only have one direction.

The second vector is redundant.

Therefore:

$$ \boxed{\mathbf v_1,\mathbf v_2\text{ are linearly dependent}} $$
3. What does "independent" mean?

Now consider:

$$ \mathbf v_1= \begin{bmatrix} 1\\ 0 \end{bmatrix}, \qquad \mathbf v_2= \begin{bmatrix} 0\\ 1 \end{bmatrix} $$

Neither vector can be produced by scaling the other.

They give us two genuinely different directions.

So they are linearly independent.

But we need a mathematical definition that works for any number of vectors.

4. The formal definition ⭐⭐⭐⭐⭐

Vectors

$$ \mathbf v_1,\mathbf v_2,\ldots,\mathbf v_n $$

are linearly independent if the equation

$$ \boxed{ c_1\mathbf v_1+ c_2\mathbf v_2+ \cdots+ c_n\mathbf v_n = \mathbf 0 } $$

has only the trivial solution

$$ \boxed{ c_1=c_2=\cdots=c_n=0 } $$

This is the definition you should know precisely.

5. What is the "trivial solution"?

Suppose:

$$ c_1\mathbf v_1+c_2\mathbf v_2=\mathbf0 $$

One obvious solution is:

$$ c_1=0,\qquad c_2=0 $$

because:

$$ 0\mathbf v_1+0\mathbf v_2=\mathbf0 $$

That's called the trivial solution.

The important question is:

Is there another solution where at least one coefficient is non-zero?

If yes → dependent.

If no → independent.

6. Example: Proving dependence

Take:

$$ \mathbf v_1= \begin{bmatrix} 1\\ 2 \end{bmatrix}, \qquad \mathbf v_2= \begin{bmatrix} 2\\ 4 \end{bmatrix} $$

Set:

$$ c_1\mathbf v_1+c_2\mathbf v_2=\mathbf0 $$

Therefore:

$$ c_1 \begin{bmatrix} 1\\ 2 \end{bmatrix} + c_2 \begin{bmatrix} 2\\ 4 \end{bmatrix} = \begin{bmatrix} 0\\ 0 \end{bmatrix} $$

Component-wise:

$$ c_1+2c_2=0 $$

and

$$ 2c_1+4c_2=0 $$

The second equation is simply 2 times the first.

Take:

$$ c_2=1 $$

Then:

$$ c_1=-2 $$

So:

$$ -2\mathbf v_1+\mathbf v_2=\mathbf0 $$

We found a non-zero solution.

Therefore:

$$ \boxed{\text{Dependent}} $$
7. Example: Proving independence

Take:

$$ \mathbf v_1= \begin{bmatrix} 1\\ 0 \end{bmatrix}, \qquad \mathbf v_2= \begin{bmatrix} 0\\ 1 \end{bmatrix} $$

Start with:

$$ c_1\mathbf v_1+c_2\mathbf v_2=\mathbf0 $$

Then:

$$ c_1 \begin{bmatrix} 1\\0 \end{bmatrix} + c_2 \begin{bmatrix} 0\\1 \end{bmatrix} = \begin{bmatrix} 0\\0 \end{bmatrix} $$

Therefore:

$$ \begin{bmatrix} c_1\\ c_2 \end{bmatrix} = \begin{bmatrix} 0\\ 0 \end{bmatrix} $$

So:

$$ c_1=0,\qquad c_2=0 $$

There is no non-trivial solution.

Therefore:

v
1
	​

,v
2
	​

 are linearly independent
	​
13. Connection to AI 🔥

This concept becomes surprisingly important in machine learning.

Imagine a dataset has three features:

$$ x_1=\text{height} $$ $$ x_2=\text{height in centimeters} $$ $$ x_3=\text{weight} $$

Suppose:

$$ x_2=100x_1 $$

Then \(x_1\) and \(x_2\) contain essentially the same information.

They are linearly dependent.

This can create problems such as multicollinearity in linear models.

So linear independence isn't just abstract mathematics.

It helps us understand:

redundant features
dimensionality
feature representations
matrix rank
regression
neural-network computations

Later, we'll connect this to rank.
-----------------------------------------------------------------------------------------------------------------------------------------

Dimension

Since you've already studied this in 2nd-sem engineering maths, we'll focus on the deeper meaning, not just the textbook definition.

1. The basic definition

The dimension of a vector space is:

$$ \boxed{\text{the number of vectors in any basis of that space}} $$

For example:

$$ \mathbb R^2 $$

has the basis:

$$ \mathbf e_1= \begin{bmatrix}1\\0\end{bmatrix}, \qquad \mathbf e_2= \begin{bmatrix}0\\1\end{bmatrix} $$

There are 2 vectors.

Therefore:

$$ \boxed{\dim(\mathbb R^2)=2} $$

Similarly:

$$ \boxed{\dim(\mathbb R^3)=3} $$

and:

$$ \boxed{\dim(\mathbb R^n)=n} $$

That's the easy part.

The interesting question is:

4. Dimension means "number of independent directions"

This is the intuition I want you to remember.

A line

You need one independent direction:

$$ \mathbf v $$

Therefore:

$$ \boxed{\dim(\text{line})=1} $$
A plane

You need two independent directions:

$$ \mathbf v_1,\mathbf v_2 $$

Therefore:

$$ \boxed{\dim(\text{plane})=2} $$
Ordinary 3D space

You need three independent directions:

$$ \mathbf v_1,\mathbf v_2,\mathbf v_3 $$

Therefore:

$$ \boxed{\dim(R^3)=3} $$

So another useful interpretation is:

Dimension = number of independent directions needed to describe the space
	​
7. Dimension and redundancy 🔥

Suppose you have:

$$ v_1= \begin{bmatrix}1\\0\\0\end{bmatrix} $$ $$ v_2= \begin{bmatrix}0\\1\\0\end{bmatrix} $$ $$ v_3= \begin{bmatrix}1\\1\\0\end{bmatrix} $$

Notice:

$$ v_3=v_1+v_2 $$

So \(v_3\) is redundant.

The span is still only the \(xy\)-plane.

Therefore:

$$ \dim(\operatorname{span}(v_1,v_2,v_3))=2 $$

not 3.

This gives a powerful connection:

$$ \boxed{ \text{Dimension tells us how many independent directions actually exist.} } $$

8. AI connection 🔥🔥

Now imagine your dataset has 100 features.

You might initially say:

$$ x\in R^{100} $$

So it appears to be 100-dimensional.

But suppose many features are linear combinations of others.

For example:

$$ x_{10}=2x_1+3x_2 $$ $$ x_{20}=x_4-x_7 $$

and so on.

Then the data might actually lie inside a lower-dimensional subspace.

For example:

$$ \boxed{ 100\text{ features} \quad\rightarrow\quad 20\text{ independent directions} } $$

This is one of the fundamental ideas behind dimensionality reduction.

Later, when we study PCA, you'll see how mathematics can identify important lower-dimensional structure inside high-dimensional data.

-------------------------------------------------------------------------------------------------------------------------------------------
2. What is a basis?

A set of vectors is called a basis if:

Condition 1: They span the space

They can generate every vector.

Condition 2: They are linearly independent

No vector is redundant.

Therefore:

$$ \boxed{ \text{Basis} = \text{Span} + \text{Linear Independence} } $$

This is not a definition to memorize.

4. A non-standard basis

Basis does NOT mean only:

$$ (1,0),(0,1) $$

Take:

$$ \mathbf v_1= \begin{bmatrix} 1\\ 1 \end{bmatrix} $$ $$ \mathbf v_2= \begin{bmatrix} 1\\ -1 \end{bmatrix} $$

Are they independent?

Yes.

Can they span all of \(R^2\)?

Let's test.

Can we make:

$$ \begin{bmatrix} 4\\ 2 \end{bmatrix} $$

Need:

$$ a\mathbf v_1+b\mathbf v_2 = \begin{bmatrix} 4\\2 \end{bmatrix} $$

Therefore:

$$ a+b=4 $$ $$ a-b=2 $$

Adding:

$$ 2a=6 $$ $$ a=3 $$

Then:

$$ b=1 $$

Thus:

$$ 3\mathbf v_1+1\mathbf v_2 = \begin{bmatrix} 4\\2 \end{bmatrix} $$

So they span \(R^2\).

Hence:

v
1
	​

,v
2
	​

 also form a basis
	​
9. A very important theorem

In:

$$ R^2 $$

Any basis has:

$$ 2 $$

vectors.

In:

$$ R^3 $$

Any basis has:

$$ 3 $$

vectors.

In:

$$ R^n $$

Any basis has:

$$ n $$

vectors.

This leads directly to our next concept:

Dimension
