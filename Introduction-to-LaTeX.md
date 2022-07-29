---
title: "Introduction to LaTeX"
author:
   - name: Andrew Moles
     affiliation: Learning Developer, Digital Skills Lab
date: "29 July, 2022"
output: 
  html_document: 
    theme: united
    highlight: pygments
    keep_md: yes
    code_download: FALSE
    toc: TRUE
    toc_float: FALSE
---

## What is LaTeX and why use it

LaTeX (pronounced LAY-tek or LAH-tek) is a tool for creating professional-looking documents, reports, books, CVs, and presentations. 

In LaTeX the document and the output are separated. This means you only focus on the contents of the document, and your computer will handle the formatting, which saves a lot of work. 

The main advantages of using LaTeX are that it is great at handling complex formatting such as mathematical formulas, table of contents, figure positions, bibliographies and more. Another advantage is once you've written the content of your document, you can change your documents appearance without any weird formatting consequences (I'm looking at you Microsoft Word). The obvious disadvantage is that you have to do some coding to use it, which has a learning curve! 

## Outcomes

* Start to use Overleaf
* Create document in LaTeX that includes
  - titles
  - sections
  - images
  - lists
  - tables
  - hyper links
  - references

## Introduction to Overleaf

LaTeX has been around a while, and therefore there are lots of options available to write and make LaTeX documents. The easiest way to get started with is Overleaf (formally ShareLaTeX). 

Make an overleaf account

Insert link here Overleaf template I made for the workshop

*(TAP style demo introducing Overleaf and basic LaTeX document structure. This would mean students go to links and trainer walks them through and asks questions about various features like what does document class mean, begin and end etc. )*

## Useful resources to use during this session

