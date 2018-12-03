---
title: xy
date: 2011-10-19
author: igor
template: article.pug
---

# XY

80% of customer support is figuring out what the customer's problem really is.
Usually that's because someone or something set into their mind that they have to use a certain technology.

```plain
< Mmike> Hm, it seems that I do have to enable/set rewrite rules per vhost :/
< jMCg> That sounds like a good idea. Maybe.
< jMCg> (Or: Don't use mod_rewrite)
< Mmike> I have to.
< Mmike> I mean, the clients "applications" depends on them
< jMCg> fallbackresource
< fajita> http://httpd.apache.org/docs/trunk/mod/mod_dir.html#fallbackresource For versions earlier than 2.2.16, see the 'rewrite everything' factoid.
< jMCg> rewrite everything
< fajita> http://httpd.apache.org/docs/trunk/rewrite/remapping.html#fallback-resource
< jMCg> That's like 95% of what clients' applications depend on. And you can fix that with one directive.
< jMCg> Works for WordPress, btw.
< Mmike> hm
< Mmike> taht's of no use to me
< Mmike>    RewriteCond %{HTTP_USER_AGENT} ^Zeus [NC]
< Mmike>    RewriteRule ^.* - [F,L]
< Mmike> this is what I need to have in every virtualhost on the server, and I have 250 of them
< Mmike> so I tought if including that in global httpd.conf, but no gain, i need to have it in each vhost
< jMCg> mod_macro
< fajita> An Apache module written by Fabien Coelho that lets you define and use macros in the Apache configuration file. or http://www.cri.ensmp.fr/~coelho/mod_macro/, or http://www.coelho.net/mod_macro/
< jMCg> That's just wrong :-/
< jMCg> mod_security
< fajita> http://www.modsecurity.org/projects/modsecurity/apache/index.html
< jMCg> Mmike: use mod_security for that kind of crap.
< Mmike> hm
< Mmike> I can try, yes
< Mmike> but, why is mod_rewrite wrong here?
< jMCg> Because mod_security is an Web Application Firewall -- and mod_rewrite is a URL transformation engine. - You're using a wrench as a screw driver because some part somehow fits into the screw.
< jMCg> So, essentially, this is a case of:
< jMCg> xy problem
< fajita> You want to do X, but don't know how. You think you can solve it using Y, but don't know how to do that, either. So, you ask about Y in order to solve X, which doesn't make sense. Just ask about X!
< jMCg> And guess what? mod_security will work on all your vhosts!
< jMCg> But you should look into mod_macro anyway.
< Mmike> it's a bit more complicated than that, because of the politics :)
< Mmike> for some reason we don't use mod_security
< Mmike> but I'll look into them both, thank you
< jMCg> Screw politics. But with a screwdriver, not a wrench
```

The other 80% of customer support is convincing the customer that the solution you provided not only is correct, but also one they should actually use. (This is the hard part)

A good strategy for revealing the XY problem is asking "why": [http://bash.org/?866112](http://bash.org/?866112 "bash.org: Why?")
