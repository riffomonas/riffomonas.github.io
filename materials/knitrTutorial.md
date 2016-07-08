---
layout: post
title:  "Laboratory reproducible research (Part 2)"
date:   2014-11-12
comments: true
---

These are the notes for our extended lab meeting on 11/12/2014 continuing the
development of reproducible research skills in the lab. The primary topic for
today will be using knitr as a tool to have an ongoing, executable laboratory
notebook. An example notebook can be used as a guide for our [wild mouse paper](https://rawgit.com/SchlossLab/wild_mice/master/wild_mice.html)


# Topics we still need to cover:  

* knitr
* GitHub
* bash
* make


# knitr
* Allows you to interleave R analysis with text
  * Can use R variables in text
  * Will remember R variables between chunks
  * Saved as an `*.Rmd` file
* Is the basis for a variety of outputs
  * slidify (R-based PowerPoint)
  * markdown (`*.md`)
  * web pages (`*.html`)
  * word (`*.docx`)
  * pdf (`*.pdf`)
* Integrated into RStudio
  * Can easily use on axiom, but would need to do:

        library(knitr)
        knit("whatever.Rmd")

  * knitr options available on the cheat sheet I posted on your Resource page
  * If a project gets too big RStudio might gag and then you'll have to use R
  * If bad things happen (and you're using `cache=TRUE` for anything), delete
  the cache folder

# Basics
* Code blocks vs. inline text
* `eval`
* `echo`
* `tidy`
* `cache`
* `fig.height`, `fig.width`, `fig.align`
* `fig.path`
* `dev`
* `engine`


# More complex features
* Globally set options with `opts_chunk$set()`; local setting trumps the global
* Re-running a code block
* Specifying where to output figures
* Make caching conditional


# Best practices
* Name your code blocks!
* `source`-ing R scripts
* `sessionInfo()`
* Don't just vomit output - format it and describe what the question was, what
you did, and what it says