* [Overleaf documentation](https://www.overleaf.com/learn)
* Google search what you need — e.g. hyperlink colour latex

### Extra resources for after the session
* Videos that [introduce various LaTeX topics](https://www.youtube.com/playlist?list=PLnC5h3PY-znyDQKn3knfXfekZLgWyL7QW)
* 30 minute [learn LaTeX course](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes)
* Free [online introduction to LaTeX](https://www.overleaf.com/learn/latex/Free_online_introduction_to_LaTeX_(part_1))

## Exercises

A friend sent you a really cool article on the gender pay gap in the UK and you want to edit it to add some of your own ideas or research. You remember that you can do this with [Adobe](https://www.adobe.com/uk/), but they are asking you to pay for the software, we can't afford that!  

You think of a creative solution...you've been meaning to learn LaTeX so how about we write the document into LaTeX so we can edit and change what we like?  

You find a useful template online to get you started - [latex_template](https://www.overleaf.com/read/hznjnmfmjfqx). Everything you need for this workshop will be in the template.  

You've emailed the author to ask them about the images and if you can use their article. They respond enthusiastically giving you a link (ADD LINK HERE) that has the following resources that will help you make your document: 

* The pdf of their document
* A csv file with the output of one of their analysis
* The two images they used in their report
* Their references file

### Task 1 — title page

First we need to build up that title page! 

Using the **gender\_pay_gap.pdf** file as your example:

* Add the title
* Add the authors but replace with your own name 
* Add the date with todays date
* Add the abstract
* Make sure the title and abstract are on a separate page to the rest of the document.

### Task 2 — contents

Now we have the nice looking title page, which is a great start! 

Next we set up the contents page which should include a table of contents, list of figures, and list of tables. We might not have added tables or figures yet, but we will soon. 

* Use the [Overleaf documentation](https://www.overleaf.com/learn) to find out how to add these to your document
* Make sure your contents page are on a separate page to the rest of the document

You are very particular and notice in our document we have numbers next to our sections but the document we are copying doesn't, how annoying! You do a quick online search and find this answer in a [stack exchange thread](https://tex.stackexchange.com/a/30123) which seems to solve your problem, yay! The simplified version of this is as follows:  

```
\section*{Introduction}
\addcontentsline{toc}{section}{Introduction}
```

### Task 3 - upload documents to Overleaf

For the next tasks we will need to upload the resources the author sent us into Overleaf. Using the upload button (on the upper left hand side of Oveleaf, just under menu) add the following files to your Overleaf project:

* pay\_gap_bot.png
* paygap.png
* references.bib

Once uploaded, you'll be able to see the files in your project. Try clicking on them to view them. 

### Task 4 — introduction

Great, we have a title page and a contents page. We are in a good place to start adding the content to our document. 

The introduction we are copying has links and an image, exciting! 

* Copy introduction text from the pdf into Overleaf (make sure to paste in the introduction section)
* Add the links. Click on the links to get the urls
* Add the figure, which is the `pay_gap_bot.png` image file in your project
* Make sure you've added a caption and your image is in the centre of the page

Note that to make the image the same as the example something like this will work: ` \includegraphics[width=0.7\linewidth]{pay_gap_bot} `

### Task 5 — methods

You might notice now, when you *Recompile* the gender pay gap bot figure now appears in your list of figures, cool!

Next up, the methods section which has more new elements in equations and citations. 

* Make a new section called methods, like we have for introduction
* Add a new page between methods and introduction
* Copy the text from the methods in the pdf into Overleaf
* Add the url links
* Write the equations
* Add the references, all of which are in the *references.bib* file

Reference hint 1: there are two ways to cite in LaTeX using either `\cite{}` or `\citep{}`. It looks like our example has used `\citep{}`.

Reference hint 2: each reference in the  *references.bib* file has a label which you use within the cite command like `\cite{ggtext}`. 

#### General note about references

The template, rather helpfully, has been set up to handle citations and references. If you are starting off from nothing, first you'll need these two lines somewhere before `\begin{document}`: 

```
% this is for the bibliography
\usepackage[]{natbib}
\bibliographystyle{apsr}
```
And later in the document you'll need this which builds the reference list at the end of your document. This should go just before your `\end{document}`. 

```
% end with the bibliography
\newpage

\bibliography{references.bib}
```

### Task 6 — hyperlinks

Now went you *Recompile* you'll have a reference page, very exciting! 

However, you notice the colour of the citations, url links, and the contents page look different to our pdf document we are copying, we can't have that! 

LaTeX comes to the rescue again. We can change these with the `\hypersetup{}` command! At the beginning of your *main.tex* file you'll see this command. Change the colours of hyperlinks as follows:

* citations to blue
* url to blue
* contents page links to red

### Task 7 — results

We finally get to the good stuff, our results page! Some new features you notice are a table, footnotes, and figure referencing. 

* Make a new section called results on a separate page from methods  
* Copy the text from the results page in the pdf to your Overleaf document
* Add the footnote about tokenisation
* Add the two url links
* The copied table doesn't work! You think writing tables from scratch in LaTeX seems like a lot of effort. After a google search you find a [table convert tool](https://tableconvert.com/) which will do the hard work for you, great! Upload the *paygap\_sector_average.csv* to the table converter to get your table. Make sure it has a caption
* Add the figure, which is the `paygap.png` image file. Be sure to pay attention to the positioning of the figure, you might need to try different positions till it looks right
* Make sure your figure has a label
* Now you can add the figure labels

Hint: You might need to edit the table to make it look the same as the pdf. Some things you can try are adding or removing `\hline` arguments or removing the lines in the in the begin tablular command like the examples below:

```
% line between columns
\begin{tabular}{l | c}
% no line between columns
\begin{tabular}{l c}
```

### Task 8 — discussion

We are almost there, just the discussion left. Two new features here are a quote and a list. 

* Make a new section called discussion on a separate page from results
* Copy the text from the discussion page in the pdf to your Overleaf document
* Format the quote properly using the quote function `\begin{quote} `` your quote '' \end{quote} `
* Add the footnote
* Format the list using the Overleaf documentation for help

Wow, we've just taken a pdf document and converted it to LaTeX! 

### Final task — take our survey

Link to survey here

## Whats next?

R Markdown with LaTeX

Write your CV in LaTeX - check out the LaTex templates to help you with this