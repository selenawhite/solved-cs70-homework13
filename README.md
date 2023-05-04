Download Link: https://assignmentchef.com/product/solved-cs70-homework13
<br>
In this problem, we will consider Buffon’s Needle, but with a catch. We now drop a needle at random onto a large grid, and example of which is shown below.

The length of the needle is 1, and the space between the grid lines is 1 as well.

Recall from class that a random throw means that the position of the center of the needle and its orientation are independent and uniformly distributed.

<ul>

 <li>Given that the angle between the needle and the horizontal lines is <em>θ</em>, what is the probability that the needle does not intersect any grid lines? Justify your answer.</li>

 <li>Continue part (a) to find the probability that the needle, when dropped onto the grid at random (with the angle chosen uniformly at random), intersects a grid line. Justify your answer.</li>

</ul>

<em>Hint: </em>You may use the fact that sin<em>θ </em>cos<em>θ </em>=  sin(2<em>θ</em>) without proof.

<ul>

 <li>Let <em>X </em>be the number of times the needle intersects a gridline (so, in the example shown above, <em>X </em>= 2). Find E[<em>X</em>]. Justify your answer.</li>

</ul>

<em>Hint: </em>Can you do this without using your answer from part (b)?

<ul>

 <li>Combine the previous parts to figure out the probability that <em>X </em>= 1, i.e. the needle will only intersects one gridline. Justify your answer.</li>

 <li>We will fold the needle into an equilateral triangle, where each side is length . What is the expected number of intersections that this triangle will have with the gridlines, when dropped onto the grid? Justify your answer.</li>

</ul>

<h1>2          Variance of the Minimum of Uniform Random Variables</h1>

i.i.d.

Let <em>n </em>be a positive integer and let <em>X</em><sub>1</sub><em>,…,X<sub>n </sub></em>∼ Uniform[0<em>,</em>1]. Find var<em>Y</em>, where

<em>Y </em>:= min{<em>X</em><sub>1</sub><em>,…,X<sub>n</sub></em>}<em>.</em>

<em>Hint</em>: You may need to perform integration by parts.

<h1>3          Erasures, Bounds, and Probabilities</h1>

Alice is sending 1000 bits to Bob. The probability that a bit gets erased is <em>p</em>, and the erasure of each bit is independent of the others.

Alice is using a scheme that can tolerate up to one-fifth of the bits being erased. That is, as long as Bob receives at least 801 of the 1000 bits correctly, he can decode Alice’s message.

In other words, Bob becomes unable to decode Alice’s message only if 200 or more bits are erased. We call this a “communication breakdown”, and we want the probability of a communication breakdown to be at most 10<sup>−6</sup>.

<ol>

 <li>Use Markov’s inequality to upper bound <em>p </em>such that the probability of a communications breakdown is at most 10<sup>−6</sup>.</li>

 <li>Use Chebyshev’s inequality to upper bound <em>p </em>such that the probability of a communications breakdown is at most 10<sup>−6</sup>.</li>

 <li>As the CLT would suggest, approximate the fraction of erasures by a Gaussian random variable (with suitable mean and variance). Use this to find an approximate bound for <em>p </em>such that the probability of a communications breakdown is at most 10<sup>−6</sup>.</li>

</ol>

<h1>4          Sampling a Gaussian With Uniform</h1>

In this question, we will see one way to generate a normal random variable if we have access to a random number generator that outputs numbers between 0 and 1 uniformly at random.

As a general comment, remember that showing two random variables have the same CDF or PDF is sufficient for showing that they have the same distribution.

<ul>

 <li>First, let us see how to generate an exponential random variable with a uniform random variable. Let <em>U</em><sub>1 </sub>∼<em>Uniform</em>(0<em>,</em>1). Prove that −ln<em>U</em><sub>1 </sub>∼ <em>Expo</em>(1).</li>

 <li>Let <em>N</em><sub>1</sub><em>,N</em><sub>2 </sub>∼ <em>N </em>(0<em>,</em>1), where <em>N</em><sub>1 </sub>and <em>N</em><sub>2 </sub>are independent. Prove that <em>N</em>.</li>

</ul>

<em>Hint: </em>You may use the fact that over a region <em>R</em>, if we convert to polar coordinates (<em>x</em><em>,y</em>) → (<em>r</em><em>,θ</em>), then the double integral over the region <em>R </em>will be

ZZ    ZZ <em>f</em>(<em>x</em><em>,y</em>)<em>dxdy </em>=           <em>f</em>(<em>r</em>cos<em>θ</em><em>,r</em>sin<em>θ</em>)·<em>rdrdθ</em><em>.</em>

<em>R                                      R</em>

<ul>

 <li>Suppose we have two uniform random variables, <em>U</em><sub>1 </sub>and <em>U</em><sub>2</sub>. How would you transform these two random variables into a normal random variable with mean 0 and variance 1?</li>

</ul>

<em>Hint: </em>What part (b) tells us is that the point (<em>N</em><sub>1</sub><em>,N</em><sub>2</sub>) will have a distance from the origin that is distributed as the square root of an exponential distribution. Try to use<em>U</em><sub>1 </sub>to sample the radius, and then use <em>U</em><sub>2 </sub>to sample the angle.

