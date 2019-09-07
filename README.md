﻿# Mathematica Class Demonstrations

A large collection of _Mathematica_ demonstrations written by Adam Rumpf, sorted according to the class that they are most likely to be useful for.

## Table of Contents

* [Overview](#overview)
* [Calculus, Differential Equations, and Analysis](#calculus-differential-equations-and-analysis)
  * [Complex Newton's Method](#complex-newtons-method)
  * [Complex Operations](#complex-operations)
  * [Crowd Escape Panic Model](#crowd-escape-panic-model)
  * [Monte Carlo Method](#monte-carlo-method)
  * [Taylor and Fourier Series Approximations](#taylor-and-fourier-series-approximations)
  * [Vector Kinematics](#vector-kinematics)
* [Number Theory](#number-theory)
  * [Pascal's Triangle Fractals](#pascals-triangle-fractals)
  * [Recamán's Sequence](#recamáns-sequence)
  * [Remainder Graphs](#remainder-graphs)
* [Graph Theory](#graph-theory)
  * [Dijkstra's Algorithm and A* Search](#dijkstras-algorithm-and-a-search)
  * [Graph Untangler](#graph-untangler)
* [Just for Fun](#just-for-fun)
  * [Bézier Curves](#bézier-curves)
  * [Domino and Tromino Tiling](#domino-and-tromino-tiling)
  * [Dragon Curve](#dragon-curve)
  * [Fractal Shoulder Angels and Devils](#fractal-shoulder-angels-and-devils)
  * [Pythagoras Tree](#pythagoras-tree)
  * [Spirograph](#spirograph)

## Overview

This repository contains a large collection of _Mathematica_ notebook files written during my time as a graduate student at Illinois Institute of Technology between 2014 and 2019, although I intend to add more over time. I originally started these projects as a way to teach myself _Mathematica_ for use as a calculus teaching assistant, but eventually started making demonstrations for topics of personal interest or for use in my own classes.

Some of these projects have been uploaded to the [_Wolfram Demonstrations Project_](http://demonstrations.wolfram.com/). My creator page can be found at http://demonstrations.wolfram.com/author.html?author=Adam+Rumpf.

Most of these files are meant to be used by evaluating the entire notebook and then interacting with the resulting Manipulate environments or other functions. All of the individual notebook files are completely standalone and meant to be downloaded à la carte depending on your interests.

In order to download just a single file, navigate to its section below and click on the **Notebook** link. The `.nb` file can then be downloaded by right clicking the **Raw** link. Alternatively, you can find the file in the directories in this repository.

## Calculus, Differential Equations, and Analysis

Many of the files in this folder are things that I wrote to show my calculus students, either demonstrating material from class or demonstrating material from later classes that indirectly involve the concepts from basic calculus. This includes a variety of material related to fractals, dynamical systems, computational mathematics, and complex analysis.

### Complex Newton's Method

<img src="images/complex-newtons-method-1.png" alt="Complex Newton's Method Image 1" height="300"/> <img src="images/complex-newtons-method-2.png" alt="Complex Newton's Method Image 2" height="300"/>

Created 2/23/2016

[Notebook Link](../master/calc-diffeq-analysis/complex-newtons-method.nb)

This is a demonstration of how [Newton's Method](https://en.wikipedia.org/wiki/Newton%27s_method) works for complex-valued functions. Most Calculus students will learn about Newton's Method for finding roots of real-valued functions, and may be surprised to learn that it also works for complex numbers. They may also learn that the method does not necessarily always converge to the root nearest the initial guess due to "overshooting" in unexpected ways. For real numbers this phenomenon is not very interesting to look at, but for the complex numbers we can generate fascinating and beautiful fractal basins of attraction.

The main function of this demonstration allows the user to specify a function and a few other parameters, and outputs a coloring of a portion of the complex plane demonstrating the basins of attraction of the different roots. Note that this may take a while to calculate for some large cases with many nodes. For this reason I would not recommend running the entire notebook, but rather running the initialization code and then evaluating one function at a time.

### Complex Operations

<img src="images/complex-operations-1.png" alt="Complex Operations Image 1" height="300"/> <img src="images/complex-operations-2.png" alt="Complex Operations Image 2" height="300"/>

Created 3/20/2017

[Notebook Link](../master/calc-diffeq-analysis/complex-operations.nb)

This is a lightweight visual demonstration of how familiar mathematical operations (addition, multiplication, trigonometric functions, etc.) affect the complex numbers, displayed as vectors in the complex plane. The user can select an operation or function and then click and drag the input vector or vectors to see how this affects the output vector. In particular, it is interesting to look at how changing just the magnitude or just the angle of an input vector affects the output.

### Crowd Escape Panic Model

<img src="images/crowd-escape-panic-1.png" alt="Crowd Fluid Dynamics Image 1" height="200"/> <img src="images/crowd-escape-panic-2.png" alt="Crowd Fluid Dynamics Image 2" height="200"/>

Created 5/1/2018

[Notebook Link](../master/calc-diffeq-analysis/crowd-escape-panic.nb)

This is an interactive version of a model described in the following 2000 [article](https://www.nature.com/articles/35035023):

> D. Helbing, I. Farkas, and T. Vicsek. Simulating dynamical features of escape panic. _Nature_, 407:487-490, 2000.

The article describes a dynamical systems model for crowds of people attempting to run to a building exit during a panic. The model is similar to those used in fluid dynamics. Each person is treated as a particle with a certain radius. Each particle attempts to move toward the exit, but they also repel each other if they get too close (incredibly strongly if they are within crush distance of each other). For each particle we can define a total force function that includes its own desired movement, repulsion from other particles and obstacles, body forces from intersecting particles and obstacles, and sliding friction past particles and obstacles. The total force can then be used to define the particle's acceleration vector, which in turn defines a system of ordinary differential equations to determine each particle's position as a function of time.

This demonstration implements the model and displays an animation of the crowd as it tries to reach the exit. Controls allow the user to change the layout of the room, including obstacles and the size of the exit. Particles are colored according to the amount of crush force experienced from the surrounding particles, becoming more red as the force increases. A plot is also displayed in the corner of the animation, with the green line indicating the number of successful exits and the red line indicating the total crush force.

### Monte Carlo Method

<img src="images/monte-carlo-method-1.png" alt="Monte Carlo Method Image 1" height="200"/> <img src="images/monte-carlo-method-2.png" alt="Monte Carlo Method Image 2" height="200"/>

Created 9/13/2016

[Notebook Link](../master/calc-diffeq-analysis/monte-carlo-method.nb)

[Monte Carlo methods](https://en.wikipedia.org/wiki/Monte_Carlo_method) are a type of computational method for numerical integration based on random experiments. If the goal is to calculate the area within a particular curve, then a Monte Carlo method consists of randomly sampling points within a region of known area that surrounds the region of interest. In expectation, the ratio of points within the region of interest to points outside of the region of interest should equal the ratio of the two regions' areas, and because the surrounding region's area is known, this ratio can be used to calculate the unknown region's area. Due to the random nature of the experiment the ratio will not be exact, and may vary between realizations, but as the number of sample points increases the ratio should converge to the correct value.

This Notebook includes a visual demonstration of the Monte Carlo method applied to calculating two separate areas: the area under an arbitrary curve, and the area of a unit circle (which should be exactly π, making this method a way to numerically approximate π). For each experiment, the user can select how many points to randomly sample. Running and re-running the command should produce slightly different results due to the randomness. There are also functions to plot the approximation error as the number of sample points increases, to show how it generally decreases as the number of iterations increases.

### Taylor and Fourier Series Approximations

<img src="images/taylor-series-1.png" alt="Taylor Series Image 1" height="300"/> <img src="images/fourier-series-1.png" alt="Fourier Series Image 1" height="300"/>

Created 11/6/2017

[Notebook Link](../master/calc-diffeq-analysis/taylor-fourier-series.nb)

This demonstration shows how a [Taylor Series](https://en.wikipedia.org/wiki/Taylor_series) or a [Fourier Series](https://en.wikipedia.org/wiki/Fourier_series) approximation of a given function changes as more terms are added to the series. The Taylor and Fourier series' are both ways of representing functions as linear combinations of simpler functions (polynomial functions for Taylor and trigonometric functions for Fourier). They also have important applications in computational mathematics, since taking only the first few terms of the series can provide a simple approximation of a potentially complicated function within a small neighorhood.

This program includes two Manipulate environments: one for Taylor series and one for Fourier series. Both include a dropdown menu of example functions and a slider to select the number of terms to include. The Taylor series also includes a slider to select the center of the approximation. These can be used to show how well the approximations model the original function near or far from the center, and how adding more terms changes things.

### Vector Kinematics

<img src="images/vector-kinematics-1.png" alt="Vector Kinematics Image 1" height="300"/> <img src="images/vector-kinematics-2.png" alt="Vector Kinematics Image 2" height="300"/>

Created 8/28/2017

[Notebook Link](../master/calc-diffeq-analysis/vector-kinematics.nb)

This demonstration is meant for elementary Calculus students encountering the concept of position, velocity, and acceleration vectors for the first time. It includes a series of Manipulate environments which describe various kinematic systems such as ballistic motion and rotational orbiting. Within each system there is a time slider to animate the system, and there is a toggle to select whether to display the position vector (with its x- and y-components), the velocity vector (with its x- and y-components), the acceleration vector (with its x- and y-components), and the velocity vector along with the acceleration vector. The purpose of these animations is to give a visual demonstration of how the velocity vector describes where the position vector is "about" to move to, and how the acceleration vector does the same for the velocity vector.

## Number Theory

Number theory is not really my area, so most of the files in this folder are related to number sequences which give rise to interesting graphics that anybody can appreciate.

### Pascal's Triangle Fractals

<img src="images/pascals-triangle-fractal-1.png" alt="Pascal's Triangle Fractals Image 1" height="300"/> <img src="images/pascals-triangle-fractal-2.png" alt="Pascal's Triangle Fractals Image 2" height="300"/>

Created 6/28/2015

[Notebook Link](../master/number-theory/pascals-triangle-fractals.nb)

[Pascal's Triangle](https://en.wikipedia.org/wiki/Pascal%27s_triangle) is a triangular array best known for the property that its rows consist of the [binomial coefficients](https://en.wikipedia.org/wiki/Binomial_coefficient). There are many other lesser-known properties of Pascal's triangle, including its relationship to the fractal [Sierpiński Triangle](https://en.wikipedia.org/wiki/Sierpi%C5%84ski_triangle). This is one of my favorite examples of a fractal appearing in an unexpected place.

A Sierpiński triangle can be generted by highlighting all odd entries in Pascal's triangle. Using the fact that each entry of Pascal's triangle is the sum of the two preceding entries, we can think of Pascal's triangle as an [elementary cellular automaton](https://en.wikipedia.org/wiki/Elementary_cellular_automaton) (specifically [Rule 60](https://en.wikipedia.org/wiki/Elementary_cellular_automaton#Rule_60)).

This program generates an instance of Pascal's triangle with the specified number of rows, and can color the entries depending on whether they are divisible by a chosen value. Highlighting the entries not divisible by 2 (i.e. the odd entries) generates a Sierpiński triangle. Choosing values other than 2 results in different fractals.

### Recamán's Sequence

<img src="images/recaman-1.png" alt="Recamán's Sequence Image 1" height="150"/> <img src="images/recaman-2.png" alt="Recamán's Sequence Image 2" height="150"/>

Created 8/25/2018

[Notebook Link](../master/number-theory/recamans-sequence.nb)

Recamán's Sequence (sequence [A005132](https://oeis.org/A005132) in the [OEIS](oeis.org)) is defined by an iterative process beginning at 0, at step _n=0_. In step _n_, we either take _n_ steps backward or _n_ steps forward. We go backward if doing so would take us to a nonnegative number that has not yet been visited, and otherwise we go forward. It is conjectured that this sequence includes every nonnegative integer exactly once.

This program is mostly meant for drawing pictures of Recamán's Sequence. Because each step is 1 unit larger than the preceding step, the most common way to draw it is using semicircular arcs to trace the path of the sequence on the number line. Doing so leads to interesting spiral patterns that illustrate the phases of rapid increase and of repeatedly bouncing back and forth to fill in areas that were previously unexplored.

### Remainder Graphs

<img src="images/remainder-graph-1.png" alt="Remainder Graph Image 1" height="300"/>

Created 10/10/2017

[Notebook Link](../master/number-theory/remainder-graph.nb)

[Demonstration Link](http://demonstrations.wolfram.com/AnimatedRemainderGraph/)

I was inspired to write this program by an [article](https://mindyourdecisions.com/blog/2015/07/26/divisibility-by-7-test-using-a-graph-why-does-it-work-sunday-puzzle/) by Presh Talwalkar. It demonstrates a cool trick for determining remainders after dividing a large number by a small number. Because this also allows calculating remainders of 0, this also encompasses the topic of divisibility tests. Testing for divisibility by 7 is famously tricky compared to the other small numbers, but this graphical method gives a fairly easy solution.

As an example, suppose we wish to know whether 42,959 is divisible by 7. The process begins by writing the numbers 0, 1, ..., 6 in a circle and connecting them in a cycle with black arrows. Next, for each of these numbers, we multiply it by 10 and then evaluate the remainder after division by 7, and draw a green arrow from the original number to the result. For example, for 2, we multiply by 10 to get 20, then divide by 7 to get 14 with remainder 6, which means that we should draw an arrow from 2 to 6. At the end of the process we will have 7 black arrows and 7 green arrows.

With this graph in place, we begin at position 0 and then read the digits of 42,959 from left to right. Each time we read a digit, we advance around the black circuit that number of steps. Between each digit, we follow the green arrow that leads out of the current position. In this case, we begin at 0 and read the first digit, "4". Then we advance 4 places to position 4, and then follow the green arrow to position 5. The next digit is "2", so we advance 2 to arrive at 0, and then follow the green arrow to remain at 0. Next we take "9" steps to 2, follow the green arrow to 6, advance "5" digits to 4, follow the green arrow to 5, and finally advance "9" digits to arrive back at 0. The final position is the remainder after division by 7. In this case it is 0, indicating that 42,959 is, indeed, divisible by 7.

The reasons for why this method works are worth figuring out for oneself (see the article linked above). It also generalizes to any base besides 7, and doing so produces some interesting graphical representations of why the well-known divisibility tests that students learn in basic arithmetic work. For example, the graphs resulting from 2, 5, and 10 all have the property that every green arrow points to 0, indicating that, no matter where the black arrows take us, we will always reset our position to 0 between steps. As a result, only the final digit matters, which is exactly what students learn for 2, 5, and 10. The graphs resulting from 3 and 9 both have the property that every green arrow is a loop, making them essentially meaningless. As a result, only the total number of steps taken on the black arrows (which is the sum of all digits) matters, and that is exactly what students learn for 3 and 9. 11 is also rather interesting.

## Graph Theory

Graph theory is close to my area of research. It is also a mathematical field that is inherently visualizable, and as such lends itself well to visual demonstrations. Since graphs are such a basic unit of information, many of the files in other sections (such as [Remainder Graph](#remainder-graphs)) indirectly involve some graph theory. The demonstrations in this section are those that are more directly related to graph theory.

### Dijkstra's Algorithm and A* Search

<img src="images/dijkstras-algorithm-astar-search-1.png" alt="Dijkstra's Algorithm and A* Search Image 1" height="300"/> <img src="images/dijkstras-algorithm-astar-search-2.png" alt="Dijkstra's Algorithm and A* Search Image 2" height="300"/>

Created 11/8/2017

[Notebook Link](../master/graph-theory/dijkstras-algorithm-astar-search.nb)

[Demonstration Link](http://demonstrations.wolfram.com/DijkstrasAndASearchAlgorithmsForPathfindingWithObstacles/)

[Dijkstra's algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) and [A* search](https://en.wikipedia.org/wiki/A*_search_algorithm) are two well-known graph search algorithms capeable of finding the shortest path between two nodes. This demonstration shows how both work for the problem of navigating between two specified points on a 2D grid with obstacles. Searched and tentative nodes are highlighted as the algorithm moves forward and the final chosen path is drawn. There are controls to select the start and end nodes as well as the obstacle shapes. A step slider can be used to animate the search process, which ends as soon as a path between the two nodes has been found.

Dijkstra's algorithm attempts to find the shortest path from a start node to every other node on the graph, although it can be halted early if a specific end node is specified. Nodes whose distance has already been determined are marked as "searched", while nodes on the search frontier have tentative distances based on the shortest known path. In each iteration the node with the shortest tentative distance is chosen for search. Because of this, the set of searched nodes slowly expands out from the start node, meaning that the algorithm may search a lot of extraneous nodes on its way to the destination. This can be seen in the demonstration by the way that the "bubble" of explored nodes slowly expands.

A* search is a modified version of Dijkstra's algorithm which explicitly attempts to choose nodes likely to be closer to the destination. This requires extra information in the form of a heuristic distance from each node to the destination (for example, the Euclidean distance based on the node coordinates). Because of this preferential selection, A* tends to move directly towards the destination when possible, spreading out only to find its way past obstacles. An interesting illustration of this is to use the L-shaped obstacle with the start node on the inside and the destination on the outside.

### Graph Untangler

<img src="images/graph-untangler-1.png" alt="Graph Untangler Image 1" height="300"/> <img src="images/graph-untangler-2.png" alt="Graph Untangler Image 2" height="300"/>

Created 2/5/2016

[Notebook Link](../master/graph-theory/graph-untangler.nb)

I wrote this as a tool for myself during my first graph theory course for the purposes of solving graph isomorphism problems. A common way to try to determine whether two different embeddings actually represent the same graph is to imagine that the vertices and edges can be moved around. If one graph can be manipulated to look like the other, then they must be isomorphic, and the physical movements which occurred are a physical representation of the bijection from one graph to the other.

This file contains a very simple function that accepts a _Mathematica_ Graph object and produces a circular embedding of the graph. The vertices can be clicked and dragged to move them around.

## Just for Fun

The files in this folder were simply made out of personal interest. Many of them are not serious attempts to demonstrate any mathematical concept, and are instead just made to solve an interesting puzzle or generate an interesting figure. I have still shown a few to my students, however, as demonstration of some things that can be done in _Mathematica_.

### Bézier Curves

<img src="images/bezier-curves-1.png" alt="Bézier Curves Image 1" height="300"/> <img src="images/bezier-curves-2.png" alt="Bézier Curves Image 2" height="300"/>

Created 9/8/2017

[Notebook Link](../master/fun/bezier-curves.nb)

[Bézier Curves](https://en.wikipedia.org/wiki/B%C3%A9zier_curve) are parametric curves defined by a sequence of control points. Most people would be familiar with them from simple graphics programs like MS Paint. They are commonly used for drawing smooth curves that are easily adjustable by clicking and dragging the control points. The process of drawing a Bézier curve can be imagined by moving points at constant speed between each pair of control points, defining a new, smaller set of moving control points. This process is then repeated with the new set of even fewer control points, repeating until reaching only a single control point. The path of this single control point is the curve.

There are some interesting mathematical properties and applications of Bézier curves, but my main interest was in watching their drawing process. This demonstration animates the process of drawing a Bézier curve for a given set of control points. I am not sure whether the program, itself, has much educational value, but it does look really cool.

### Domino and Tromino Tiling

<img src="images/domino-tiling-1.png" alt="Domino Tiling Image 1" height="300"/> <img src="images/tromino-tiling-1.png" alt="Tromino Tiling Image 1" height="300"/>

Created 10/16/2017

[Notebook Link](../master/fun/domino-tromino-tiling.nb)

[Demonstration Link](http://demonstrations.wolfram.com/DominoAndTriominoTilingsOfAChessboard/)

This file combines two related puzzles that involve tiling a chess board. The main purpose of the puzzles is to figure out for yourself whether tilings exist under certain circumstances, and how you could go about finding these tilings. The tromino puzzle, in particular, is often used as an introduction to proof by induction. This program makes use of the puzzles' solutions to compute tilings and display the results.

**Domino Puzzle:** Consider the problem of attempting to tile a chess board with dominos, each of which covers two adjacent squares. The goal is to cover the entire chess board with no gaps, no overlap, and nothing hanging over the edges. Obviously this can be done since the dominos can be laid out in rows like bricks.

What if we remove some squares from the chess board? If we just remove one square then the tiling is obviously impossible. A chess board contains 64 squares, so removing 1 leaves 63, and there is no way to cover an odd number of total squares if each domino covers exactly two squares. What if we remove two squares? That leaves 62, which is even and thus not immediately ruled out. To make things simple, suppose we remove the opposite corners of the chess board. Can it be tiled with dominos? What pairs of squares could be removed while still allowing a domino tiling?

**Tromino Puzzle:** Consider the problem of attempting to tile a chess board with L-shaped _trominos_, each of which covers _three_ adjacent squares. This is impossible on a standard chess board because 64 is not divisible by 3.

What if we remove a single square from the board? Then we would have 63 squares, which is divisible by 3, and thus might be possible. Suppose, for simplicity, that we remove a corner from the board. Can it be tiled with trominos? What squares could be removed while still allowing a tromino tiling?

### Dragon Curve

<img src="images/dragon-curve-1.png" alt="Dragon Curve Image 1" height="180"/>

Created 5/6/2016

[Notebook Link](../master/fun/dragon-curve.nb)

The [dragon curve](https://en.wikipedia.org/wiki/Dragon_curve) is my favorite fractal, and considering how much I love fractals that is really saying something. Like all fractals it looks cool and has some interesting properties, like being self-similar and tileable and being two-dimensional in the limit despite each finite iteration being one-dimensional. However, unlike many fractals it is fairly simple to approximate in real life, and the final shape is completely unexpected based only on the first few iterations.

One of the several equivalent constructions of the dragon curve involves taking a thin strip of paper and folding it in half, end-to-end, several times (the number of folds corresponds to the generation number). Then unfold the paper, open each crease to form a 90 degree angle, and look at the edge of the strip. The first fold simply creates an "L" shape. Starting over and adding a second fold creates a roughly "?" shape. Including additional folds one-at-a-time and observing the resulting curve produces shapes that are not very interesting, but after around 6 or 7 folds the shape begins to become incredibly intricate and complex.

This Notebook defines a function that applies a recursive algorithm to draw a specified generation of dragon curve. Due to the recursive nature, the computational time increases exponentially as the generation number increases, so I would not recommend trying to draw anything past approximately 18 generations. I would also not recomment running the entire notebook at once, and instead running only specific blocks one-at-a-time.

### Fractal Shoulder Angels and Devils

<img src="images/fractal-angels-devils-1.png" alt="Fractal Shoulder Angels and Devils Image 1" height="200"/> <img src="images/fractal-angels-devils-2.png" alt="Fractal Shoulder Angels and Devils Image 2" height="200"/>

Created 3/15/2016

[Notebook Link](../master/fun/fractal-angels-devils.nb)

This is a joke based on the shoulder angel/devil trope for representing a character's internal struggle over an ethical dilemma. Occasionally in films the idea of a shoulder angel is toyed with by giving the shoulder angel, itself, its own tiny shoulder angel and devil. I thought it would be funny to carry that out to its logical conclusion.

The program generates fractal arrangements of shoulder angels and devils with adjustable parameters, including the relative scaling and position of each generation.

### Pythagoras Tree

<img src="images/pythagoras-tree-1.png" alt="Pythagoras Tree Image 1" height="200"/> <img src="images/pythagoras-tree-2.png" alt="Pythagoras Tree Image 2" height="200"/>

Created 1/6/2016

[Notebook Link](../master/fun/pythagoras-tree.nb)

This is a simple program containing a variety of Manipulate environments to generate [Pythagoras tree](https://en.wikipedia.org/wiki/Pythagoras_tree_(fractal)) fractals with various parameters. A Pythagoras tree is generated iteratively by beginning with a square and then stacking two smaller squares on top of it, leaning against each other and meeting at the corner. The same process is then repeated on top of the two new squares, and then on top of the four new squares, and so on. The relative sizes of the two squares (or equivalently the angle at which they meet) determines the shape of the tree.

There is not much mathematical content here. The main purpose of the program is simply to generate cool-looking fractals, and so most of the options are related to the display.

### Spirograph

<img src="images/spirograph-1.png" alt="Spirograph Image 1" height="150"/> <img src="images/spirograph-2.png" alt="Spirograph Image 2" height="150"/> <img src="images/spirograph-3.png" alt="Spirograph Image 3" height="150"/> <img src="images/spirograph-4.png" alt="Spirograph Image 4" height="150"/>

Created 10/27/2016

[Notebook Link](../master/fun/spirograph.nb)

This is an interactive version of a [Spirograph](https://en.wikipedia.org/wiki/Spirograph) which displays the path of a pen attached to a disk rolling around a larger disk. There are controls to adjust the relative sizes of the disks, whether the small disk is inside or outside the larger disk, and where the pen is positioned (even allowing it to be outside of the disk). There is also a feature that displays a disk rolling on its edge around in circles.

This was originally written while teaching Calculus, which is when many students are introduced to the concept of polar and parametric coordinates. Part of the course material mentions [epicycloids](https://en.wikipedia.org/wiki/Epicycloid) and [hypocycloids](https://en.wikipedia.org/wiki/Hypocycloid), both of which are interesting in their own right and both of which show up in nature in some unexpected places, but I thought that it would be more impactful to show how they can all be generalized using this type of rolling mechanism.
