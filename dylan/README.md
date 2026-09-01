# Dylan

## Overview

These are documents related to the history of 
[the Dylan language](https://en.wikipedia.org/wiki/Dylan_%28programming_language%29).

These documents do not necessarily correspond to anything modern.
As  with all of this repository, they are snapshots of interesting
state from long ago.

## One Person's Understanding of the History

Dylan was originally developed at Apple under the code name "Ralph" as a
Scheme-like alternative language for programming the Apple Newton.
I, and I think others, sometimes informally described this dialect
as being conceptually like Scheme + CLOS, though it attempted no
actual compatibility with either; that was more just a metaphorical
way of understanding the scope of the endeavor. 
One of its design documents is reproduced here.
It's a genuinely interesting
piece of design, and it's a shame that this version never saw the light of day.

Later, Apple collaborated with Harlequin on a revised design that
was intended to give disenchanted C++ programmers a place to go.
The redesign featured an infix syntax that was specifically hoped
to appeal to the C++ crowd, and to create distance from the Lisp
audience, which marketing people at the time worried would be 
off-putting to potential buyers. Unfortunately, Java came onto the
scene and stole all the oxygen that Dylan might have used, so
the revised Dylan did not appeal to either the C++ or the Lisp/Scheme
community in any large numbers and did not take the world by storm.

[Harlequin](https://en.wikipedia.org/wiki/Harlequin_%28software_company%29)
did produce a DylanWorks product. 
Apple produced [Apple Dylan](https://en.wikipedia.org/wiki/Apple_Dylan).

Dylan survives today as [Open Dylan](https://opendylan.org/index.html).

## Contained Documents

I'm not sure if the conditions proposal
was adopted or implemented, or what version was final if so.
These are just the artifacts that I had a record of.\
&emsp;&mdash;_Kent Pitman_, 2026-08-21

* A design document for Ralph,
  _Ralph: A Dynamic Language with Efficient Application Delivery_,
  July 25, 1991, by Andrew LM Shalit, Apple Computer, Inc.

  * [Ralph (1991-07-25)](ralph-1991-07-25.pdf)

* A proposal for a condition system for Ralph,
  _RALPH CONDITIONS (version 1.1)_ by
  David A. Moon,
  14 August 1991.

  * [Ralph Conditions v1.1 (1 of 2)](Ralph_conditions_proposal_by_Moon_v1.1_part_1_of_2_1991-08-14.pdf)
  * [Ralph Conditions v1.1 (2 of 2)](Ralph_conditions_proposal_by_Moon_v1.1_part_2_of_2_1991-08-14.pdf)
