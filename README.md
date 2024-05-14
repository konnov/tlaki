# TLAki: Little cute typed definitions in TLA<sup>+</sup>

This project contains alternative definitions of commonly-used data structures:

 - [Lists.tla][] are typed 0-based sequences of elements, as an alternative
   to untyped 1-based [TLA+ Sequences][].

 - [Tuples.tla][] are typed constructors for [TLA+ Tuples][].
   When using these constructors, you do not need additional type annotations.

Our goal is not to replace the standard constructs of TLA<sup>+</sup>, but to
provide specification writers with alternative definitions, if they need them.
If you are looking for TLA<sup>+</sup> definitions for all life circumstances,
check [TLA+ Community Modules][].

For example, too many people were wondering, why indices of TLA<sup>+</sup>
sequences start with 1? Why cannot they start with zero? The answer is simple:
They can, [Lists.tla][] contains definitions like that. To avoid name collisions
with [TLA+ Sequences][], we use alternative names that you can find in
programming languages.

## Examples

```tla
\* with Sequences
<<1, 2, 3>>[2] = 2
<<2, 3>> \o <<5, 6>> = <<2, 3, 5, 6>>

\* with Lists
At(List(<<1, 2, 3>>), 1) = 2
Concat(List(<<2, 3>>), List(<<5, 6>>)) = List(<<2, 3, 5, 6>>)

\* standard TLA+: a triple is also a sequence
<<5, 6>>
<<1, 2, 3>>

\* with Tuples: a triple that is definitely annotated as a tuple
Pair(5, 6)
T2(5, 6)
T3(1, 2, 3)
```

## Name

How to pronounce TLAki? [tee-el-ay-kee]. In my mother tongue, the suffix '-ki'
usually points to little or cute things, animals, or people. Like, in
[Pirozhki][].

[TLA+ Community Modules]: https://github.com/tlaplus/CommunityModules
[Lists.tla]: ./src/Lists.tla
[Tuples.tla]: ./src/Tuples.tla
[TLA+ Sequences]: https://apalache.informal.systems/docs/lang/sequences.html
[TLA+ Tuples]: https://apalache.informal.systems/docs/lang/tuples.html
[Apalache]: https://github.com/informalsystems/apalache
[Pirozhki]: https://en.wikipedia.org/wiki/Pirozhki