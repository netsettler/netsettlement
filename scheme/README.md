# Scheme artifacts

These files are not all part of a single collection. There are some
that are related, but I'll add some metadata here that spans
multiple files and isn't appropriate to one specific file.
&emsp;&mdash;_Kent Pitman, 1-Jul-2026

## About individual files

### `*._notes-on-scheme-error-integration.pdf`

There are several of these files, at intervals, as if I was developing
something.  The filenames change, but the content seemed to be
evolutionary versions of the same thing.

As nearly as I can reconstruct, this was part of thinking through what
CL errors might look like if cast into Scheme. I don't know if this
got used or not.

On more than one occasion, I mulled how to integrate something like
the Common Lisp (CL) condition system into Scheme.  If memory serves
(and it doesn't always), I had an extensive discussion with Dan
Friedman about such an integration. I think he had his own ideas and
was going to write a book on this, or perhaps had already done so.
While I did try my best to cast things into Scheme way of doing
things, I think he had some slightly different ideas. So I don't know
which way things went after that.

Note in particular, though, that this code is written using DEFINE,
not DEFUN, so that's already identifying it as Scheme, not Common
Lisp. (There are some files that have Common Lisp references only
because I was cheating and prototyping in CL something that used
Scheme notation, but I'm very confident that CL was not the target of
anything other than my personal debugging.) But it also uses OBJECT,
which is a special form that was particular to T (Yale Scheme).
(More on T in the `Background` section of this `README.md` file.)

### `*._other-notes-on-scheme-error-integration.pdf`

This is a similar kind of thing, but I think not part of the same series.

There are some handwritten notes at the end of this. They seemed like maybe
part of the same thing, but maybe not. There is one file that is half printed
and has some similar scribbling.

### `t-yale-*.pdf`

Some files related to Yale Scheme, perhaps from about 1986 sometime, based
on the content of the announcement file.

### Other files may be coming

There may be some additional files that belong here that I have not
yet checked in because I'm still researching details.

## Background

### About the T Language

The T language (a.k.a. "Yale Scheme") has
[a Wikipedia page](https://en.wikipedia.org/wiki/T_%28programming_language%29)
that offers useful information.

In particular, it describes the `OBJECT` special form (macro) that you see
used in some of the coding examples in this repository. This operation is a
way of creating something that might be described as an instance of an
anonymous class description, in the same way as `LAMBDA` creates a single
lexical closure that is an anonymous function.

Jonathan Rees maintains [The T Project](https://mumble.net/~jar/tproject/)
web page with a bit more information and a picture of some of us.

#### My (Kent Pitman's) Participation

For the record, it was Jonathan's project from the start. He invited
me to join and I said I could spend a summer helping it get going.
Much of the surviving work from that summer is his compiler.  I wrote
an emulator for prototyping on a TOPS-20 machine that I imagine got
lost somewhere. I don't think I have a copy (though I'm still not 100%
sure).  Norman Adams joined a little while later, overlapping with me
a bit, and eventually others joined, but by then I was gone.  Still,
there are a few major language-level features of T that I either
designed or contributed to. It was a fun summer.

#### T Trivia

The T language was sometimes criticized for having a
one-letter name, as if no serious language would ever do that. (It's
OK if you need to take a second to ponder if that's really so.) In
response, someone came up with the alternate name "TEA" (T with
Extended Acronym). I don't think a homonym with more letters would
have satisfied anyone, but it did _technically_ answer the criticism.
We never officially changed the name, but at least we had the option
in our conversational quiver in case of subsequent criticism.

### Other Conditions Work Elsewhere

It seems [MIT Scheme at some point got
a condition system](https://www.gnu.org/software/mit-scheme/documentation/stable/mit-scheme-ref/Error-System.html),
but I have no special reason to suppose it was based on any of my doodling here.
The shape of it does not look like the shape of what's in these files,
especially for lack of the T `OBJECT` operation.
It might have come from the CL system or just as plausibly they might
have repeated what I did in the CL condition system and patterned
things after the Lisp Machine condition system. The same ideas were
available to a lot of people. I was a consumer and repackager of such
ideas, but there could very easily have been more people doing the
same.

There is also [SRFI 35: Conditions](https://srfi.schemers.org/srfi-35/srfi-35.html)
by Richard Kelsey and Michael Sperber.
Note that Kelsey worked on T (Yale Scheme),
writing a PhD on [Compilation By Program Transformation](https://mumble.net/~kelsey/kelsey-diss-2012.pdf),
so that cultural heritage _might_ be relevant here.
But it's probably just coincidence.
The shape of the interface suggested by this SRFI does not look like
what I wrote here. 

Probably the condition system code I scanned here is just some lost
thoughts by me that have not much relevance to anything.
