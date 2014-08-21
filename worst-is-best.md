---
---

<!-- This is massive and sprawling and needs to be cut down. Ruby seems to be
a perfect example of a modern worse-is-better system as defined here, but I'm
not sure I want to bring that in. -->

WORSE: C, Perl, PHP, Javascript (node), Go.

BETTER: LISP, Haskell, Erlang.
Erlang mops the floor with deployment and monitoring but loses on packaging and
getting started quickly.

Values:
Programming languages will be used much more by people who know then than
people who are learning them. Optimize for the expert user. (better)

Optimize for starting quickly rather than long-term maintainence. (worse)

It is more important to be able to account for all possible configurations than
to make it easy to set up and deploy in the common case. (better)

Low-variance in all metrics is more important than high-performance because
there are ways to get performance out of low-variance systems through scaling.
(worse)

Premise: javascript is C in the "Worse is Better" paradigm.
Goal: extract learnings from "worse" programming systems that won. Identify
properties systems should aim for and avoid.

Properties to aim for: virality, easy on-boarding, robust packing and deployment.
Properties to avoid: designing up-front instead of designing for flexibility.

----------------------------------------------------------------------

Javascript: the bad news, the bad news and how to Go big. (Worst is Best)
OR Programming systems beat programming languages

- C and Unix are the ultimate computer virus

php
perl
javascript
go

The core value of the a worse-is-better is prioritizing implementation
simplicity above all other values including correctness, consistency, and most
of all completeness. This provides a couple of technical advantages that sum to
a social advantage. The first technical advantage is that implementation
simplicity allows for very quick turnaround between recognizing a problem and
producing a candidate solution. In addition, the implementation simplicity
makes it very easy to iterate quickly on the solution in order to converge on
a mostly correct solutions to problems that matter more quickly than more
thorough and correct --that is to say better-- solutions. The first social
benefit this provides is a userbase, when a half-baked solution becomes widely
used quickly, it becomes a crucial piece of infrastructure that is hard to
remove and through its ubiquity, often becomes a more thoroughly-baked solution
as people devote resources to patching over its holes. TODO(chas) there is
a second social factor, but I forgot it.

Since the original publication of "Worse is Better", the consumer internet has
exploded and changed the face of software development in ways that make worse
better than ever.

Before discussing the specifics of this change, it is important to clarify
terms. When actually programming, no one purely interacts with a programming
_language_, instead they are operating a programming _system_. A programming system
is the whole interface used when programming: the language itself, the package
manager, the build system, the editing tools, the device being programmed, the
testing and verification system, the tools for code manipulation, the
deployment and monitoring environments, anything that interacts with the code
is a part of the "programming system". Programming system discussion is
inextricably tied to any discussion of a programming language because
a language doesn't exist outside of it's system except in the most academic of
discussions. Programming languages are the UIs of programming systems.
A language doesn't have one system, and a system doesn't necessarily have one
language, but strong cultures develop around each programming system.
Programming systems much like other cultures tend to be very strongly tied with
particular time and places. So, instead of thinking about "programming
languages" let's think about "programming systems". When it comes to
"programming", the system has become much more important than the language.

Some examples:
-LISP, emacs, lisp machines, CLOS, DSLs, explicit use of code as data, MIT, better is better.
-C, text editors, make, Unix, diff + patch, email, New Jersey, worse is better.
-Haskell, hackage, cabal, category theory/algebra, quickcheck.
-Perl, CPAN, cgi-bin, unix, TMTOWTDI, system administration.
-Go, gofmt, go, go get, godoc, distributed systems.
-Javascript, web browsers, the DOM, selenium, HTML, CSS, UI.
-Javascript, node, npm, github, concurrent web services.

DO INTRO BASED ONE WORSE IS WORSE ANALYSIS:
-- default language on system
-- right place for the cost constraints

C and LISP went through their early evolution in an era before the internet and
distributed development as we know it know. Since then, the type of software we
build has changed, moving from largely single-computer installations with
a single-user or local client-server model to a single-computer global
client-server model (early internet) to a model of commodity
distributed-systems serving global clients (recent internet and "cloud"
computing).

This, coupled with an exponential explosion in computing power, has added
dimensions to the considerations around programming system design and adoption,
namely, deployment, packaging, and monitoring. The expectations of software
that were present when "Worse is Better" was written are still present, but the
presence of tools to make programming in the ever-larger possible now
potentially swamp language concerns.

