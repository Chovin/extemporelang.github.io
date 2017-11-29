---
title: about-this-documentation
---

# About this documentation {#about-this-documentation}

This documentation is generated using
[Sphinx](http://www.sphinx-doc.org/), using the
[rtd](https://github.com/snide/sphinx_rtd_theme) theme. Eventually we
might even host it at [Read the Docs](http://readthedocs.org), but
currently someone (usually Ben) generates the static HTML, and then we
host it on GH pages. Since it's all just
[reStructured](http://www.sphinx-doc.org/en/stable/rest.html) text files
in the `docs/` subdirectory, it's easy for others to contribute.

## Generating {#generating}

To generate these docs, you'll need a few python packages, something
like:

    pip install sphinx sphinx-autobuild sphinx_rtd_theme pygments

The docs are generated from the reStructured text (`.rst`) files in the
`docs/` subdirectory in the Extempore source distribution.

If you want to work on the docs locally (with a live-reload server so
that you can see the changes) you can use run `sphinx-autobuild` in this
`docs/` directory on your local machine:

    sphinx-autobuild . _build

To actually build the docs to host somewhere, use the makefile:

    make html

then take the generated output from `_build/html` and dump it on a
webserver somewhere---it's a self-contained static site.

Currently, we're hosting it on GitHub pages through the Extempore repo,
in a special `gh-pages` branch.

## Contributing {#contributing}

If you find problems, or can think of improvements, [fork away on
GH](https://github.com/digego/extempore), edit the documentation source
files and submit a pull request---we'd love these docs to become a real
community effort. There will probably be a few broken links and other
little things like that, so no pull request is too small to be
appreciated :)

If you've got questions, or want to bounce around some ideas for
improvements before you go ahead and make big changes then get in touch
on the [mailing list](mailto:extemporelang@googlegroups.com).

## ReStructured text cheat sheet {#restructured-text-cheat-sheet}

Since these docs use Sphinx, their [ReStructured text
docs](www.sphinx-doc.org/en/stable/rest.html) are the best place to
look, but here are a few quick reminders about the formatting of these
doc files.

### Sections {#sections}

Section headings are underlined, where the "level" of the heading is
determined by the character used for the underline like so:

    Section heading
    ===============

    Subsection heading
    ------------------

    Subsubsection heading
    ^^^^^^^^^^^^^^^^^^^^^

    Paragraph heading
    """""""""""""""""

### Source Code {#source-code}

For Extempore code blocks, use the `source-code` directive, then indent
the code block:

    .. source-code:: extempore

    (printf "foo")

### Links {#links}

External links should be done like this:

    You can `Google all the things!`_

    .. _Google all the things!`: www.google.com

You can make internal links to other parts of the documentation:

    if the documentation you want to link to lives in it's own top-level
    .rst file, you can use e.g. :doc:`quickstart` (use the fiename
    without extension in the target).

    If you want the link text to be something other than the title of
    the subpage, use e.g. :doc:`getting started quickly <quickstart>`

You can also add arbitrary link targets:

    .. _this-is-a-target:

    For more information, see :ref:`this-is-a-target`
