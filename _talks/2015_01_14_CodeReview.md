---
title				: "Introduction to code review in the Schloss Lab"
subtitle		: ""
author			: "Patrick D. Schloss"
job         : Department of Microbiology & Immunology
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {selfcontained, standalone, draft}
knit        : slidify::knit2slides
--- 

## Motivation

* Difficult for me as a PI to oversee everything that goes on in the lab and with people's analyses
* I do a poor job of training people how to code and do their analyses
* Would like to incorporate more training into the lab meeting schedule

--- 

## Plan

* Incorporate "code review" as a mechanism to delegate review of code and to
help train people how to code better
* Something we *all* can benefit from
* Current idea is to have it as part of the regular lab meeting schedule

---

## What is code review?

> "[Code review](http://en.wikipedia.org/wiki/Code_review) is systematic
> examination (often known as peer review) of computer source code. It is
> intended to **find and fix mistakes** overlooked in the initial development
> phase, improving both the **overall quality of software** and the
> **developers' skills**"

---

## How will we implement this?

1. Someone else reads a snippet of your code (50-100 lines of code) and tells
the rest of us what it means
1. Help trouble shoot other people's coding problems
1. Presentation of new packages we've found

---

## Benefits of code review (see Petre & Wilson) to researchers

* usability (e.g., how easily someone can “enter the structure” of the code)
* ease of re-use, readability, and density
* code structure and solution structure (“The way they organise a solution to a problem”)
* feedback on the organisation of README files
* performance and opttimization
* unit testing (or its absence)

---

## Talking with others...

* The main benefit comes from knowing that someone else will be reading your
code - so it's not essential that we review every line of code
* Improves collaboration among people that work together

---

## Today we will focus on...

1. Style
1. Code review
1. Testing

---

## Style

* Numerous style guides available
  * [google](http://google-styleguide.googlecode.com/svn/trunk/Rguide.xml)
  * [Hadley Wickham](http://adv-r.had.co.nz/Style.html)
* The goal is to have a uniform style to improve readibility and prevent bugs

---

## Code review

* [Example](https://github.com/SchlossLab/miseq_analysis/blob/master/code/split_error_summary.R)
from project I am currently working on

---

## Testing

* We tend to have a haphazard appraoch to testing our code
* As projects get bigger, we forget about dependencies, and small changes
can lead to problems
* A testing framework would allow us to keep our tests and make sure they pass
as we continue to develop other parts of a project

> * One approach is called Test Driven Development (TDD)

---

## TDD is a software development process where you...

1. Create a failing test that describes one a realistic problem you might face
1. Make sure test fails / see which tests fail
1. Write enough code to make sure test passes
1. Run all tests to make sure you haven't broken other test
1. Simplify the code
1. Repeat

---

## Philosophy

* Every line of code has a test (extreme)
* The programmer writes the tests and so they aren't dependent on others getting requirements
* Don't Repeat Yourself (DRY)

---

## How did you test your last piece of code?

---

## Introducing: `testthat`

* Problems with what we've been doing
	* This process can get tedious
	* It's not automated
	* We lose the tests
* `testthat` is an R package for doing testing
  * Put test code into a separate file (`test-????.R`)
  * Code as normal in your R script file (`????.R`)

---

## How to run...

* Method #1:

```r
library(testthat)
source("????.R")
source("test-????.R")
```

* Method #2:

```r
library(testthat)
source("????.R")
test_dir("./")
```

* Should be able to use `auto_test`, which runs tests automatically when source
code is updated

---

## Things to know about...
* Expects the testing file to be named `test_something.R`
* Options to go with `expect_that` include:
  * `is_true`: truth
  * `is_false`: falsehood
  * `is_a`: inheritance
  * `equals`: equality with numerical tolerance
  * `equals_reference`: equality relative to a reference
  * `is_equivalent_to`: equality ignoring attributes
  * `is_identical_to`: exact identity
  * `matches`: string matching

---

## More...

* Options to go with `expect_that` include:
  * `prints_text`: output matching
  * `throws_error`: error matching
  * `gives_warning`: warning matching
  * `shows_message`: message matching
  * `takes_less_than`: performance

---

## Other elements of `testthat`

* Can get fancy by defining your own expectation functions
* Can establish specific contexts with environmental settings, etc.
* Can automate testing so that it runs the tests whenever you update the source code

---

## Let's redo my code...

1. Create a failing test that describes one a realistic problem you might face
1. Make sure test fails / see which tests fail
1. Write enough code to make sure test passes
1. Run all tests to make sure you haven't broken other test
1. Simplify the code
1. Repeat
