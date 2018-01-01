---
layout: post
title:  "Learning QFT"
date:   2017-12-31 19:30:44 +0900
categories: physics
use_math: true
comments: true
topic: physics
published: true
uid: 20171231
header-image: page-header-feynman
---

I spent the past five months getting familiar with the basics of Quantum Field Theory (QFT).
I thought I might write a post to provide some guidance to someone who, like me, have always wanted to understand basics of QFT but have had somewhat
limited education in college level physics.

### Background
To give more context for my background: I took AP Physics B & C in highschool and one undergraduate physics course on [Classical Mechanics][phy3318], but that is as far as my education in physics has gone inside of class.
I've always *liked* physics though, and read numerous pop-science books growing up. I liked physics a lot in highschool and I considered double majoring in it in college, but it never happened for a number of reasons.
Being away from school (ironically?) has given me time to rebuild the some of the missing undergrad foundations and dive into some of the more advanced topics.

Before I proceed, I want to thank [Flip](http://physics.ucr.edu/~flip/), who luckily TA'ed the only physics class I took in undergrad. He's given me very helpful advice in the beginning. Without his encouragement, I don't think I would have gotten to tackling QFT this soon. Thanks, Flip!

[phy3318]: https://www.physics.uci.edu/~tanedo/P3318.html

-------

### Before QFT

QFT does have a few prerequisites, but it is not as daunting as it may seem (given the fact that a first course on QFT is usually taught as a first-year graduate course)

* **Quantum Mechanics**

    You need a solid foundation in undergrad QM. I worked through the entire Griffiths and read most of Sakurai, which seems to be enough so far. You need to be comfortable with the bra-ket notation, different dynamical pictures (Schrodinger, Heisenberg, Interaction), and some basic perturbation theory.

* **Hamiltonian/Lagrangian mechanics**

    You need to be familiar with all the basics. This is a fascinating subject on its own.

* **Special Relativity**

    This is really a half-course in terms of time (though I'm sure you can go a lot deeper into it). You just need to be familiar with the basics and working with tensors and Einstein notation.
    You should be familiar with the covariant form of Maxwell's equations.

* **Mathematical prerequisites**

    Other than the ones that carry over from undergrad physics (vector calculus, etc.) you need to be comfortable with
    using basic theorems of complex analysis for computations (e.g. Cauchy's residue theorem).
    You should be familiar with Green's functions (typically you first see them in E&M).

    Although not necessary, I think it's rewarding to understand the mathematical foundation of distributions (generalized functions), which give more rigorous meaning to objects like dirac delta, which physicists often sloppily deal with.


As you can see, that's just about two and a half physics courses (if you were to prepare yourself really thoroughly) and some mathematical background that you can probably even pick up as you go, which I hope doesn't seem as bad as you might have first imagined from a beast like QFT.


In particular, you do not need to know the following (though it would certainly help):
* Electromagnetism

    You don't need a full standard undergraduate course on E/M.
    For myself I just skimmed parts of David Tong's lecture notes to fill in on the gaps.

* Classical Field Theory

    If you're familiar with Hamiltonian/Lagrangian mechanics for particles the extension to fields is rather straightfoward (though still very amusing)


Note: A mathematician's introduction to QFT (TQFT, for one) probably takes a lot more work, and I have yet to learn that myself.


--------

### Guidelines

Although I'm a beginner myself, here are some targets that I think would have helped me navigate the area better when I first tried to learn QFT.

If you've learned your QM, you'll know that there's usually two standard approach: Schrodinger's and Heisenberg's.
In QFT there's also two formulations, but the contrast is a bit wilder. They are called **canonical quantization** and **path integral**.

Both has its beauty and convenience, but my personal recommendation for starters is canonical quantization.


-----------

### Resources

Here are some books and articles that have helped me along the way.

* [QFT for the Gifted Amateur](https://www.amazon.com/Quantum-Field-Theory-Gifted-Amateur/dp/019969933X)

     Despite the possibly offputting title, this book is great. They really mean much more than an amateur; the exercises can be quite challenging.
    * Pros: they cover a lot (the book has 50 chapters, though each one is very short), and cover many prerequisites along the way.
    * Cons: they cover a bit too much. Some depth might have been better than breadth. Bit childish at times.


* [David Tong's QFT lecture notes](http://www.damtp.cam.ac.uk/user/tong/qft.html)

    These are great to read along with another more in-depth book. Despite its brevity, the notes comment on a lot of subtle things that might have troubled you elsewhere.


* [Gauge theories in Particle Physics](https://www.amazon.com/Theories-Particle-Physics-Graduate-Student/dp/0750309822)

    This books is amazing. Though its depth falls quite short of more traditional texts like Peskin & Schroeder, the writing is extremely lucid. Particularly helpful is Chapter 5, introducing canonical quantization from a physical model, and Chapter 10's overview of renormalization (although for the toy ABC theory), which was by far the clearest and most coherent exposition I came across so far.


* [QFT in a Nutshell](https://www.amazon.com/Quantum-Field-Theory-Nutshell-nutshell/dp/0691140340)

   Despite the phenomenal reviews this book has, I don't think it's the best book for someone completely new. The raving reviews mostly seem to come from people who already understand QFT (for them, I'd imagine it reads more like an insightful overview). But I think it's useful for getting a highlevel refresher after you've read a topic elsewhere.



There are also articles on more focused topics that are helpful:

* [How I Learned to Stop Worrying and Love QFT](https://arxiv.org/abs/1201.2714)

   This is a helpful article that gives some hints of how the extremely shady mathematical hand-waving that physicists routinely do in QFT could be given made more rigorous (though my understanding is that we are still far from giving a completely rigorous treatment of the many issues in QFT).

    There were quite a few gems; one I remember is how the origin of the undetermined coupling constants can be traced back to the ambiguity in defining products of distributions.



Any well-known standard books or articles I left out are definitely not due to their lack of quality--I just haven't gotten to them yet myself.

-------

Here's a functional integral to start off:
$$\int \mathcal{D}[q]e^{i S[q]} $$

...\[to be continued\]

--------

### *Updates*

Dec 31, 2017: first version