<h1>5          Markov Chain Terminology</h1>

In this question, we will walk you through terms related to Markov chains.

<ol>

 <li>(Irreducibility) A Markov chain is irreducible if, starting from any state <em>i</em>, the chain can transition to any other state <em>j</em>, possibly in multiple steps.</li>

 <li>(Periodicity) <em>d</em>(<em>i</em>) := gcd{<em>n</em><em>&gt; </em>0 |<em>P<sup>n</sup></em>(<em>i</em><em>,i</em>)=P[<em>X<sub>n </sub></em>=<em>i</em>|<em>X</em><sub>0 </sub>=<em>i</em>]<em>&gt; </em>0}, <em>i</em>∈<em>X </em>. If <em>d</em>(<em>i</em>)= 1 ∀<em>i</em>∈<em>X </em>, then the Markov chain is aperiodic; otherwise it is periodic.</li>

 <li>(Matrix Representation) Define the transition probability matrix <em>P </em>by filling entry (<em>i</em><em>, j</em>) with probability <em>P</em>(<em>i</em><em>, j</em>).</li>

 <li>(Invariance) A distribution <em>π </em>is invariant for the transition probability matrix <em>P </em>if it satisfies the following balance equations: <em>π </em>= <em>πP</em>.</li>

</ol>

<em>a</em>

1−<em>b</em>1−<em>a</em>

<em>b</em>

<ul>

 <li>For what values of <em>a </em>and <em>b </em>is the above Markov chain irreducible? Reducible?</li>

 <li>For <em>a </em>= 1, <em>b </em>= 1, prove that the above Markov chain is periodic.</li>

 <li>For 0 <em>&lt; a </em><em>&lt; </em>1, 0 <em>&lt; b </em><em>&lt; </em>1, prove that the above Markov chain is aperiodic.</li>

 <li>Construct a transition probability matrix using the above Markov chain.</li>

 <li>Write down the balance equations for this Markov chain and solve them. Assume that the Markov chain is irreducible.</li>

</ul>

<h1>6          Analyze a Markov Chain</h1>

Consider the Markov chain <em>X</em>(<em>n</em>) with the state diagram shown below where <em>a</em><em>,b </em>∈ (0<em>,</em>1).

<em>a               b</em>

<em>1 – a </em>

<em>0   1 – b     1      1      2</em>

<ul>

 <li>Show that this Markov chain is aperiodic;</li>

 <li>Calculate P[<em>X</em>(1) = 1<em>,X</em>(2) = 0<em>,X</em>(3) = 0<em>,X</em>(4) = 1 | <em>X</em>(0) = 0];</li>

 <li>Calculate the invariant distribution;</li>

 <li>Let <em>T<sub>i </sub></em>= min{<em>n </em>≥ 0 | <em>X</em>(<em>n</em>) = <em>i</em>}, <em>T<sub>i </sub></em>is the number of steps until we transit to state <em>i </em>for the first time. Calculate E[<em>T</em><sub>2 </sub>| <em>X</em>(0) = 1].</li>

</ul>

<h1>7          Boba in a Straw</h1>

Imagine that Jonathan is drinking milk tea and he has a very short straw: it has enough room to fit two boba (see figure).

<table width="57">

 <tbody>

  <tr>

   <td width="57"></td>

  </tr>

  <tr>

   <td width="57"> </td>

  </tr>

 </tbody>

</table>

Figure 1: A straw with one boba currently inside. The straw only has enough room to fit two boba.

Here is a formal description of the drinking process: We model the straw as having two “components” (the top component and the bottom component). At any given time, a component can contain nothing, or one boba. As Jonathan drinks from the straw, the following happens every second:

<ol>

 <li>The contents of the top component enter Jonathan’s mouth.</li>

 <li>The contents of the bottom component move to the top component.</li>

 <li>With probability <em>p</em>, a new boba enters the bottom component; otherwise the bottom component is now empty.</li>

</ol>

Help Jonathan evaluate the consequences of his incessant drinking!

<ul>

 <li>At the very start, the straw starts off completely empty. What is the expected number of seconds that elapse before the straw is completely filled with boba for the first time? [Write down the equations; you do not have to solve them.]</li>

 <li>Consider a slight variant of the previous part: now the straw is narrower at the bottom than at the top. This affects the drinking speed: if either (i) a new boba is about to enter the bottom component or (ii) a boba from the bottom component is about to move to the top component, then the action takes two seconds. If both (i) and (ii) are about to happen, then the action takes three seconds. Otherwise, the action takes one second. Under these conditions, answer the previous part again. [Write down the equations; you do not have to solve them.]</li>

 <li>Jonathan was annoyed by the straw so he bought a fresh new straw (the straw is no longer narrow at the bottom). What is the long-run average rate of Jonathan’s calorie consumption? (Each boba is roughly 10 calories.)</li>

 <li>What is the long-run average number of boba which can be found inside the straw? [Maybe you should first think about the long-run distribution of the number of boba.]</li>

</ul>