# Example document using the Arcada thesis template

An example LaTeX document using the [Arcada thesis template][template-repo]. This is also the documentation (@todo still need to write it), _Note currently only in swedish_

![Thumbnail](http://i.imgur.com/M7Tvs.png)

## Getting started

Check out [the template README][template-readme] for dependency and install instructions.

The documentation for using this template is the output of this example, you can either build it yourself or [read it online][document-pdf].

The easiest way to get started is to fork this repository and start looking at the code and how it works. Once you've had a look you can simply delete all files within `chapters/` and remove the `\input{chapters/**}` lines in the document.tex file.

### How this example document is structured

There are several ways you can use the template, one way is to just download the tar-ball and use the thesis.cls as you documentclass within your own .tex document. I prefer a workflow which is a bit more complicated to set up but a lot more structured as well.

1. Keep the document version controlled! This is as simple as forking the repository and cloning your own version.

2. Keep the [arcada-thesis-template][template-repo] in a submodule so you can update it in case of bug fixes. Pulling updates is as simple as `git submodule update`.

  If you feel like you need to hack something, please file a bug and I'll look into making possible without hacks.

3. Use the [Makefile][makefile] provided in this example and modify it to do whatever you want. Eg. running automated tests on the code examples in your theis or maybe writing some chapters in markdown and then compiling them into latex?

  With the example makefile running `make` would:
  * Replace åäö with the escaped versions within your .bib file.
  * Run bibtex to create your bibliography.
  * Create a pdf version.

  *There's also a `make clean` command to remove the build scraps.*

4. Split your document into as many parts as you see fit. Personally I like a clean main .tex which then includes all chapters and special pages etc.

  To do this you can create a .tex file somewhere and then use `\input{path-to-file-without-tex-extension}` to include it in your main document.


### Files

* `document.tex` The main document which ties all other files together.
* `references.bib` The reference database, used by [BibTeX][bibtex].
* `settings.tex` Contains your personalized variables used throughout the document.
* `Makefile` The build file used when running make.
* `template/thesis.cls` The thesis document class which is imported in document.tex
* `pages/*` All custom pages within the document, ie. abstracts, appendix, tables, title.
* `chapters/*` The documents content.

## Resources

* [BibTeX][bibtex], HOWEVER, the thesis is using a heavily modified version of the usual fields and types. You should refer to the documentation on what fields and types are available.

* [The Not So Short Introduction to LaTeX 2e][lshort], awesome guide to LaTeX.

* [Wikibooks LaTeX][wikibooks], an easier reference than the above.

* [CPAN contrib][cpan-contrib], all packages contain documentation files which are very helpful when you need to customize something.

[cpan-contrib]: http://tug.ctan.org/tex-archive/macros/latex/contrib
[wikibooks]: http://en.wikibooks.org/wiki/LaTeX/
[lshort]: http://tobi.oetiker.ch/lshort/lshort.pdf
[bibtex]: http://en.wikipedia.org/wiki/BibTeX
[makefile]: https://github.com/oxyc/arcada-thesis-example/blob/master/Makefile
[template-repo]: https://github.com/oxyc/arcada-thesis-template
[template-readme]: https://github.com/oxyc/arcada-thesis-template#getting-started
[document-pdf]: http://cloud.github.com/downloads/oxyc/arcada-thesis-example/document.pdf
