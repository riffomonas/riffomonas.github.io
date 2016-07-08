---
layout: post
title:  "TIL: How to write a Word document in RStudio"
date:   2014-11-06
comments: true
---

Today I started writing a proposal for an RFA titled, [Training Modules to
Enhance Data Reproducibility (R25;
RFA-GM-15-006)](http://grants.nih.gov/grants/guide/rfa-files/RFA-GM-15-006.html).
My pitch is going to be the development of a set of teaching modules describing
how to setup a working environment that facilitates computational
reproducibility through the use of blog posts, version control, and literate
programming tools. So, I thought it would be cool to do the thing I've always
wanted to do and write a document under version control. This meant learning how
to write a document in markdown and converting it either to LaTeX or to a
Microsoft Word docx file.

When I've tried this before I've gotten some pretty funky results that I haven't
been entirely happy with. RStudio seems to select some weird formatting scheme
that is pretty horrid. Here's how I started. In RStudio, go File -> New R
Markdown -> Document and then click the button next to "Word". Go ahead and name
the file `test.Rmd`. If you are going to use knitr blocks you want the `.Rmd`
extension. Alternatively, you can just name it `test.md`. This creates a new
file for you with some generic text and a YAML header that looks like so...

    ---  
    title: "test.Rmd"  
    author: "Patrick D. Schloss"
    date: "November 6, 2014"
    output: word_document
    ---

If you go ahead and hit `Knit Word` you'll generate a docx file. It's kind of
ugly and doesn't have the formatting I'd like to use. So, what to do? Alter the
YAML header to look like this...

    ---  
    title: "test.Rmd"  
    author: "Patrick D. Schloss"  
    date: "November 6, 2014"  
    output:  
      word_document:  
        reference_docx: template.docx  
    ---


This will take your file and format it according to the "Normal" style in the
template.docx file. So, you need to go and create a blank Word file called
`template.docx`. Go open a new Word document and save it as `template.docx`. If
you see that the document is now double spaced and you want it single spaced, go
to `template.docx`, right click on the "Normal" tab in the style banner and
select "Modify". From there you an change all sorts of formatting stuff.
Similarly, for my NIH proposal, I wanted 0.5" margins. To do that, I opened
`template.docx` and double clicked on the margins and changed them all to 0.5".
Before clicking OK on the margins window, I clicked the default button. Now,
when I went back to RStudio and clicked on `Knit Word`, viola the document look
like I wanted. Boom. There are two kludgey things about this. First, Word does
not automatically update the file as you modify it. So when I'm working on a
specific aims page that can only be one page, I might have to close and open the
word document multiple times. Second, there's no easy way to go from a docx to a
markdown file. So, that kind of limits me to collaborating with myself or with
others that are open to using markdown to develop the text and then convert the
stuff to Word. Regardless, I could write the way I want and give it to a
collaborator to edit how they want. Oh well, I feel like this is progress

PS. I do admit to opening a LaTeX book today and putting it down since I really
need to get this written ASAP. Someday...
