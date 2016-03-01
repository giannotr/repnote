# The `repnote` package

This package is meant to make indipendant the well known feature of
pointing several footnotes to the same anchor
present in the `scrartcl` and `memoir` classes
while adding more flexibility and funtionality than the present packages
that tackle this task: `footmisc` and `fixfoot`.

The first major change is a patch of the `\footnote` macro
that can be used as usual furthermore, so the solution is completely backward compatible.
`\footnote` now is just called with an optional third argument
in which the user declares a unique labelname to which he points with the
core macro `\repnote`, i.e. `\footnote[number]{text}[labelname]`.

Then a simple `\repnote{labelname}` would replicate the footnote mark.
`\repnote` does not have any optional arguments.

It is possible to define a static footnote vis `\DeclareRepeatedFootnote`,
i.e. `\DeclareRepeatedFootnote[format]{macroname}{footnotetext}{labelname}`.

Yet there aren't any known incompatibilities with other packages or loading order concerns.
`repnote` relies only the `kvoptions` package,
which presumably is present in every TeX distribution.

The package is invoked as usual employing the `\usepackage` command:

    \usepackage[options]{repnote}

The only option available is 'reprint' and its values are boolean.
There are also the synonyms 'reprint' for "reprint=true"
and 'noreprint' for "reprint=false".
This option specifies if the anchor footnote should be reprinted
while entering a new page.

This is version 0.1 of the package.

Copyright (C) 2016 by Ruben Giannotti 
<ruben dot giannotti at gmx dot net>

---

This work may be distributed and/or modified under the
conditions of the LaTeX Project Public License, either
version 1.3c of this license or (at your option) any
later version. The latest version of this license is in
  http://www.latex-project.org/lppl.txt
and version 1.3 or later is part of all distributions
of LaTeX version 2005/12/01 or later.

This work has the LPPL maintenance status `maintained'.

The Current Maintainer of this work is Ruben Giannotti.

This work consists of the files
  repnote.dtx 
  repnote.ins
and the derived file repnote.sty.


To install the package

 1. run `latex repnote.ins`
 2. move 'repnote.sty' to locations where LaTeX will find it
