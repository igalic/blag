---
title: resume
date: 2010-02-12
author: igor
template: article.jade
---
# Résumé
I discovered [Theo Schlossnagle](http://omniti.com/is/theo-schlossnagle) as [blogger](http://lethargy.org/~jesus/) much earlier than as [author](http://omniti.com/writes/scalable-internet-architectures). It was his post describing the ambiguity of [Web Operations](http://lethargy.org/~jesus/writes/a-job,-a-mission,-a-career-all-without-a-path-or-a-name) that made me really aware of how deep an understanding he has to what the muddy term "Operations" means to the most of us. (Or most of the people I've been working with anyway).

I sent his article to my boss, and he was taken aback too, because it spoke so directly to him as it had spoken to me. What an "Application Engineer" (we) does isn't quite clear, and thus hiring good people to do it, is quite hard.

Basics
------

So let's take a tour through the list:

> They have a deep understanding of networks, routing, switching, firewalls, load-balancing, high availability, disaster recovery, TCP & UDP services, NOC management, hardware specifications, several different flavors of UNIX, several web server technologies, caching technologies, several databases, storage infrastructure, cryptography, algorithms, trending and capacity planning.

-   **Networks**: CCNA, routing and switching, IOS and friends. It's been some time now, though - but this is one of the fundamental basics
-   **Firewalls**: PIX, Phion (both some time ago), much more fluent with: Linux iptables and BSD pf
-   **Load-Balancing**: F5 BigIP, Apache mod\_proxy\_balancer
-   **TCP & UDP services**: tcpdump, snoop ;)
-   **NOC** best managed with a stick
-   **Hardware Specifications**: Lots of experience with running the same software on different architectures and *very* differing results.
-   **UNIX**: Solaris, OpenSolaris, FreeBSD, Linux
-   **Web Server**: Apache HTTPd, Apache Tomcat (and JBoss), recently: nginx. Briefly: IIS7. Basically: Anything that speaks HTTP and has accessible documentation: Good. Accessible source: GREAT!
-   **Caching Technologies**: ZFS, APC, memcached, varnish, Apache mod\_cache
-   **Databases**: SQLite (my favourite ;), MySQL, PostgreSQL, Oracle (very peripheral). Recently: CouchDB
-   **Storage**: What? LVM? ZFS? No, real Storage. Fortunately someone else was always taking care of that stuff.
-   **Cryptography**: I've read the TLS, OpenGPG RFCs - and my favourite one: *"Internet X.509 Public Key Infrastructure - Certificate and CRL Profile"*
-   **Algorithms**: I have *"The Art of Computer Programming"* on my shelf, but I haven't read them yet.
-   **Trending and Capacity Planning**: At Brainsware, most of the time we evaded this, because of lack of money. All energy was focused on making things faster with the limited hardware we had

> responsible for all of the above, and more. Effective and complete troubleshooting of failures. Making sense of trending information. Understanding work loads that exist. Tuning systems to better accommodate current workloads and proactive tuning to handle known future workloads. One of the key differences between mid-level and junior is the ability to correctly prioritize remediation of issues during incident response. Staying calm, collected and executing with clarity of thought during an emergency.

This blog basically is about documenting trouble-shooting, trending and making a piece of crap hardware from Brainsware perform like the powerhorses we have at Bwin.

One of the things I learned at Bwin is how to prioritize: When a red light on the monitoring is flashing and the NOC is calling, it's important. If shortly thereafter a customer calls, it's very important. Also, it's *VERY BAD*, when the customer calls you *BEFORE the NOC* does! When 300 customers are screaming at you, it's *VERY IMPORTANT and VERY URGENT*.

Now a word on the calm and collected part: Screaming and shouting at your computer, trashing away on your desk and smoking one cigarette after the other. Verbally abusing your computer and server and shell and documentation and everything. Do that. I do it. It really helps. It's all right. It's healthy. But if you're in an office with four other people, two of which might be fighting a production-problem of their own, you're best off being the stoic statue of Zeno of Citium himself. Because that helps everybody.

Rounding it up
--------------

> What does "complete troubleshooting" mean? I mean troubleshooting without boundaries. I want no shyness in cracking open developer code and telling them what they did wrong and why. Finger pointing at people simply doesn't work, you have to point your finger at implementation problems, not people.

I speak several languages: Срско/Hrvatski, Deutsch and English. I understand many more. Same goes for Programming Languages. I'm fluent enough with C, PHP and Perl that I can read and understand other people's code (I have trouble understanding my own from a long time ago ;). But when it comes to fixing a system, it doesn't much matter what the language is, you just dig in, find the offending code, and either fix it yourself, or tell the developers! Oh man, I love F/OSS. I wish it could work everywhere like that.
