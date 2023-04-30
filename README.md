Download Link: https://assignmentchef.com/product/solved-icsi401-homework-3-more-root-finding-and-related-topics
<br>
<h1>3.1         More root finding and related topics</h1>

<ul>

 <li>This question will test your understanding of the intermediate value theorem, which you will recall is the theorem that motivates bisection search.</li>

</ul>

Consider the following function <em>f</em>(<em>x</em>):

(3.1)

(This notation is standard and means that <em>f</em>(<em>x</em>) = <em>x </em>whenever <em>x &lt; </em>−1<em>/</em>2 and <em>f</em>(<em>x</em>) = <em>x </em>+ 2 whenever <em>x </em>&gt; −1<em>/</em>2.)

Note that <em>f</em>(<em>x</em>) is defined for every real <em>x</em>, but it has no roots. That is, there is no <em>x</em><sub>∗ </sub>such that <em>f</em>(<em>x</em><sub>∗</sub>) = 0. Nonetheless, we can find an interval [<em>a,b</em>] such that <em>f</em>(<em>a</em>) <em>&lt; </em>0 <em>&lt; f</em>(<em>b</em>): just choose <em>a </em>= −1<em>,b </em>= 1. Why can’t we use the intermediate value theorem to conclude that <em>f </em>has a zero in the interval [−1<em>,</em>1]?

<ul>

 <li>This question will test your understanding of the limitations of bisection search and Newton’s method. Consider the function.

  <ul>

   <li>Can we use bisection search to find one of its roots? Why or why not?</li>

   <li>Can we use Newton’s method to find one of its roots? Why or why not?</li>

  </ul></li>

</ul>

<h1>3.2        Fixed point iteration</h1>

<ul>

 <li>Complete problem 4.7.12 in the textbook. This will test your knowledge of what a fixed point of a function is, how to find them, and how to determine when iteration will converge to a fixed point.</li>

</ul>

3-1

3-2

<ul>

 <li><strong>Application question. Here’s how this works: You get full points for a reasonable attempt. So you MUST attempt this question. You get extra credit if you’re correct. </strong>This question presents a simple model of population dynamics, and analyzes its equilibrium states. Models like this, but more complicated, can be used to predict global population trends, for instance.</li>

</ul>

Let <em>N<sub>t </sub></em>denote the number of individuals in a population at time <em>t</em>. We will assume that <em>N<sub>t</sub></em>

<table width="588">

 <tbody>

  <tr>

   <td width="419">evolves at each time step according to the following equation:</td>

   <td width="168"> </td>

  </tr>

  <tr>

   <td width="419"><em>N<sub>t</sub></em><sub>+1 </sub>= <em>N<sub>t </sub></em>+ <em>rN<sub>t</sub></em>(1 − <em>N<sub>t</sub>/K</em>)<em>,</em></td>

   <td width="168">(3.2)</td>

  </tr>

 </tbody>

</table>

where

<ul>

 <li><em>r </em>is the birth minus death rate (per existing individual) parameter. Let us assume that it is larger than 0.</li>

 <li><em>K </em>is a positive constant representing fundamental resource limitations for the population. For example, on Earth, there is only a finite amount of of consumable biomass, and so the number of humans on Earth probably cannot grow to infinity. Note that when <em>N<sub>t </sub>&gt; K</em>, we have <em>N<sub>t</sub></em><sub>+1 </sub>− <em>N<sub>t </sub>&lt; </em></li>

</ul>

Supposing we start with some initial population <em>N</em><sub>0</sub>, we can calculate <em>N<sub>t </sub></em>as follows:

<ul>

 <li>Define <em>F</em>(<em>x</em>) = <em>x </em>+ <em>rx</em>(1 − <em>x/K</em>).</li>

 <li>Define <em>x </em>= <em>N</em><sub>0</sub>.</li>

 <li>Compute <em>N<sub>t </sub></em>= <em>F </em>◦ <em>F </em>◦ <em>… </em>◦ <em>F</em>(<em>x</em>), where <em>F </em>is applied <em>t </em></li>

</ul>

Now, we want to determine cases where this process converges. Suppose <em>r &gt; </em>0 and <em>K &gt; </em>0 are fixed.

<ul>

 <li><strong>Determine all non-negative values of </strong><em>x </em><strong>for which </strong><em>F </em><strong>is a contraction.</strong></li>

</ul>

Hints: Recall that we say that a function <em>F </em>is a contraction if its Lipschitz constant <em>L </em>is strictly less than 1. In other words:

|<em>F</em>(<em>z</em>) − <em>F</em>(<em>z</em><sup>0</sup>)| 6 <em>L </em>· |<em>z </em>− <em>z</em><sup>0</sup>|                                                        (3.3)

