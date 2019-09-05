# Mathematica Class Demonstrations

A large collection of _Mathematica_ demonstrations written by Adam Rumpf, sorted according to the class that they are most likely to be useful for.

## Table of Contents

* [Overview](#overview)
* [Calculus, Differential Equations, and Analysis](#calculus-differential-equations-and-analysis)
  * [Complex Newton's Method](#complex-newtons-method)
* [Number Theory](#number-theory)
  * [Recamán's Sequence](#recamáns-sequence)
  * [Remainder Graphs](#remainder-graphs)
* [Just for Fun](#just-for-fun)
  * [Domino and Tromino Tiling](#domino-and-tromino-tiling)
  * [Dragon Curve](#dragon-curve)
  * [Spirograph](#spirograph)

## Overview

This repository contains a large collection of _Mathematica_ notebook files written during my time as a graduate student at Illinois Institute of Technology between 2014 and 2019, although I intend to add more over time. I originally started these projects as a way to teach myself _Mathematica_ for use as a calculus teaching assistant, but eventually started making demonstrations for topics of personal interest or for use in my own classes.

Some of these projects have been uploaded to the [_Wolfram Demonstrations Project_](http://demonstrations.wolfram.com/). My creator page can be found at http://demonstrations.wolfram.com/author.html?author=Adam+Rumpf.

Most of these files are meant to be used by evaluating the entire notebook and then interacting with the resulting Manipulate environments or other functions. All of the individual notebook files are completely standalone and meant to be downloaded à la carte depending on your interests.

In order to download just a single file, navigate to its section below and click on the **Notebook** link. The `.nb` file can then be downloaded by right clicking the **Raw** link. Alternatively, you can find the file in the directories in this repository.

## Calculus, Differential Equations, and Analysis

Many of the files in this folder are things that I wrote to show my calculus students, either demonstrating material from class or demonstrating material from later classes that indirectly involve the concepts from basic calculus. This includes a variety of material related to fractals, dynamical systems, computational mathematics, and complex analysis.

### Complex Newton's Method

<img src="images/complex-newtons-method-1.png" alt="Complex Newton's Method Image 1" width="300"/> <img src="images/complex-newtons-method-2.png" alt="Complex Newton's Method Image 2" width="300"/>

Created 2/23/2016

[Notebook Link](../master/calc-diffeq-analysis/complex-newtons-method.nb)

This is a demonstration of how [Newton's Method](https://en.wikipedia.org/wiki/Newton%27s_method) works for complex-valued functions. Most Calculus students will learn about Newton's Method for finding roots of real-valued functions, and may be surprised to learn that it also works for complex numbers. They may also learn that the method does not necessarily always converge to the root nearest the initial guess due to "overshooting" in unexpected ways. For real numbers this phenomenon is not very interesting to look at, but for the complex numbers we can generate fascinating and beautiful fractal basins of attraction.

The main function of this demonstration allows the user to specify a function and a few other parameters, and outputs a coloring of a portion of the complex plane demonstrating the basins of attraction of the different roots. Note that this may take a while to calculate for some large cases with many nodes. For this reason I would not recommend running the entire notebook, but rather running the initialization code and then evaluating one function at a time.

## Number Theory

Number theory is not really my area, so most of the files in this folder are related to number sequences which give rise to interesting graphics that anybody can appreciate.

### Recamán's Sequence

<img src="images/recaman-1.png" alt="Recamán's Sequence Image 1" width="300"/> <img src="images/recaman-2.png" alt="Recamán's Sequence Image 2" width="300"/>

Created 8/25/2018

[Notebook Link](../master/number-theory/recamans-sequence.nb)

Recamán's Sequence (sequence [A005132](https://oeis.org/A005132) in the [OEIS](oeis.org)) is defined by an iterative process beginning at _0_, at step _n=0_. In step _n_, we either take _n_ steps backward or _n_ steps forward. We go backward if doing so would take us to a nonnegative number that has not yet been visited, and otherwise we go forward. It is conjectured that this sequence includes every nonnegative integer exactly once.

This program is mostly meant for drawing pictures of Recamán's Sequence. Because each step is _1_ unit larger than the preceding step, the most common way to draw it is using semicircular arcs to trace the path of the sequence on the number line. Doing so leads to interesting spiral patterns that illustrate the phases of rapid increase and of repeatedly bouncing back and forth to fill in areas that were previously unexplored.

### Remainder Graphs

<img src="images/remainder-graph-1.png" alt="Remainder Graph Image 1" height="300"/>

Created 10/10/2017

[Notebook Link](../master/number-theory/remainder-graph.nb)

[Demonstration Link](http://demonstrations.wolfram.com/AnimatedRemainderGraph/)

I was inspired to write this program by an [article](https://mindyourdecisions.com/blog/2015/07/26/divisibility-by-7-test-using-a-graph-why-does-it-work-sunday-puzzle/) by Presh Talwalkar. It demonstrates a cool trick for determining remainders after dividing a large number by a small number. Because this also allows calculating remainders of 0, this also encompasses the topic of divisibility tests. Testing for divisibility by 7 is famously tricky compared to the other small numbers, but this graphical method gives a fairly easy solution.

As an example, suppose we wish to know whether 42,959 is divisible by 7. The process begins by writing the numbers 0, 1, ..., 6 in a circle and connecting them in a cycle with black arrows. Next, for each of these numbers, we multiply it by 10 and then evaluate the remainder after division by 7, and draw a green arrow from the original number to the result. For example, for 2, we multiply by 10 to get 20, then divide by 7 to get 14 with remainder 6, which means that we should draw an arrow from 2 to 6. At the end of the process we will have 7 black arrows and 7 green arrows.

With this graph in place, we begin at position 0 and then read the digits of 42,959 from left to right. Each time we read a digit, we advance around the black circuit that number of steps. Between each digit, we follow the green arrow that leads out of the current position. In this case, we begin at 0 and read the first digit, "4". Then we advance 4 places to position 4, and then follow the green arrow to position 5. The next digit is "2", so we advance 2 to arrive at 0, and then follow the green arrow to remain at 0. Next we take "9" steps to 2, follow the green arrow to 6, advance "5" digits to 4, follow the green arrow to 5, and finally advance "9" digits to arrive back at 0. The final position is the remainder after division by 7. In this case it is 0, indicating that 42,959 is, indeed, divisible by 7.

The reasons for why this method works are worth figuring out for oneself (see the article linked above). It also generalizes to any base besides 7, and doing so produces some interesting graphical representations of why the well-known divisibility tests that students learn in basic arithmetic work. For example, the graphs resulting from 2, 5, and 10 all have the property that every green arrow points to 0, indicating that, no matter where the black arrows take us, we will always reset our position to 0 between steps. As a result, only the final digit matters, which is exactly what students learn for 2, 5, and 10. The graphs resulting from 3 and 9 both have the property that every green arrow is a loop, making them essentially meaningless. As a result, only the total number of steps taken on the black arrows (which is the sum of all digits) matters, and that is exactly what students learn for 3 and 9. 11 is also rather interesting.

## Just for Fun

The files in this folder were simply made out of personal interest. Many of them are not serious attempts to demonstrate any mathematical concept, and are instead just made to solve an interesting puzzle or generate an interesting figure. I have still shown a few to my students, however, as demonstration of some things that can be done in _Mathematica_.

### Domino and Tromino Tiling

<img src="images/domino-tiling-1.png" alt="Domino Tiling Image 1" width="300"/> <img src="images/tromino-tiling-1.png" alt="Tromino Tiling Image 1" width="300"/>

Created 10/16/2017

[Notebook Link](../master/fun/domino-tromino-tiling.nb)

[Demonstration Link](http://demonstrations.wolfram.com/DominoAndTriominoTilingsOfAChessboard/)

This file combines two related puzzles that involve tiling a chess board. The main purpose of the puzzles is to figure out for yourself whether tilings exist under certain circumstances, and how you could go about finding these tilings. The tromino puzzle, in particular, is often used as an introduction to proof by induction. This program makes use of the puzzles' solutions to compute tilings and display the results.

**Domino Puzzle:** Consider the problem of attempting to tile a chess board with dominos, each of which covers two adjacent squares. The goal is to cover the entire chess board with no gaps, no overlap, and nothing hanging over the edges. Obviously this can be done since the dominos can be laid out in rows like bricks.

What if we remove some squares from the chess board? If we just remove one square then the tiling is obviously impossible. A chess board contains 64 squares, so removing 1 leaves 63, and there is no way to cover an odd number of total squares if each domino covers exactly two squares. What if we remove two squares? That leaves 62, which is even and thus not immediately ruled out. To make things simple, suppose we remove the opposite corners of the chess board. Can it be tiled with dominos? What pairs of squares could be removed while still allowing a domino tiling?

**Tromino Puzzle:** Consider the problem of attempting to tile a chess board with L-shaped _trominos_, each of which covers _three_ adjacent squares. This is impossible on a standard chess board because 64 is not divisible by 3.

What if we remove a single square from the board? Then we would have 63 squares, which is divisible by 3, and thus might be possible. Suppose, for simplicity, that we remove a corner from the board. Can it be tiled with trominos? What squares could be removed while still allowing a tromino tiling?

### Dragon Curve

<img src="images/dragon-curve-1.png" alt="Dragon Curve Image 1" height="300"/>

Created 5/6/2016

[Notebook Link](../master/fun/dragon-curve.nb)

The [dragon curve](https://en.wikipedia.org/wiki/Dragon_curve) is my favorite fractal, and considering how much I love fractals that is really saying something. Like all fractals it looks cool and has some interesting properties, like being self-similar and tileable and being two-dimensional in the limit despite each finite iteration being one-dimensional. However, unlike many fractals it is fairly simple to approximate in real life, and the final shape is completely unexpected based only on the first few iterations.

One of the several equivalent constructions of the dragon curve involves taking a thin strip of paper and folding it in half, end-to-end, several times (the number of folds corresponds to the generation number). Then unfold the paper, open each crease to form a 90 degree angle, and look at the edge of the strip. The first fold simply creates an "L" shape. Starting over and adding a second fold creates a roughly "?" shape. Including additional folds one-at-a-time and observing the resulting curve produces shapes that are not very interesting, but after around 6 or 7 folds the shape begins to become incredibly intricate and complex.

This Notebook defines a function that applies a recursive algorithm to draw a specified generation of dragon curve. Due to the recursive nature, the computational time increases exponentially as the generation number increases, so I would not recommend trying to draw anything past approximately 18 generations. I would also not recomment running the entire notebook at once, and instead running only specific blocks one-at-a-time.

### Spirograph

<img src="images/spirograph-1.png" alt="Spirograph Image 1" width="150"/> <img src="images/spirograph-2.png" alt="Spirograph Image 2" width="150"/>
<img src="images/spirograph-3.png" alt="Spirograph Image 3" width="150"/> <img src="images/spirograph-4.png" alt="Spirograph Image 4" width="150"/>

Created 10/27/2016

[Notebook Link](../master/fun/spirograph.nb)

This is an interactive version of a [Spirograph](https://en.wikipedia.org/wiki/Spirograph) which displays the path of a pen attached to a disk rolling around a larger disk. There are controls to adjust the relative sizes of the disks, whether the small disk is inside or outside the larger disk, and where the pen is positioned (even allowing it to be outside of the disk). There is also a feature that displays a disk rolling on its edge around in circles.

This was originally written while teaching Calculus, which is when many students are introduced to the concept of polar and parametric coordinates. Part of the course material mentions [epicycloids](https://en.wikipedia.org/wiki/Epicycloid) and [hypocycloids](https://en.wikipedia.org/wiki/Hypocycloid), both of which are interesting in their own right and both of which show up in nature in some unexpected places, but I thought that it would be more impactful to show how they can all be generalized using this type of rolling mechanism.
