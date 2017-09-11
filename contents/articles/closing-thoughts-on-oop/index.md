---
title: closing thoughts on oop
date: 2014-07-24
author: igor
template: article.jade
---

From time to time I say something semi-interesting on twitter, and then get sucked into *very* interesting discussions:

<blockquote class="twitter-tweet" lang="en"><p><a href="https://twitter.com/seriouspony">@seriouspony</a> twas one of my first programming lessons.&#10;and I&#39;m on <a href="https://twitter.com/mykola">@mykola</a>&#39;s boat here, it kinda reinforces *one* model onto young minds.</p>&mdash; The Wrath of K&amp;R™ (@hirojin) <a href="https://twitter.com/hirojin/statuses/492339244225273857">July 24, 2014</a></blockquote> <script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

This one was about teaching young people how to code using non-programming
examples in the real world.
We also touched on OOP.

I have thoughts on OOP.

<span class="more"></span>

We were taught in school all the nomenclature and theory of OOP as it was retrospectively applied onto Smalltalk, but were then taught C++, Java, and I later learned and taught PHP.
Those languages, as Kay has said himself, have nothing to do with Smalltalk's OOP.
They solve very valid problems, and do so in an idiosyncratic way.
Like **any other** language.

But the fact that these languages call the tools they use to solve these problems Objects and Classes, misinformed generations of programmers about what OOP could be.
In the sense way generations of programmers and software designers have been mislead as to what design patterns can be from books written exclusively for languages lacking certain abstractions concepts, or getting in the way with others.

---

I'll try not to bash too hard on these languages, even though I like to draw parallels between "enterprise patterns" and "decline of the agile movement".

Let's take a different comparison instead: The Puppet DSL is a declarative programming language implemented in Ruby.
It has "`class`es" which are actually just singletons.
These singletons are used as containers to hold variables, defer execution, or sometimes even just as namespace.

At no point does Puppet call itself object oriented.
Perhaps what we can take from this is that all languages will have to solve the problem of encapsulation, but that the naming things is still one of the hardest problems to solve.
With possible exception for community management.