for all <em>z,z</em><sup>0 </sup>&gt; 0. Remember that you can get an upper bound on <em>L </em>by upper bounding |<em>F</em><sup>0</sup>(<em>z</em>)| for every <em>z</em>.

You should get an answer of the form “<em>x &gt; g</em>(<em>K</em>)” for some explicit function <em>g </em>that you have to determine.

<ul>

 <li>Suppose that <em>x </em>6 <em>K</em>. <strong>Show that </strong><em>F</em>(<em>x</em>) &gt; <em>x</em><strong>.</strong></li>

 <li>Suppose that <em>x &gt; K</em>. <strong>Show that </strong><em>F</em>(<em>x</em>) <em>&lt; x</em><strong>.</strong></li>

 <li>What we’ve shown, then, is that <em>F </em>is a contraction on the interval (<em>g</em>(<em>K</em>)<em>,</em>∞), and, furthermore, if we fix <em>any L &gt; g</em>(<em>K</em>), <em>U &gt; K &gt; L</em>, then <em>F </em>maps any value <em>y </em>∈ [<em>L,U</em>] to some value <em>F</em>(<em>y</em>) ∈ [<em>L,U</em>]. Thus, by Banach’s fixed point theorem, we can conclude that <em>F </em>has a unique fixed point <em>x</em><sub>∗ </sub>in the interval [<em>L,U</em>], and iterated application of <em>F </em>converges to <em>x</em><sub>∗</sub>. Here, <em>x</em><sub>∗ </sub>is the limiting population size!</li>

</ul>

Furthermore, since <em>K </em>is guaranteed to be in [<em>L,U</em>], we see that <em>x</em><sub>∗ </sub>= <em>K</em>. That is, if we start at <em>any </em>positive population size <em>&gt; g</em>(<em>K</em>), the population will eventually converge to <em>K </em>(in fact, with more work, one can show that this happens for any positive initial 3-3

population size). This makes intuitive sense: remember that <em>K </em>represents the resource constraints on the population, so this says that the population will converge to the capacity of its environment.

<strong>You don’t have to do anything for this bullet point. Just make sure that you understand it!</strong>

<h1>3.3         Condition numbers and algorithmic stability</h1>

Recall that the relative condition number <em>κ</em>(<em>x</em>) of a function <em>f</em>(<em>x</em>) is approximately the factor by which a relative error in the input gets magnified in the relative error in the output. I.e., if <em>x </em>is perturbed to ˆ<em>x</em>, then

<em>.                                                               </em>(3.4)

We gave a formula for <em>κ</em>(<em>x</em>) in class, and it also appears in the textbook.

<ul>

 <li>Qualitatively speaking, if the relative condition number of a function is large, does this make the function ill-conditioned, or well-conditioned (choose one)?</li>

 <li>Suppose that a problem has a very small condition number for a given input, but the relative error of the output of an algorithm for the problem is large. Is this the fault of the problem or of the algorithm (choose one)?</li>

 <li>Complete problem 6.3.5 on compound interest in the textbook, and make sure that you understand how they derived I<em><sub>n</sub></em>(<em>x</em>). Also, note that lim<em><sub>n</sub></em><sub>→∞ </sub>I<em><sub>n</sub></em>(<em>x</em>) = <em>e<sup>x</sup></em>.</li>

</ul>

For part (d), demonstrate your method in Matlab.

<h1>3.4        Some numerical linear algebra</h1>

<ul>

 <li>This problem will teach you how to work with the LU decomposition of a matrix programmatically to solve a linear system.</li>

</ul>

The Matlab function lu(A) returns [L, U, P], where <em>L </em>is a lower triangular matrix, <em>U </em>is an upper triangular matrix, and <em>P </em>is a permutation matrix, such that

<em>A </em>= <em>P<sup>T</sup>LU.                                                                              </em>(3.5)

Complete the following code to produce a solution to the equation <em>Ax </em>= <em>b</em>, <em>without multiplying the input matrices</em>.

function x = solve_with_LU(L, U, P, b)

%

% Given a lower triangular matrix L, an upper triangular matrix U,

% a permutation matrix P, and a vector b,

% return a solution to the equation P’LUx = b.

%

3-4

z = P’b y = %FILL THIS IN!

x = %FILL THIS IN! end

<ul>

 <li>In Matlab, compute the matrices <em>P</em>, <em>L</em>, and <em>U </em>from the LU decomposition of the matrix</li>

</ul>

(3.6)

and use the completed function above to obtain the solution to the system <em>Ax </em>= <em>b</em>, where

(3.7)

Please note that you have to turn in Matlab code for this question, including the completed version of the function above.