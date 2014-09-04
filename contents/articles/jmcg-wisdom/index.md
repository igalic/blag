---
title: jmcg wisdom
date: 2011-09-09
author: igor
template: article.jade
---
# jMCg wisdom
A chatlog from \#opencsw on FreeNode:

```irc
 * automaciej hopes no one asks why or how different
< jMCg> automaciej: if they do, pretend to know, then: Use the source!
< jMCg> That's what I usually do..
< automaciej> jMCg: http://paste.pocoo.org/show/473126/
```

And here's the paste:

    cat jMCg-help.c
    if someone_asks(thing) {
        printf("That's simple.\n");
        wisdom = get_wisdom(thing.source);
        printf(wisdom);
    }
