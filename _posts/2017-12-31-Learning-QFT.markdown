---
title:  "Learning QFT"
date:   2017-12-31 19:30:44 +0900
categories:
use_math: false
comments: true
---

I spent the past five months getting familiar with the basics of Quantum Field Theory (QFT).
I thought I might write a post to provide some guidance to someone who, like me, have always wanted to understand basics of QFT but have had somewhat
limited education in college level physics.

### Background 
To give more context for my background: I took AP Physics B & C in highschool and one undergraduate physics course on [Classical Mechanics][phy3318], but that is as far as my education in physics has gone inside of class.
I've always *liked* physics though, and read numerous pop-science books growing up. I liked physics a lot in highschool and I considered double majoring in it in college, but it never happened for a number of reasons.
Being away from school (ironically?) has given me time to rebuild the some of the missing undergrad foundations and dive into some of the more advanced topics.

Before I proceed, I want to thank [Flip](http://physics.ucr.edu/~flip/), who TA'ed the only physics class I luckily took in undergrad. He's given me very helpful advice in the beginning. Without his encouragement, I don't think I would have gotten to tackling QFT this soon. Thanks, Flip!

-------

### Before QFT

QFT does have a few prerequisites, but it is not as daunting as it may seem (given the fact that a first course on QFT is usually taught as a first-year graduate course)

* Quantum Mechanics

    You need a solid foundation in undergrad QM. I worked through the entire Griffiths and read most of Sakurai, which seems to be enough so far. You need to be comfortable with the bra-ket notation, different dynamical pictures (Schrodinger, Heisenberg, Interaction), and some basic perturbation theory.
    
* Hamiltonian/Lagrangian mechanics

    You need to be familiar with all the basics. This is a fascinating subject on its own.

* Special Relativity 

    This is really a half-course in terms of time (though I'm sure you can go a lot deeper into it). You just need to be familiar with the basics and working with tensors and Einstein notation.
    You should be familiar with the covariant form of Maxwell's equations.

* Mathematical prerequisites

    Other than the ones that carry over from undergrad physics (vector calculus, etc.) you need to be comfortable with
    using basic theorems of complex analysis for computations (Cauchy's residue theorem).
    You should be familiar withe Green's functions (typically you first see them in E&M).
    
    Although not necessary, I think it's rewarding to understand the mathematical foundation of distributions (generalized functions), which give more rigorous meaning to objects like dirac delta, which physicists often sloppily deal with.
    
    
As you can see, that's just about two and a half physics courses (if you were to prepare yourself really thoroughly) and some mathematical background that you can probably even pick up as you go, which I hope doesn't seem as bad as you might have first imagined from a beast like QFT.
  
  
In particular, you do not need to know the following (though it would certainly help):
* A full undergraduate course on E & M

    For myself I just skimmed parts of David Tong's lecture notes to fill in on the gaps.
    
* Classical Field Theory

    If you're familiar with Hamiltonian/Lagrangian mechanics for particles the extension to fields is rather straightfoward (though still very amusing)


Note: A mathematician's introduction to QFT (TQFT, for one) probably takes a lot more work, and I have yet to learn that myself.


--------

### Guidelines

Although I'm a beginner myself, here are some targets that I think would have helped me navigate the area better when I first tried to learn QFT.

If you've learned your QM, you'll know that there's usually two standard approach: Schrodinger's and Heisenberg's.

In QFT there's also two formulations, but the contrast is a bit wilder. They are called **canonical quantization** and **path integral$$.

Both has its beauty and convenience, but 



-----------

### Resources

Here are some books and articles that have helped me along the way.



Here's a functional integral to start off:
$$\int \mathcal{D}[q]e^{i S[q]} $$

...\[to be continued\]


[phy3318]: https://www.physics.uci.edu/~tanedo/P3318.html
