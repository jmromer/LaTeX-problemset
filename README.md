# problemset

A LaTeX document class for problem sets.

## Description

The `problemset` class uses space on the page in a way that more closely resembles what one would expect from a problem set, eschewing the ample margins more appropriate to articles and manuscripts than to the typical weekly pset.

The result is a document that combines the elegance of LaTeX with the compactness and informality of a hand-written document.

### Features
* Todos (courtesy of the [`todonotes`][todonotes_docs] package)
	* For more details see also [this excellent blog post][todonotes_blog]
	* Todos are hidden by declaring the `final` option (see below)
* Convenience control sequences
	* 	Take much of the repetitive drudgery out of typing up psets. (Other forms of drudgery it can't help with, alas.)
	
### Options
```
\documentclass[options]{problemset}
```

* `final`: Suppresses the Todo list, hides all inline todos, and loads graphics.

* `worksheet`: Hides solutions and prints problems on separate sheets—useful for self-testing.
* `expand`: Includes a page break after each solution. This is sometimes a neater, if less compact, presentation.



## Control Sequences

#### Sample Output
For output samples of the commands described below see [here](sample-brief/Problem Set 1.pdf) (a toy example) and [here](sample/MTH 427 Problem Set 6.pdf) (a real one).

### Header
`\header[shortname]{name}{course}{assignment}{date}`
  	
Creates the document header. 

Example:
  	
```
\heading[Romer]{Jacob Romer}{Math 427. Partial Differential Equations}{Assignment 6}{November 28, 2012}
```
`shortname` is an optional string that appears to the left of the page number. (Numbering is omitted on the first page).

### Problem		
`\problem[description]`

Marks the beginning of a problem, with optional descriptive text.

```
\problem[5.3.8 (5pts)]
. . .
Is $\lambda = 0$ an eigenvalue?
```

### Solution
	
`\solution{}`

Encloses the solution, which can be hidden with the `worksheet` document class option. 
  
* **NB**: This is incompatible with `verbatim`, which can't be directly called from within a control sequence. 
 
	A workaround is to include `verbatim` text by keeping it in a separate file (e.g., `filename.tex`) and using `\input{filename}` to include this in your solution. 

	Alternatively, experiment with `\texttt{}`, which is often an adequate substitute for short bits of code.
  	
### Formula Environment

`\begin{formula}[name]` 

Takes an optional argument for a named equation. Otherwise names formulas sequentially (Formula 1, Formula 2, etc.).

```
\begin{formula}[Rayleigh Quotient]
\lambda = \frac{\eval{-p(x) \phi(x)\phi'(x)}{a}{b} + \Int{p(x) [\phi'(x)]^2 - q(x) [\phi(x)]^2}{a}{b}}{\Int{[\phi(x)]^2\sigma(x)}{a}{b}}.
\end{formula}
```
  
### Mathtable Environment
`\begin{mathtable}[options]{columns}` 

Essentially `booktabs`-style table, but DRYed up for entries in math mode. This combines the syntatic simplicity of using the `array` package for your table with the prettiness of the `booktabs` table. 

```
\begin{mathtable}[caption=true,title={Some Greek letters},label={one}]{ccc}
  1  & 2   & 3  \\
  \midrule
  \a & \b  & \c \\
  \d & \ep & \t \\
\end{mathtable}
```

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
