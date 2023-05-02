Download Link: https://assignmentchef.com/product/solved-comp1012-lab8
<br>
<h1 id="material-covered">Material covered</h1>

<ul>

 <li>Random numbers</li>

 <li>Simulations</li>

</ul>

<h1 id="exercises">Exercises</h1>

<h2 id="question-1-required-estimating-the-volume-of-a-sphere">Question 1 (Required): Estimating the volume of a Sphere</h2>

A sphere with a radius of 1 (centered at point the point <span class="math inline">(0,0,0)</span>) is given by the equation <span class="math inline">1=x2+y2+z2</span>. <a href="http://mathworld.wolfram.com/UnitSphere.html" target="_blank" rel="noopener">Click here</a> if you want to see it visualized. This unit sphere has volume <span class="math inline">43π units3</span>. If you restrict this sphere to non-negative values of <span class="math inline">x,y,z</span>, then its volume is <span class="math inline">π6 units3</span> which is approximately <span class="math inline">0.524</span> (we got this by dividing <span class="math inline">43π</span> by <span class="math inline">8</span>). So if we were to generate a (uniformly) random point <span class="math inline">(x,y,z)</span> in the cube <span class="math inline">[0,1)×[0,1)×[0,1)</span>, the point should have about a 52.4 % probability of landing <em>inside</em> the sphere because the unit cube has volume 1. This means that we can approximate <span class="math inline">π</span> using the relative frequency of randomly generated points <span class="math inline">(x,y,z)</span> that lie in the sphere multiplied by 6.

You are going to write a script that will estimate <span class="math inline">π</span> by following the following steps:

<ol type="1">

 <li>Have a loop that runs <code>TRIALS</code> number of times, where <code>TRIALS</code> is the number of times we will generate points. For testing use 1,000,000 for <code>TRIALS</code>.</li>

 <li>Use <code>random.random()</code> to generate uniformly random values from the interval <span class="math inline">[0.0,1.0)</span>. Generate one for <span class="math inline">x</span>, one for <span class="math inline">y</span> and one for <span class="math inline">z</span>. This will be a give a random point <span class="math inline">(x,y,z)∈[0,1)×[0,1)×[0,1)</span>.</li>

 <li>With your random <span class="math inline">(x,y,z)</span> point, see if the points are within the sphere. The point <span class="math inline">(x,y,z)</span> are in the sphere if <span class="math inline">1&gt;x2+y2+z2</span></li>

 <li>Estimate <span class="math inline">π</span> with <span class="math inline">π=6×# points inside sphere# of trials</span>.</li>

</ol>

Print out your estimation of <span class="math inline">π</span>, and the number of trials you did to get there.

Example, created with seed of <code>1000</code>, your output should look like:

<pre><code>Estimating pi using (seed=1000)Number of trials: 1000000, estimation of pi: 3.133602</code></pre>

Now increase your trials. What happens? How many trials do we need to do before we are accurate to 2 decimal places? What about 3?

<h3 id="challenge-optional---automatic-precision">Challenge (optional) – automatic precision</h3>

Write a program that will automatically increase the number of trials until you get to a specific precision. That is, ask the users how many digits of precision are required, then run trials until you reach that level of precision and report the number of trials you needed to run.

<strong>Hint</strong>: You’ll need to take the <em>difference</em> of the real <span class="math inline">π</span> and the value you’re generating.

<h3 id="super-challenge-optional---fixed-point-arithmetic">Super challenge (optional) – fixed-point arithmetic</h3>

How many digits of precision until you <em>can’t</em> tell the difference between what Python knows about <span class="math inline">π</span> and the value you’re generating? Floating point numbers have limited precision on a computer. Python’s precision for integers is <em>unlimited</em>, and so at a certain level of precision you have to move from using floating point numbers to <a href="https://en.wikipedia.org/wiki/Fixed-point_arithmetic" target="_blank" rel="noopener"><em>fixed</em>-point arithmetic</a>.

Convert your program to calculate <span class="math inline">π</span> using <em>fixed</em>-point arithmetic.

<h2 id="question-2-required-rock-paper-scissors">Question 2 (Required): Rock, Paper, Scissors</h2>

Simulate a game of “Rock, Paper, Scissors”. If you are unfamiliar with the game, <a href="https://en.wikipedia.org/wiki/Rock%E2%80%93paper%E2%80%93scissors" target="_blank" rel="noopener">there is a good description on Wikipedia</a>. In general, both players randomly choose a signal from “rock”, “paper” and “scissors”. Rock beats scissors, scissors beats paper, paper beats rock. If both players choose the same signal, it is a “push”, and neither player wins.

You can simulate a player’s choices by choosing from a list, where each element of the list is a string that is either “rock”, “paper” or “scissors”. Use <a href="https://docs.python.org/3/library/random.html#random.choice" target="_blank" rel="noopener">random.choice</a> to randomly choose an element from the list of signals.

Create a simulation that runs 100 rounds of “Rock, Paper, Scissors” between two players named “Right” and “Left” (think about how to represent a player <strong>abstractly</strong> – what, minimally, do you need to represent this person?). Track how many times the right wins, how many times left wins, and how many pushes there are.

Using the seed 42, your result should be:

<pre><code>Simulating rock, paper, scissors (seed=42)Trials: 100, Left win %: 40.0, Right win %: 36.0, Push %: 24.0</code></pre>

How would the results change if left only ever uses rock?

<h3 id="challenge-optional---no-logic">Challenge (Optional) – No Logic</h3>

The previous problem used conditional statements extensively to determine the winner. You <em>can</em> write this problem in such a way that the winner is automatically determined using <em>dictionaries</em> and <strong>no</strong> conditional statements. Try rewriting the problem to use a dictionary of dictionaries to determine the winner of “Rock, Paper, Scissors”.

Only do this challenge if and when you have completed solving the problem with conditional statements.