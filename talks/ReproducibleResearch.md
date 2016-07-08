---
title				: "Making your analyses more reproducible"
subtitle		: "http://riffomonas/talks/2014_12_03_DANG.html"
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

* Have you ever wondered why so many cook books suck?  
* Have you ever wondered how a computer programming/analysis book can have an errata?  
* Ever have problems getting a published primer pair to work?

> * Lack of reproducibility is an insidious and pervasive problem

--- 

## In the next hour you should be able to...

* Understand the importance of reproducibilty in research
* Describe the current climate in terms of research reproducibility
* Reflect on the practices used in your lab that foster or limit reproduciblity
* Set up your own data analysis workbook

---

## [Elements of the scientific method (according to wikipedia)](http://en.wikipedia.org/wiki/Scientific_method#Elements_of_the_scientific_method)
* Characterizations
* Hypothesis development
* Predictions from the hypothesis
* Experiments
* Evaluation and improvement
* Confirmation

---

## Evaluation and improvement

> * PIs take it on faith that your analysis is right  
> * Few (any?) reviewers actually try to redo your science on any level  
> * Reproducibility is a critical component to doing science  
> * A flawed experiment can screw over a bunch of downstream studies  

---

## Many levels of reproducibility

> * Repeat the general experiment with a different population  
> * Repeat the general experiment with the same population  
> * Repeat the analysis using the same data  
> * Repeat the analysis using the same data and methods  

---

## I should be able to read your paper and...  

1. Download your raw, unprocessed data   
2. Read your paper and any supplements to understand what exactly you did to curate the data  
3. Repeat your analysis  
4. Support your results  
5. Do something creative that builds upon what you've done  

---

## Notes

> * This is not about whether ***you*** ....
  * ... did the analysis correctly
  * ... got the "right" answer
> * It is about whether ***I***...
  * ... am able to see what you did and repeat it
  * ... can use your data to do something more
> * Most importantly, this is not about fraud

---

## General trend: Drug discovery

<img src="http://www.nature.com/nrd/journal/v10/n9/images/nrd3439-c1-f1.jpg" style="margin:0px auto;display:block" width="800">

# Bayer HealthCare
# Prinz et al. 2011. Believe it or not: how much can we rely on published data on potential drug targets? Nature Reviews Drug Discovery 10:712 (http://www.nature.com/nrd/journal/v10/n9/full/nrd3439-c1.html)

---

## General trend: Drug discovery

* Researchers from Amgen replicated 53 "landmark" papers and could only confirm 6 (11%) of the findings  
  - C. Glenn Begley	& Lee M. Ellis. 2012. Drug development: Raise standards for preclinical cancer research. Nature. 483:531.

* "An unspoken rule among early-stage venture capital firms that “at least 50% of published studies, even those in top-tier academic journals, can't be repeated with the same conclusions by an industrial lab” has been recently reported (see Further information) and discussed"
  - Prinz et al. 

---

## Discuss with your neighbor...

* You are the PI of a research group that is riding the wave of some exciting publications. The student who did the bulk of the work for your last ScienceCellNature paper has gone off to do a postdoc. You are now getting inundated with emails from others asking about the nitty gritty of the methods.

> * Now what do you do?
> * How would you prevent this in the future?
> * What if the person emailing you is a competitor?

---

## What are the hurdles to reproduciblity?

* Limited space in Materials & Method sections
* The raw data or the metadata are not public
* Manually editing data files
* Software versions
* Time it takes to make sure data/methods are reproducible
* Can you think of others?

---

## Think about the last paper from your lab

* What would keep me from taking your raw data and regenerating Figure 1?

---

## What should the goal be?
* Not this!
  * Should ***not*** have to contact the original scientists for help (what happens in 5 years?)
  * Should ***not*** have to distrust original scientists if you can't reproduce their work
* Note...
  * Anytime you edit a file, you lose reproducibility
  * Anytime you make a decision that is not documented, you lose reproducibility

---

## What do we think of this?

> "The study is described so that it could be replicated by another expeditionary team who were willing to dive across Oman collecting rare fish under several hard-earned licences" - [Steve Simpson](http://www.nature.com/news/confusion-over-publisher-s-pioneering-open-data-rules-1.16409?WT.mc_id=TWT_NatureNews)

* How does this affect reproducibilty?

---

## Literate programming...

* "I believe that the time is ripe for significantly better documentation of programs, and that we can best achieve this by considering programs to be works of literature. Hence, my title: 'Literate Programming.'" - Donald Knuth, 1992
* The concept of combining code with documentation

---

## Reproducibile research toolbox 

* Literate programming tools
  - Wikis
  - IPython notebook
  - `knitr` and `slidify` R packages
* Version control: git and GitHub
* `make`

--- &twocol

## IPython Notebook

*** {name: left}
* An executable wiki
* Can run any programming language
* Can output to any format
* Used for [Ding and Schloss (2014) Nature paper](http://nbviewer.ipython.org/gist/pschloss/9815766/notebook.ipynb)


*** {name: right}
<img src="assets/img/IPythonNotebook.png" style="margin:0px auto;display:block" width="500">

---

## knitr R package

* Very similar to IPython
* Bonus of being able to present varaiables within the text:


```r
random.numbers <- runif(10)
total <- sum(random.numbers)
```

* I randomly drew 10 random numbers. These included: 0.72, 0.91, 0.48, 0.58, 0.54, 0.87, 0.12, 0.95, 0.61, 0.53
* Their sum was 6.31

--- &twocol

## Who is your most important collaborator?

*** {name: left}
* You. Six months from now.
* Version control software (e.g. git/GitHub) provides a "time machine" of versions of text and software
* Facilitates collaboration

*** {name: right}

> <img src="assets/img/phd101212s.gif" alt="Piled Higher and Deeper by Jorge Cham, http://www.phdcomics.com", style="margin:0px auto;display:block" width="400">

---

## knitr

* Combination of [markdown](http://rmarkdown.rstudio.com) and R code to create literate programming documents
* Markdown: allows you to focus on text without worrying about the formatting:

```
# This is a heading
Today I learned something *really* important. I think I'm now prepared to
make some **bold** claims. These claims include...
* Claim 1
* Claim 2
* Claim 3
```

* You try!


---

## knitr: embed R code


```r
plot(runif(100), ylab = "Random Number", xlab = "Order numbers drawn", pch = 19, 
    col = rainbow(100))
```

<img src="assets/fig/unnamed-chunk-2-1.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />

---

## knitr: inline R code

````
My favorite thing about knitr is the ability to embed R code within
my document so that I don't have to copy and paste any numbers. I
mean who can keep track of factoids like that the square root of pi
is ` r sqrt(pi)`
````

My favorite thing about knitr is the ability to embed R code within
my document so that I don't have to copy and paste any numbers. I
mean who can keep track of factoids like that the square root of pi
is 1.7724539

---

## Where to go from here...

* Acutally use knitr/IPython notebooks to document your workflow
* Get a GitHub account and [learn git](https://try.github.io)
* Integrate noteoboks with a repository
* Uninstall Excel/Prism
* Learn R or Python ([Software Carpentry Workshops](https://www.eventbrite.com/e/university-of-michigan-wise-software-carpentry-workshop-registration-14607865519))