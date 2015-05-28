---
title: Thoughts on Distributed Systems, and segregated Dev and Ops
date: 2015-05-28
author: igor
template: article.jade
---

I have some WORDS on distributed systems development.

It's also WORDS on DEV ops…

The experience with DEV ops I've had so far is that DEV ops mostly
materializes, out of frustration, from ops folk.  In those scenarios, Dev and
Ops are still segregated, often widely so, because this a revolution from
below, and those are either slow, or don't work.

However, thanks to all the automation going on in Ops, Dev can suddenly churn
out more complex, more distributed systems.

This happens while, at the same time they keep ignoring input from Ops. This is
a function of the ongoing segregation: Dev and Ops are far from aligned, so why
should we bother adding sensible logging, or sensible monitoring.  The complex
systems are possible to ***deploy***, thanks to Ops polishing away at the turd,
as well as the occasional feature request from ops that gets through to product
management.

Nobody cared enough, or had a say in the development of logging, or monitoring
"features. Let's not even talk about things like ~introspection~.

This is of course, because deploying such a complex distributed system, and
configuring it correctly is such a mountain of work for Ops. So much so, that
it noticeably detracts from their daily business of keeping the business alive.
Thus, we shift the goal of what success means: A huge amount of work in order
to ***deploy***, and ***correctly configure*** a giant, complex, distributed
system is now seen as a marker of success.

But What happens when such a complex, distributed systems, developed in
segregation, in multiple teams, each piece tested and approved because it
"works on my machine", integrated by yet a different team that barely knows the
architecture is put into production and then fails? Often silently…

How do you debug such a system now?
