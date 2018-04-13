---
layout: post
title:  "Collecting coupons and Projecting Cubes"
date:   2018-04-13 19:30:00 +0900
categories: programming, math
use_math: true
comments: true
published: true
uid: 20180413
permalink: /coupons-and-cubes
---

I've been participating in Google Code Jam on and off for the past 7 years. It's probably my favorite among similar competitions; 
everything about it feels very clean and professional, from the UI to the clean solutions that are possible. I also particularly like the separation between small and larget inputs.

Despite being physicially limited this year (I didn't have access to my own computer or local storage), 
I ended up participating in the qualification round as the new interface
made it much easier for me to participate from my army base. Overhearing some of my bunkmates discussing the problems made me curious too.

-------

## Overview

Here are the names of the four problems from this year's Qualification Round, which happend on April 7:

* **Saving the Universe, Again**

  A typical greedy problem (feels like de ja vu, almost). There is also a linear time solution, but I couldn't motivate myself 
  to implement it.

* **Trouble Sort**

  A very cute problem. Would recommend.

* **Go, Gopher!**

  A new type of interactive problem. My first initial reaction was negative, but the problem turned out to be more interesting than I initially 
  suspected.

* **Cubic UFO**

  A nice 3D geometry problem that could be approached in a few ways. 


Here's a [link](https://codejam.withgoogle.com/2018/challenges) to all the rounds from this year's competition.

Below I will give some commentary and analysis on the last two problems.


-------

## Go, Gopher!

Probably anyone could think of the following straightforward approach: just pick a target area of at least 200 (I picked a stripe of dimensions 3 x 67),
divide it into squares of 3x3 cells, and target the centers of every square until each square is completely filled.

The only questions is, can we do this efficiently using less than 1000 queries?

I think the new limit on the number of queries rather than on computation time is a very interesting one (there is a limit on time too, but surely the one on quries is more stringent).
This reminds of some of the research in learning theory and high dimensional statistics in grad school, 
where often we care about number of samples as well as the time complexity.
So I think from a larger perspective the new type of problem is fitting given our current perspective on computer science and learning at large.

### Analysis
We could treat filling all 9 cells of each square as a [Coupon collector's problem](https://en.wikipedia.org/wiki/Coupon_collector%27s_problem).
We get an estimate of the tail probability on the number of required queries $$T$$ to fill a 3x3 square (using the tail estimate in the above link with $$n=9$$): $$\text{Pr}(T \gt 20 \beta) \le 9^{-\beta+1}$$ for any $$\beta > 0$$

Unfortunately, this seems way too low and I was certain that this approach would fail.
But after I wrote a script and ran the simulations, the queries were concentrating very well around about 550!
I had forgotten to take into account of the fact that each coupon collection problem is independent and they add up to
something that concentrates very nicely.

Despite having thought about more complicated instances of concentration of measure, I had failed to take notice of it in this simple setting.
But it was nice to see with my own eyes that concentration of measure has more use besides proving theorems that can go up on arxiv,
mainly helping me proceed to the next round of GCJ : )


### Alternatives?

When using the above stripe, we can also query all of the middle 1x65 segment instead of segregating into separate grid cells and querying each one.
At first this seems like a dumb,  redundant thing to do, but then I wondered if there's much to lose since each query point will be satisfied (which I define to be if all of its neighbors are filled)
more easily so we can move on more faster. 
But this seems like a much more complicated scenario to analyze due to all the dependnecies between neighboring queries. In simlutions, it does worse, concentrating around about 650 queries.


I wonder if more efficient alternatives are possible.
Or perhaps if we can prove that the above "coupon collecting in non-intersecting regions" can be shown to be optimal in some sense.
What about in higher dimensions?

--------

## Cubic UFO

I figured that intuitively the area of the shadow is maximized when its projection is a regular hexagon.
If so, it would be enough to rotate only using one axis (though some initial rotation makes it easier to work with
standard basis). I did calculations with some trig and 2d rotations and in fact the projected reached the maximum area of $$\sqrt{3}$$ on WolfamAlpha,
but I wasn't satisfied. Surely there was a more intuitive justification using symmetry or something of the sort?

I was delighed with the following cute proof from my bunkmate Jongwon. I wasn't able to find anything similar in the official commentary or elsewhere online so far,
so I decided to share it with all of you:

* First, observe we can think of choosing a plane (which is specificed by its unit normal, or any direction in 3d) to project against, rather than rotating the cube
and projecting out the $$y$$. Let the normal be $$(u_x, u_y, u_z)$$.

* Also, observe that the area of projection of a single side of the cube is the (absolute value of) the cosine of the angle its normal makes with the normal of the projection plane. Assuming normalization, then the area is just the absolute value of the inner product between the two normals.
  Then, it's not hard to see that the area of projection of the cube is exactly the sum of the absolute value of the inner products between the projection plane normal and each of the normals of three orthogonal sides of the cube.
  
* Now, it's nice working with the dual perspective of rotating the projection plane rather than the cube, because the three normals of the cube remain fixed at the standard basis: $$(1,0,0), (0,1,0),$$ and $$(0,0,1)$$. 
Hence, from above, the area of the cube's projection is just $$|u_x| + |u_y| + |u_z|$$. 
 
* So our goal is the maximmize this quantity subject to the $$u_x^2 + u_y^2 + u_z^2 \le 1$$.
 Via Cauchy-Schwartz, we can easily see that the maximum area achieved is $$\sqrt{3}$$ when $$|u_x| = |u_y| = |u_z|$$, which is exactly when the projection is symmetric.
 
In the official commentary, a reference is made to the "amazing cube shadow theorem," which I understood as saying that when the side length of the cube is 1 (in some unit), the orthogonal height of the rotated cube is the same as its projected area (we're comparing lengths and areas here, hence the need for normalization in unit). This seems like a mystery but using similar calculations as above one can show that indeed the two physical quantities are computing the same mathematical quantity, $$|u_x| + |u_y| + |u_z|$$ (after appropriate rotation).
 So no mystery.
 
 
Now what's great is one can take advantage of the above proof to also derive a constant time solution. 
I'm lazy so I'll leave that as an exercise to the reader.



--------

### *Updates*

Apr 13, 2018: first version
