# The `repnote` package

This package is meant to make indipendant the well known feature of
pointing several footnotes to the same anchor
present in the \cls{scrartcl} and \cls{memoir} classes
while adding more flexibility and funtionality than the present packages
that tackle this task: \pkg{footmisc} and \pkg{fixfoot}.

The first major change is a patch of the \cs{footnote} macro
that can be used as usual furthermore, so the solution is completely backward compatible.
\cs{footnote} now is just called with an optional third argument
in which the user declares a unique labelname to which he points with the
core macro \cs{repnote}, i.e. \cs{footnote}\oarg{number}\marg{text}\oarg{labelname}.

Then a simple \cs{repnote}\marg{labelname} would replicate the footnote mark.
\cs{repnote} does not have any optional arguments.

It is possible to define a static footnote vis \cs{DeclareRepeatedFootnote},
i.e. \cs{DeclareRepeatedFootnote}\oarg{format}\marg{macroname}\marg{footnotetext}\marg{labelname}.

Yet there aren't any known incompatibilities with other packages or loading order concerns.
\pkg{repnote} relies only the \pkg{kvoptions} package,
which presumably is present in every \TeX\ distribution.

The package is invoked as usual employing the \cs{usepackage} command:

\cs{usepackage}\oarg{options}\{repnote\}

The only option available is \optn{reprint} and its values are boolean.
There are also the synonyms \optn{reprint} for \mbox{\enquote{reprint=true}}
and \optn{noreprint} for \mbox{\enquote{reprint=false}}.
This option specifies if the anchor footnote should be reprinted
while entering a new page.
