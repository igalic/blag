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

* don't invent your own configuration format

   …not without good reason, anyway. 
   [There](http://yaml.org/) [are](http://json.org/)
   [*too*](http://www.w3.org/TR/REC-xml/)
   [many](https://en.wikipedia.org/wiki/INI_file)
   [configuration](https://httpd.apache.org/docs/current/configuring.html)
   [formats](https://en.wikipedia.org/wiki/Zone_file)
   [already](http://riemann.io/api/riemann.config.html).
   Before inventing a new format, please discuss this with your ops people beforehand.

* version numbers are a [contract](http://semver.org/)

   This contract extends to the API, the ABI, your configuration, your utilities.
   You can break the contract between major versions, but please, for the love of
   [Knuth](http://sentimentalversioning.org/) don't break the [method of
   determining the version](https://github.com/elastic/puppet-elasticsearch/pull/477)

* providing a tool to modify the configuration…

   Does the [tool](http://wiki2.dovecot.org/Tools/Doveconf) need the daemon to
   be [running](https://trafficserver.readthedocs.org/en/latest/appendices/command-line/traffic_line.en.html)?
   Will it know when the configuration is broken?  Will it be able to tell me
   *how* the configuration is broken?

* use the underlying systems' facilities

   Rather than bootstrapping a daemon and a watchdog, use (smf|systemd|etc…)

   Use the OS package manager, or your programming environment's package
   manager (gem|pip|war|etc). Or your
   [container](http://blog.gardeviance.org/2015/08/is-there-trouble-brewing-in-land-of.html)'s
   package manager. This makes installation really easy, and an *atomic transaction*.

* Do *not* reinvent a new package manager

   If you accidentally did anyway, consider providing a way of finding out if
   the package manager has already [ran
   successfully](https://github.com/bower/bower/issues/1312).

* Put packages into repositories

   This makes installation *actually* easy, and dependency management possible
   within the above mentioned *atomic transaction*.

   [Consider](https://github.com/nodesource/distributions/issues/170) providing
   your repositories over [IPv6](https://gitlab.com/gitlab-org/gitlab-ce/issues/2481)…

   Oh, your package repository should *not* be (only) github.

* If your software needs to scale, it's easier when it's stateless

   If you need to replicate state, how will you do that to 3 nodes?
   How about 300 nodes?

These are the basics. Your software is now installed, configured and running!
But is it running correctly?

* Provide an easy way to get metrics from the software

   This isn't restricted to *health* metrics of the application. But can be
   liberally extended to the health of the *business*.

And finally, if you want to be really nice to your admin, not just your admin's
automation software:

* Provide debuggable errors in the log

   Can someone who didn't write the software find out why it crashed from the
   logs? Can they fix it?

That's all folks!
