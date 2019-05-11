Case Studies
============

This repository showcases some examples of tricky Rust code that I have
encountered during my years working with a variety of advanced macro libraries
in Rust (my own and others').

<br>

## The point

This project is dedicated to the one profound insight about Rust macro
development: the difference between someone who is competent with macros vs an
expert at macros mostly has nothing to do with how good they are "at macros".

90% of what enables people to write powerful and user-friendly macro libraries
pushing the limits of possibility is in their mastery of everything else about
Rust outside of macros, and their creativity to put together ordinary language
features in interesting ways that may not occur in handwritten code.

You may occasionally come across Rust macros that you feel are really advanced
or magical. If you ever feel this way, I encourage you to take a closer look and
you'll discover that as far as the macro implementation itself is concerned,
none of those libraries are doing anything remotely interesting. If it is a
procedural macro, they always just parse some input in a boring way, crawl some
syntax trees in a boring way to find out about the input, and paste together
some output code in a boring way exactly like what you would learn in a few
hours by working through any part of my [procedural macro workshop][workshop].
If it is a macro\_rules macro, everything is conceptually just as boring but
when stretched to its limits it becomes a write-only syntax that poses a
challenge for even the author to follow and understand later, let alone someone
else not already fluent in the basics of macro\_rules.

To the extent that there are any tricks to macro development, all of them
revolve around *what* code the macros emit, not *how* the macros emit the code.
This realization can be surprising to people who entered into macro development
with a vague notion of procedural macros as a "compiler plugin" which they
imagine must imply all sorts of complicated APIs for *how* to integrate with the
rest of the compiler. That's not how it works. The only thing macros do is emit
code that could have been written by hand. If you couldn't have come up with
some piece of tricky code from one of those magical macros, learning more "about
macros" won't change that; but learning more about every other part of Rust
will. Inversely, once you come up with what code you want to generate, writing
the macro to generate it is generally the easy part.

[workshop]: https://github.com/dtolnay/proc-macro-workshop

<br>

## Focus

Yes, these case studies are drawn from use cases that arise from work on macros,
but the macros are never the interesting part. The ingenuity and sophistication
always lie in what Rust code ultimately gets emitted by the macro, and I think
you will find that those are fully possible to appreciate even if you know
nothing about macros.

To that end, I make an effort to minimize the role of macros in these case
studies. For each one I give only enough context about the relevant macro to
explain a set of constraints that the generated code will need to comply with.
The focus is on the generated code, which somehow solves the constraints using a
clever combination of Rust language features unrelated to macros. Lastly and
least importantly, I tie it back to the macro to point out that making a macro
produce the generated code we came up with would be the easy part.

<br>

#### License

<sup>
Licensed under either of <a href="LICENSE-APACHE">Apache License, Version
2.0</a> or <a href="LICENSE-MIT">MIT license</a> at your option.
</sup>

<br>

<sub>
Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in this project by you, as defined in the Apache-2.0 license,
shall be dual licensed as above, without any additional terms or conditions.
</sub>