By co-opting a document publication medium and turning into the building blocks
of applications, modern web development has guaranteed significant duplication
of effort between projects in order to reimplement a standard suite of basic
features that almost all projects require. Perhaps the most popular of the
early languages coupled to the web, PHP, exemplifies this. The name it was
first released under, Personal Home Page Tools, emphasizes its specific role:
it let people who could make HTML pages

Further, it provided extremely easy deployment onto shared hosting, making it
nearly trivially easy to develop a website with a text editor and FTP client
and let its features grow with the comfort of the developer, one mysql_query at
a time.

Into the current day, `git push heroku master` makes it very easy for small-scale
work to get off the ground.

In addition to the quick deployment of small systems, large distributed systems
are often designed so that the health of the system is independent of the
reliability of any particular node and the system being programmed is much
larger than a single process on a single machine. So error-prone programming
models can be allowed to be flaky in any number of ways without seriously
harming the ability of the system to do its job. Monitoring tools then take up
the slack that a compiler could be capable of in a more sophisticated language
and check for problem conditions that programming systems that were optimizing
for per-node quality aren't aware of.  This means that languages which are not
expressive are less harmful to work in because the core complexity is in the
coordination and maintainence of the system rather than in any particular node.
Additionally, a language that is less productive on the per-node level can
become more productive by being very well designed for deployment, allowing
large distributed systems to be created and updated efficiently.


Additionally, from the perspective of 1989, the Free Software movement has been
overwhelmingly successful, and the

example
explanation
explanation

example
explanation
explanation

It is an interesting aside (is it though?) that the the most popular platform of
the web, Linux, won out over GNU HURD in a particularly worse-is-better manner
whereby a monolithic kernel that was "NOT portable..." and "probably never will
support anything other than AT-harddisks" beat the much more technically
sophisticated GNU HURD.


The rise of the open source movement.

Licensing issues and accidental ubiquity.


Development via copy-pasta and Stack Overflow.

With that in mind, there are two more examples of systems being more important
than language in a worse-is-better (or maybe system-is-better) way:

In the era of the early web immediately after the publication of worse is
better, two programming systems became prominent that exemplified the new
worse-is-better strategy:

Perl, CPAN, and the cgi-bin internet. Leveraged sysadmin knowledge and code
reuse. (This might be an example of best-is-best depending on your perspective)
Could also be interesting to look at how C++ supplanted C using the same
worse-is-better tricks C used in the first place. (Cfront starting as
a C preprocessor, choosing backwards compatibility over "the right thing")
Richard's follow-up essay Worse is Worse explicitly states a few points that
I think are relevant to this discussion. ("within the context of the
worse-is-better systems, these system were the right thing")

PHP and the LAMP stack - Lack of barrier to entry, easy on-ramp. Very very easy
development and deployment story. Lots of available examples for copy-paste
coding. (PHP's package manager is Google) Great documentation with
user-contributed notes

Worse is the Worst
==================
Java and the JVM and how it became ubiquitous in
enterprise development - strong deployment and monitoring tools, code
maintenance via IDE. Also interesting because of the current reuse of the
system while attempting to switch out the language (Clojure and Scala are
actually getting traction) (won on deployment, but also on marketing, boooo marketing)

In this sense, go is a worst is best language *par excellence*. The language
itself embraces a deliberately trailing-edge featureset in order to ensure that
the language itself is deeply approachable for anyone with a mainstream
programming background. The compiler is optimized for programmer iteration
speed. This produces a substrate on which a strong programming system can be
built

Being the default language of the system.  What sort of people use these
systems? (Lisp is used by weirdos who do weirdo science, Haskell "requires
a computer science PhD") Being affordable for the common person and the role of
the host computer. PHP and shared hosting are deeply related to this in
a modern way. Unstated here is the understanding that today's cheap shitty
thing only taken seriously by amateurs is tomorrow's industry-standard
platform.  Avoiding buggy complexity is the right thing. Go very strongly
supports this point.  Winning by default ("there was never a head-to-head
competition between a right-thing solution and a worse-is-better one") LAMP
stack is relevant here, many people never knew another way to get code on the
internet.

The domain and codomain of "worse is better" are different. Sometimes worse is worse and sometimes better is better. Make a two-by-two.

Unix and C are not disjoint from the worst is best languages. Diff and patch came from C and Unix, this is a package manager and code distribution tool. Email is the substrate.
