# Mathematica Class Demonstrations

A large collection of _Mathematica_ demonstrations written by Adam Rumpf, sorted according to the class that they are most likely to be useful for.

## Table of Contents

* [Overview](#overview)
* [Calculus, Differential Equations, and Analysis](#calculus-differential-equations-and-analysis)
  * [Complex Newton's Method](#complex-newtons-method)
* [Number Theory](#number-theory)
  * [Recamán's Sequence](#recamáns-sequence)

## Overview

This repository contains a large collection of _Mathematica_ notebook files written during my time as a graduate student at Illinois Institute of Technology between 2014 and 2019, although I intend to add more over time. I originally started these projects as a way to teach myself _Mathematica_ for use as a calculus teaching assistant, but eventually started making demonstrations for topics of personal interest or for use in my own classes.

Some of these projects have been uploaded to the [_Wolfram Demonstrations Project_](http://demonstrations.wolfram.com/). My creator page can be found at http://demonstrations.wolfram.com/author.html?author=Adam+Rumpf.

Most of these files are meant to be used by evaluating the entire notebook and then interacting with the resulting Manipulate environments or other functions. All of the individual notebook files are completely standalone and meant to be downloaded à la carte depending on your interests.

In order to download just a single file, navigate to its section below and click on the **Notebook** link. The `.nb` file can then be downloaded by right clicking the **Raw** link. Alternatively, you can find the file in the directories in this repository.

## Calculus, Differential Equations, and Analysis

Many of the files in this folder are things that I wrote to show my calculus students, either demonstrating material from class or demonstrating material from later classes that indirectly involve the concepts from basic calculus. This includes a variety of material related to fractals, dynamical systems, computational mathematics, and complex analysis.

### Complex Newton's Method

<img src="images/complex-newtons-method-1.png" alt="Complex Newton's Method Image 1" width="300"/> <img src="images/complex-newtons-method-2.png" alt="Complex Newton's Method Image 2" width="300"/>

[Notebook](../master/calc-diffeq-analysis/complex-newtons-method.nb)

2/23/2016

This is a demonstration of how [Newton's Method](https://en.wikipedia.org/wiki/Newton%27s_method) works for complex-valued functions. Most Calculus students will learn about Newton's Method for finding roots of real-valued functions, and may be surprised to learn that it also works for complex numbers. They may also learn that the method does not necessarily always converge to the root nearest the initial guess due to "overshooting" in unexpected ways. For real numbers this phenomenon is not very interesting to look at, but for the complex numbers we can generate fascinating and beautiful fractal basins of attraction.

The main function of this demonstration allows the user to specify a function and a few other parameters, and outputs a coloring of a portion of the complex plane demonstrating the basins of attraction of the different roots. Note that this may take a while to calculate for some large cases with many nodes. For this reason I would not recommend running the entire notebook, but rather running the initialization code and then evaluating one function at a time.

## Number Theory

Most of the files in this folder are related to interesting number sequences which give rise to interesting graphics.

### Recamán's Sequence

<img src="images/recaman-1.png" alt="Recamán's Sequence Image 1" width="300"/> <img src="images/recaman-2.png" alt="Recamán's Sequence Image 2" width="300"/>

[Notebook](../master/number-theory/recamans-sequence.nb)

8/25/2018

Recamán's Sequence (sequence [A005132](https://oeis.org/A005132) in the [OEIS](oeis.org)) is defined by an iterative process beginning at _0_, at step _n=0_. In step _n_, we either take _n_ steps backward or _n_ steps forward. We go backward if doing so would take us to a nonnegative number that has not yet been visited, and otherwise we go forward. It is conjectured that this sequence includes every nonnegative integer exactly once.

This program is mostly meant for drawing pictures of Recamán's Sequence. Because each step is _1_ unit larger than the preceding step, the most common way to draw it is using semicircular arcs to trace the path of the sequence on the number line. Doing so leads to interesting spiral patterns that illustrate the phases of rapid increase and of repeatedly bouncing back and forth to fill in areas that were previously unexplored.

## Just for Fun

The files in this folder were simply made out of personal interest. Many of them are not serious attempts to demonstrate any mathematical concept, and are instead just made to solve an interesting puzzle or generate an interesting figure. I have still shown a few to my students, however, as demonstration of some things that can be done in _Mathematica_.
