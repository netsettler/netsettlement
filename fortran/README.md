# Fortran-to-Lisp Translator

## Overview

This directory contains scans of various hardcopy bundles that I had
kept, related to a Fortran-to-Lisp translator that I wrote as part of
an undergraduate thesis project at MIT.\
&emsp;&mdash;_Kent Pitman_ (23-Jun-2026)

[A paper about the translator](https://www.nhplace.com/kent/Papers/Fortran-to-Lisp.html)
was presented at the Macsyma Users' Conference in June, 1979, Washington, DC.

## Origin Story of the Fortran-to-Lisp Translator

I joined the group maintaining
[Macsyma](https://en.wikipedia.org/wiki/Macsyma) in fall of 1977,
doing part-time work through the MIT Undergraduate Research
Opportunities Program (UROP) to help pay my way through college,
something that's not really feasible in the modern world, but
almost was back then.

Not long after I started working with the Macsyma group, I was
assigned a desk in an office with
[Guy Steele](https://en.wikipedia.org/wiki/Guy_L._Steele_Jr.)
and
[JonL White](https://lisp50.blogspot.com/2008/10/jonl-white-will-speak-at-lisp50.html).

I was going to need a thesis for my planned degree in Electrical
Engineering (course 6, as MIT people called EE; more specifically,
course 6.3, which was what amounted to a computer science degree).
At some point, a suggestion emerged that my thesis project should
be the writing of a Fortran-to-Lisp translator, so that Macsyma
could have access to the IMSL Fortran Library from within Maclisp,
the language that Macsyma was written in.
[Mike Genesereth](https://en.wikipedia.org/wiki/Michael_Genesereth),
who was part of the Macsyma group at the time,
was my thesis advisor.

I continued to do paid work for the Macsyma group on other matters,
but the work on the Fortran-to-Lisp translator is something I paid
MIT tuition for the privilege of doing.

Also, since I had an office with a link to a computer&mdash;which was
unusual for an undergraduate&mdash;I spent a lot of time there unpaid, just
because it was both fun and educational and I felt useful. The
writing of _The Revised Maclisp Manual_ (a.k.a. the &ldquo;Pitmanual&rdquo;) 
was one later result of that.
[That story has been told elsewhere.](https://maclisp.info/pitmanual/history.html)

Eventually, though, I opted for a degree in Philosophy and
Linguistics (course 24 in MIT-speak), which did not in fact
require the writing of a thesis.
But I _did_ finish the coding work for what was to have been
my thesis, and created a way for people to
access the IMSL Fortran library. I wrote the work up in a paper
unsurprisingly titled
[A FORTRAN&rarr;LISP Translator](https://www.nhplace.com/kent/Papers/Fortran-to-Lisp.html)
that I presented at the 1979 Macsyma Users Conference.

After graduating MIT in 1981, I worked at the MIT AI Lab and, for a summer,
the UK's Open University on unrelated projects. But in 1985,
I took my first salaried commercial job at
[Symbolics](https://en.wikipedia.org/wiki/Symbolics#History)
to work again on Macsyma, which Symbolics had turned into
a commercial product. However, the IMSL relationship that Macsyma
had enjoyed while at MIT did not 
carry over to the Symbolics endeavor, and if it had,
Symbolics had its 
own native Fortran implementation, so my work there was not on
the translator. I did other things.

George Carrette (original creator of
[SIOD](https://en.wikipedia.org/wiki/SIOD), and generally a very smart
guy and prolific Lisp programmer) was part of the Macsyma group at MIT
when I first met him. He was a big fan of the translator and went on
to use it on other operating systems with good success, so it did see
a life beyond its original intent.

## Macsyma and the Macsyma Group

[Macsyma](https://en.wikipedia.org/wiki/Macsyma) is one of the oldest
computer algebra systems.

The team that developed and maintained it worked on the 8th floor of
MIT building NE-43 (545 Tech Square).

The work was done on the MC (Macsyma Consortium) computer, a PDP-10
mainframe computer made by Digital Equipment Corporation (DEC),
running an MIT-created/maintained operating system called ITS (the
Incompatible Timesharing System). To the outside world (the ARPANET),
this machine was generally known as MIT-MC. (There were no dots in
host names on the ARPANET, as the total number of machines was
[quite finite](https://upload.wikimedia.org/wikipedia/commons/b/bf/Arpanet_logical_map,_march_1977.png). There was eventually an internet host named
mc.lcs.mit.edu,
for example. But in the late 1970s and early 80s, such fine-grained parsing
was unnecessary to an ARPANET
with only a few hundred computers at all.)

The Macsyma Consortium was part of
[Project MAC](https://www.britannica.com/topic/Project-Mac),
which later became MIT's Laboratory for Computer Science, and which at the time
was separate from the MIT AI Lab. (Later the two entities merged into a
consolidated [CSAIL](https://csail.mit.edu).)

(Note, too, that Project MAC has no relation at all to Apple's
Macintosh computers, which came much later.)

## Why So Many Versions

There was severe pressure to conserve disk space. So even though we
had a versioned file system, in practice we couldn't keep many old
versions. As such, I often had the practice of hardcopying my files
before deleting them, and I saved a lot of that hardcopy. In 2026,
I finally scanned a lot of that back in. That's what you find here.

The bundles are organized first by date, then by numbered version, as
in `Fortran.1980-06-27.213.pdf` which is my translator's version `213`
from `1980-06-27`. (In one case, `Fortran.1980-12-22.pdf`, a version
number was not available, so is omitted in the name, but ordering by
date means it still sorts properly in a file listing.)

There were a number of reasons for that naming structure, with date
before version, but most especially:

* The file system didn't have subdirectories, so there was no
  file-system-level grouping helping me organize files that
  worked together. Likewise, we did not have anything like git.
  I did at some point create a tool that would delete files for
  me and keep a record of what was deleted. There might be data
  I can lift from that sometime. But that data was not separated
  by project.

* The mechanism for holding onto version numbers for the application
  as a whole was originally just assigning a particular variable in
  one particular file of Maclisp code. This meant that if I wrote new
  versions of any other files (it was a file system with versions,
  so reading in `FOO >` would get me perhaps `FOO 3` and writing
  it back would make a `FOO 4`), the file containing the variable
  with the application version didn't notice the changes to the
  supporting files.

  We did not have DEFSYSTEM, a Lisp tool for
  organizing sets of files into systems and managing things like
  versions of a system and numbered patches to it. That tech
  originated on the Lisp Machine, and initially
  I was mostly working on the MIT-MC PDP-10 in Maclisp.
  So I had to create an ad hoc mechanism for versioning.

  Actually, for the final and most-likely-complete set (dated
  1980-12-22), I had changed my ad hoc system versioning to be
  something a bit more clever,
  where every time I dumped a fresh executable with all of the
  functionality of the translator pre-loaded, my homemade dump
  tool bumped the version and
  put that number in an outboard file. Unfortunately, the final
  bundle, the one that uses this better mechanism, does not contain
  the very outboard file that would have offered the version info
  to go along. Oh well.
  &ldquo;The best laid plans...&rdquo;

* I cannot account for why in one case the numbers do not increase
  monotonically. The files `Fortran.1978-11-12.120.pdf` and
  `Fortran.1978-12-17.102.pdf` highlight this problem. Why was the
  12 Nov 1978 PDF numbered 120 but the 17 Dec 1978 PDF numbered 102?
  All I can say is that I checked this several times and that's
  how it seems to be.

So I think the file dates give a more reliable clue and hence I chose
to put them earlier in the file name than the version to make things
sort by time, which I'm assured by physicists does increase
monotonically (even if frame of reference might affect my perception
of flow outside my inertial frame&mdash;these files have been through
quite a journey to get here, but nothing that would implicate that).

More particularly, what I did was to look at the most recent file date
I could find in the set. (The files are not OCR'd yet, so even that is
error-prone, but I looked at the file date on each file, which either
came from the top of each page of file content or from a cover page.)

I assumed that the files were probably printed all on the same day,
though they may have been printed one-by-one and that might not literally
be true. (I did find collected sets of files in some of my archiving where
this assumption is violated. But, in general, when I was doing a big
  set to save,
I understood the need to have a coherent set of files, so I probably
tried to get it 'adequately close'.)

So I think these bundles represented either coherently loadable sets
or at least partial sets that were trying to work together. The sets
where I'm less certain were often looseleaf bound, and I've notated
that fact. For those, listings could be added/removed at any time, and
that makes it less sure.  But if I took the time to velobind them, not
an automatic process, and not done at some copy shop, but something
that took patient manual labor to do, it was probably that I was
seeking to make something reasonably consistent so that I could place
it in a kind of time capsule for a then-future purpose, such as the
archival project you're reading about now. The main problem is that
there was no tool tracking whether the set was complete, and we have
to hope I really got all the relevant files.

Even though the file dates differ, I suppose that the files I chose were
the most current as of the time when I made the effort to collect them
together, or else if there'd been a more recently dated file,
I'd have included that one instead. It's all just a hunch, but it's
better than nothing.

## Caveats

Some of these collections are just bundles of individual files that
are not properly possible to think of as a coherent system, but I
thought they might still have some historical value, so I brought them
online, imperfect as they are. Others seem like they might conceivably
be coherent versions someone could make run, or at least study
coherently.

### Do Any of These Bundles Actually Work?

The translator definitely did work quite solidly back in its day. Do
any of these represent enough puzzle pieces to reproduce that? I hope
so. But I can't make a promise.

Also, at least for now, these PDFs are just page images. No OCR has
been done. As such, getting text out of them that anyone can even try
to read into a Lisp would be a project in itself. (Google Chrome, for
example, will do a crude OCR automatically if you view a PDF at all,
but, in my experience, their free OCR tool makes a lot of mistakes and
has no concept of headers and other artifacts. And anyway, I could not
see a way to save the resulting text annotation back out into a
PDF. It just saved the same file as I'd opened.) If it's a project
you're inspired to undertake in a way that collaborates in a
synchronized way with this historical archive, feel free to
[contact me](https://nhplace.com/kent/contact-kent.html).

## Background on Filenames

The ITS filenames had four parts. Each part could have 1 to 6
[DEC sixbit](https://en.wikipedia.org/wiki/Six-bit_character_code#DEC_SIXBIT_code)
characters in its name. This implied uppercase.
Use of lowercase was assumed to imply the corresponding uppercase.
Some filename parts were positional, while others were marked with a
trailing character, allowing greater positional flexibility.

 * optional device (ending in ":" if it appears) DSK: means local
   disk, though if the local machine is MC, MC: and DSK: would be
   the same. Even in the 1970s, the four ITS machines (MC, ML,
   AI, and DM) had a networked file system and all knew about each
   other, so a filename MC: could be used on any of the 4 ITS machines
   and would be accessed as from the MC machine. Likewise for ML: and
   AI: and DM: so that's why you often see that instead of DSK:

 * an optional directory (ending in ";" if it appears).
   There were only 512 directories possible,
   a compiled-in parameter of the operating system that was not possible
   to change. So MC: KMP; would be KMP's home directory on the MC machine.

 * a "first filename" (or "fn1") is just six characters, and needs no
   marker.

 * a "second filename" (or "fn2") is space-separated from the
   first filename. Typically, the fn2 was a numeric version or a word
   indicating a type. It could not be both. A filename ">" would read
   the greatest number and write the next higher version. So if file
   FOO 1 appears in the file system, reading FOO > into the editor would
   read it in, and writing FOO > would write FOO 2.

In this repo, I've created files that really don't match the ITS convention,
but there are some files where you might want to know about these filenames.

 * In files like x.y.z.metadata.txt, you'll find metadata descriptive info
   related to x.y.z in this same dir.

 * In files like x.y.z.manifest.txt, you'll find information on the ITS
   filenames (and often specific versions) that are to be found in these
   scans. In most cases, the scans have cover sheets and headers that 
   mention these filenames.

You may also see references to Lispy notations for files in the ITS
file system, allowing for `(load '((dev dir) fn1 fn2))`, for example.
This [namelist](https://maclisp.info/pitmanual/files.html#Namelist)
format is detailed in _The Revised Maclisp Manual_.

## About Lisp Style

The programming styles in these files are pretty poor by modern
standards. I blame that partly on me being new to large scale
programming. Partly Maclisp was just messy to program in. Let's just
say I'm not advocating a lot of it as good style to copy today. I
personally, and we as a community, evolved better coding style over
time.

Some of that, too, was the [Maclisp](https://maclisp.info/pitmanual)
language itself.

* Slash, not backslash, was the syntactic
  quoting character, so `//` is the division operator and is a single
  slash. Backslash was an ordinary character. This meant it was common
  for newbies to write  
  `(/ 8 2)`  
  and be confused about why the
  error message was about an unknown function `| 8|`.

* Maclisp defaulted to base 8. Most code would do  
  `(setq base (setq ibase 10.))`    
  but it was still good to be careful.

* There wasn't a character datatype in Maclisp, but people knew ASCII
  codes. `(TYO 32.)` would be well-understood to mean &ldquo;output a
  space to the terminal.&rdquo; It wasn't until later that `#/` (the
  Maclisp equivalent of Common Lisp's `#\` character notation) was
  invented. But that wasn't until after the all-purpose sharpsign
  readmacro had been created and socialized for debate before
  eventually being distributed it with Maclisp as a pre-loaded
  feature. (Unlike Common Lisp, which has been quote semantically
  stable since its standardization, Maclisp was notorious for almost
  weekly "breaking changes".)

* Maclisp did not have strings. For most purposes where you'd use strings for
  today, quoted symbol names (often written inside vertical bars) had to suffice.

  As a result of this, to test parts of strings, one had to "explode"
  a string into a list of its characters as either numeric codes
  (using [EXPLODEN](https://maclisp.info/pitmanual/charac.html#EXPLODEN))
  or one-letter symbols
  (using [EXPLODEC](https://maclisp.info/pitmanual/charac.html#EXPLODEC)).
  It was hard for that not to be ugly.

* Maclisp for a long time did not have the FORMAT function, so you see
  a lot of tedious expressions of a general form like this instead:
  ```
  (PROGN
    (PRINC '|The value of |)
    (PRIN1 VARNAME)
    (PRINC '| is |)
    (PRIN1 VARVAL)
    (PRINC '/.))
  ```

There were many other odd features of Maclisp that would seem archaic
now, but these are particularly dominant in the translator, which
did a lot of "string" manipulation when parsing Fortran code
and writing output files, as well as managing I/O to the terminal
in its user interface.

## On the Absence of License Metadata

There are no `.license.txt` files here, nor did I make any
corresponding adjustment to the `LICENSES/` directory at the root
of this repository.
That is because the intellectual property issue is complicated,
and I've opted not to even attempt to sort things out definitively.

I will, however, make some observations that you can think of as
conversation starters for any future person who tries to 
undertake such a Herculean task. :)

It was customary for Macsyma
to include a copyright line in its source files 
and I almost certainly automatically 
included such a line to accommodate the normal look and feel
of Macsyma source files, without understanding its full
legal implication.
However, I recall no publication step for Macsyma sources,
like there was with
[the fiasco
with the Pitmanual](https://maclisp.info/pitmanual/history.html),
so I don't recall ever being presented a document
in which I was meant to expressly 
yield my intellectual
property rights to MIT.

It's also my recollection that the general 
respectful handling
of intellectual property rights of students writing such code
was something that was
evolving over time. I think the fact that it needed to be considered
was only a creeping realization, or at least that's what it seemed
to me from how I saw it handled over time in different situations involving
thesis work by other people, for example.
Matters also became
simpler when computer prices came down enough that ordinary mortals
could do real computation without paying a true fortune, so the 
separation could be made more cleanly.

And the
situation was further complicated by the fact that
my work was my own, but done on government-funded computers.
Maybe that means the government had some intellectual
property interest, too. I'm not
sure of the terms of the funding. But as a taxpayer, I have to say I
hope that the fact of government funding doesn't leave me poorer by retaining
no rights to the citizens paying for that funding. 

I would hope the
terms MIT worked out with the government for what was developed
were pretty liberal (like
the MIT license later came to be). I am not asserting that an MIT
copyright notice means an MIT license automatically applied here, 
just that I think it would be a compromise position I'd probably argue
for if I were trying to figure one out. Or, put another way, it's a
compromise that would satisfy my personal needs.

With a tool like this translator, as old and long dormant as it is,
it's far too easy to mindlessly assert rights 
without having any goal in mind beyond virtue-signaling and puffery
to show one did
one's abstract job of "protecting rights" from general encroachment,
and in so doing to just stop
legitimate use dead in its tracks because no one 
wanting to invest in the making of new and experimental 
uses also has the resources to
fight large batteries of corporate lawyers over possible benefits
that are at best speculative. In effect, at that point, intellectual property rights 
become nothing more than the right to keep others from succeeding
at something one never had a goal to succeed at themselves. There 
may be a sense of power in that, and it may be a legal right, but there
is no moral authority in that whatsoever, and it does damage to the
legitimate investment of others. So I hope that isn't how it later
resolves and I want to be on record as strongly as possible as saying
that is not only a bad outcome but a general pattern that no court
should ever sustain. 

Copyright lasts way too long, and in situations
where a stakeholder has asserted not the slightest interest in using
such rights until someone else does the hard work of reviving
something, the idea that it would not be obvious that the 
right thing is to allow a liberal license so that value is not simply
lost is repugnant to me. There most certainly do exist rights that
can be used in such a way as to stop things dead in their tracks,
but I am offended by that fact.

Just in case you wondered about my opinion, both as the original
author and, separately, as someone who has invested time and energy
in the curation of these items.

But definitively resolving such a messy situation was too complicated
for me to attempt as I preserve this historical record,
and that's why I am steering clear of offering even summary advice
about how intellectual property can practically be construed here.

I am raising only questions, not answers. And, yes, I'm hinting
(loudly) my personal bias. I don't mean to assert the
unique correctness of my point of view. But this is my metadata,
and I'm not going to waste it by failing to say that I do
have a point of view.
As happens to all of us, I'll be gone at some point, and this
might as well record my thoughts.
Others have the entire Internet
on which to
voice alternative positions.
And I could certainly 
imagine other reasonable positions
being advanced, I'm just not sure what they might be. If I could,
I would have added them to my mulling here, if for no other reason
than to be able to then respond to them.

Meanwhile, I'm just trying
to put the data into some form that survives long enough for even
those questions to matter. :)
