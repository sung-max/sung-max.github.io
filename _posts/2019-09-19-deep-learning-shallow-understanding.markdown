---
layout: post
title:  "Why is our understanding of Deep Learning so shallow?"
date:   2019-09-29 00:00:00 +0900
categories: computer science, math
use_math: true
comments: true
published: true
uid: 20190929
permalink: /deep-learning-shallow
---

Why is our understanding of Deep Learning so shallow?
Given that the world's best computer scientists, mathematicians, statisticans, and even physicists are thinking about this problem lately,
to me it is a little surprising that our understanding is still hopelessly rudimentary. 

Sure, deep neural networks are complicated objects, but the arsenal of analytical tools we have developed in these mature fields
can tackle pretty complicated objects. So why exactly?

I think it is worth taking a step back and thinking about why we understand so little, before we can progress a little bit forward.
Here are some facets of (unfinished) thoughts I've had over the past year. Disclaimer that many of these ideas are not mine and 
arose from discussions with others.

-------

## Aren’t there mature fields whose tools should have some power here?

My understanding is that as mature as these fields are, if you actually examine more closely the tools they developed,
they are rather surprisingly limited in their scope. Afterall, people tend to study things they have some grasp over.

And it appears that Deep Neural Networks is one thing that's outside their control (caveat: I actually know close to nothing about
some of the fields below; let me know if you have deeper or more accurate characterizations):

* Optimization
  
  The world of optimization is mostly convex. So except for limited special cases of non-convexity, it appears that
  our tools for convex optimization los all their power when we enter the real world. While people often draw tools and insights from convex optimization and apply
  them to the non-convex world nonetheless, there is a deep sense of uneasiness when one actually sits down and starts thinking about it...

* Statistical Learning Theory
  
  We had never really considered the overparameterized regime before DNNs, and ruled out interpolating estimators based on
  believable intuitions we had about overfitting and bias-variance tradeoffs. Only in the past few months have researchers isolated what's now called the "double descent" phenomena, and are beginning to understand it in its simpler settings.
  
  But a bigger problem I think is that SLT has never been a prescriptive framework.
  Although some special cases like boosting seem to have gotten insights from it, it's not clear to me that
  the overall framework is currently built in a way conductive to doing scientific modelling. 
  
  I believe the SLT framework had some power in analyzing SVMs, but probably all bets off when you startchanging the kernel itself?
        
* Statistics
  
  While recently various communities have made vast progress in understanding high-dimensional statistics, my guess is that
  the models we understand are still all too basic. 
  Also, it's only with the recent advances in machine learning that SGD became part of the statistical toolbox,
  so it will be a while before we understand its properties.
  
* Dynamical Systems / Controls
   
  My impression is that while these are very mature fields, in general people don't have a good grasp on non-linear systems.
  Apparently, this is why weather forecasts are still limited to relatively short horizons.
  
  There have been some recent developments passing the discrete dynamics to the continuous one, and analyzing the latter,
  which seems intuitively reasonable, but don't appear to have that much of a ripple in the community.
 
* Statistical physics
  
  Personally I feel that the tools they have developed to analyze their complicated systems should have leverage here, but it appears
  that it hasn't been of any radical use.
  Perhaps because the systems there are quite simpler and regular?
        
* Differential geometry, other abstract math areas
 
  I have no idea what these intuition these guys have, but certainly they don't seem to be that useful so far.


One general trend that has been happening in the field in the past two years is that people from different communities
try to reduce a significant aspect of the problem to something that they understand very well in their area, and claim understanding. While it is certainly plausible that some of their tools do in fact have leverage, I think it would be more productive as a field to actively seek out and develop new tools (even if they are not fully rigorous) to understand these new regimes, rater than trying too hard to reduce to things we understand, yet we secretly suspect are too different from our original goals.

-------

## So how do we progress forward?

It's not clearly to me, honestly. 
On some level, it's not even clear what "understanding" deep learning would even look like. 

Are there other similar instances from human history that we can draw inspiration from?
At least, to get a sense of what level of understanding we should strive for.

One analogy that seems to come up constantly is aerospace engineering. 
From what I hear, while we have a very good grasp on its engineering (obviously, since we take commercial flights for granted now), 
a lot of it is simulation based (though I don't have a good sense of what their design process looks like. Probably much much more rigorous than machine learning). So perhaps that's all we can hope for in deep learning too.

-------

## What about Neuroscience?

Here, the comparison makes the outlook even more grim.
Afterall, if DNNs are indeed working similarly to their original inspiration (e.g. human brain), and given that our understanding of
the brain is still hopelessly basic, why should we hope to understand these objects better?
Perhaps we have finally found something that mimics the human intellect, but we will never be able to understand it, just like we have failed to do so for our own brains.
Here is a quote that says this more eloquently:
> "...artificial neural networks are understood only at a heuristic level, where we empirically know that
> certain training protocols employing large data sets will result in excellent performance. This is reminiscent of the
> situation with human brains: we know that if we train a child according to a certain curriculum, she will learn
> certain skills — but we lack a deep understanding of how her brain accomplishes this" (Lin, Tegmark, Rolnick, 2017).

The huge difference, though, is that we technically do have access to these objects in their entirety.
We have all the weights, connections, manipulate it in all kind of ways (well, up to computational resources :). So hopefully that will give us enough
leverage to glean out its inner workings in the future, as we progressively amass more experimental data and insights.

