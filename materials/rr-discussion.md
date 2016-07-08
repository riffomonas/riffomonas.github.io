---
layout: post
title:  "Laboratory reproducible research (Part 1)"
date:   2014-11-05
comments: true
---

This will be the first of probably a few sessions where we discuss how our
research group can improve our ability to document lab activities and foster
scientific communication among each other. Today we'll be talking about what
a reproducible research notebook might look like and what some of the first
steps should be towards that goal.

### The problems that I see currently...  

* Analyses are a mess - folders are horribly organized, little documentation of
what was done, legacy methods get passed along with mutation, etc. The upshot is
that while you may know what you're doing, I have no idea what you've done and
am unable to correct/encourage in real-time  
* This becomes a real problem when people work at a distance or leave the lab  
* When it comes time to write the paper, there are frequently numerous things
that were done and it's hard to make sense of how they all fit together  


### The challenge that I think limits the value of traditional lab notebooks is:  

* Not immediately useful to you  
* Not searchable  
* Do not engage multi-media data  
* Not conducive to computational work  


### To remedy this we will use the following tools...  

* **GitHub repositories:** Everyone should have an account by now, but my sense is
that is something of a major accomplishment to get anything up there and keep it
updated. I really would like to be able to see your code, figures, etc. as they
are produced. GitHub has tools for collaboration where I can see what you've done
and make suggestions
* **Laboratory blogs:** These will be hosted on GitHub and can incorporate output
from knitr. Will have comments window for dialog between me and you and between
each of you. You will have a separate blog posts for each day's goal. These need
to be useful to you to provide you with an incentive to use them. But really,
you just need to do it and get used to it.  
* **kntir:** All software repositories should be based around a knitr document
that compiles and is hosted on GitHub. This will allow all of your analyses to
be run on axiom using R, which is not currently possible with the IPython notebook
system


### Today's goals...

* Set up personal blogs
* Using blog setup get a sense of the overall GitHub workflow
* Ask get a sense of what resources people have used and have you make a pull
request to add those resources.
* Discuss what it would take to get buy in
* Tutorial of knitr?
* Future directions
