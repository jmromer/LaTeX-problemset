problemset
==========

A LaTeX document class for problem sets.

For samples see [here](sample-brief/Problem Set 1.pdf) (a toy example) and [here](sample/MTH 427 Problem Set 6.pdf) (a real one).

###Description

The `problemset` class uses space on the page in a way that more closely resembles what one would expect from a problem set, eschewing the ample margins more appropriate to articles and manuscripts than to the typical weekly pset.

The result is a document that combines the elegance of LaTeX with the compactness and informality of a hand-written document.

###Features
* Todos (courtesy of the [`todonotes`][todonotes_docs] package)
	* For more details see also [this excellent blog post][todonotes_blog]
* Worksheet mode
	* Hide solutions and print problems on separate sheets—useful for studying.
* Expanded mode
	* Each problem and solution pair on its own page

###Control Sequences
(descriptions to come)

  * `\header`
  * `\problem`
  * `\solution`
  * `formula` environment
  * `mathtable` environment

###Convenience Macros
  * Greek Letters
  * Theorem-Style Environments
  * Mathematical Symbols
    * Calculus
    * Probability and Statistics
    * Linear Algebra
    * Vector Calculus

See the [wiki][problemset_wiki] (in the works) for a full listing.

[todonotes_docs]: http://www.tex.ac.uk/ctan/macros/latex/contrib/todonotes/todonotes.pdf
[todonotes_blog]: http://latexforhumans.wordpress.com/2009/03/13/todonotes
[problemset_wiki]: http://github.com/jmromer/LaTeX-problemset/wiki
