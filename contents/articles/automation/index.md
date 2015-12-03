---
title: Software vs Automation
date: 2015-12-03
author: igor
template: article.jade
---

As always, this started out as a presumptuous tweet:

<blockquote class="twitter-tweet" lang="en"><p lang="en" dir="ltr">maintaining
a million puppet modules has taught me one thing: not a single piece of
software was written with automation in mind.</p>&mdash; The Wrath of me™
(@hirojin) <a href="https://twitter.com/hirojin/status/672033157391245314">December 2, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<span class="more"></span>

Of course, this was met with a certain skepticism. So here are some lessons
learned from ~9 years of putting applications into production, and being woken
up by them falling over.

1. don't invent your own configuration format

   …not without good reason, anyway. Discuss this with your ops people beforehand.

1. version numbers are a [contract](http://semver.org/)

   This contract extends to the API, the ABI, your configuration, your utilities.
   You can break the contract between major versions, but please, for the love of
   [Knuth](http://sentimentalversioning.org/) don't break the [method of
   determining the version](https://github.com/elastic/puppet-elasticsearch/pull/477)

1. providing a tool to modify the configuration…

   Does the tool need the daemon to be running? Will it know when the
   configuration is broken?  Will it be able to tell me *how* the configuration
   is broken?

1. use the underlying systems' facilities

   Rather than bootstrapping a daemon and a watchdog, use (smf|systemd|etc…)

   Such as the OS package manager, or your programming environment's package
   manager (gem|pip|war|etc). Or your container's package manager. This makes
   installation really easy, and an *atomic transaction*.

1. Put packages into repositories

   This makes installation *actually* easy, and dependency management possible
   within the above mentioned *atomic transaction*.

   Consider providing your repositories over IPv6…

1. If your software needs to scale, it's easier when it's stateless

   If you need to replicate state, how will you do that to 3 nodes?
   How about 300 nodes?

These are the basics. Your software is now installed, configured and running.
But is it running correctly?
