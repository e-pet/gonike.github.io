---
published: false
layout: post
image: /images/2018-04-04-interpolation.png
title: Don't use standard cubic spline interpolation
---
... or at least, now exactly what you're doing.

Following my numerics course in university, I somehow had this idea that standard cubic splines were a good thing (tm) and this is what one should generally do when solving an interpolation problem in practice.
Let's see why this may - in many cases - be a bad idea, and how we can do better.

### How does standard cubic spline interpolation work?
blah...

### Why may this be a bad idea?
Monotonicity, locality, smoothness, ...
Example with > 0 restriction...

### How can we do better?
Akima, Pchip...

Refs...(Moler,+?)

### Examples
Let's see how the methods discussed above compare in some small examples.
First, we consider the interpolation of impulse data.

![Interpolation results for impulse data](/images/2018-04-04-interpolation-impulse.png){:height="400px"}
([Python code for generating this figure](/snippets/interpolation/interpolation.py))

The *ringing* behavior of the standard spline interpolation is very obvious; above we have seen several reasons why this may be harmful in practice.
The Akima and Pchip interpolations almost completely coincide for these data, so let's consider a second example to assess their differences.

![Interpolation results for sine data](/images/2018-04-04-interpolation-sine.png){:height="400px"}
([Python code for generating this figure](/snippets/interpolation/interpolation.py))

Here it becomes apparent that the Akima interpolation really does not result in a monotone approximation, as opposed to the Pchip interpolation.

### Conclusion
Blah...
Pointer regression...

[The code for reproducing the figures in this post is available on my GitHub page.](/snippets/interpolation/interpolation.py)