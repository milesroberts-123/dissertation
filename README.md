# Dissertation

Author: Miles Roberts

This dissertation meets the MSU's formatting guidelines as of Spring 2025, but these are subject to change. Check the graduate school's website for the most up-to-date info on formatting requirements:

https://grad.msu.edu/etd

# Advice

* Keep your table of contents as simple as possible - do not add section headings to the document beyond what is required.
  
* Have just one bibliography for the entire dissertation - splitting it up by chapter just adds more work and is not necessary

  
* Do not add a list of figures or a list of tables. These are easy to do in latex but you'll probably need to mess with the formatting.

  
* Organize your figures into folders by chapter/appendix

  
* If you have supplementary tables in published works, just cite that your supplementary tables are available online in the data availability statement in each chapter, so that you don't have to add the tables to the latex document (big pain)

  
* I do not know how to break up a figure or table over multiple pages in latex while also adhering to the graduate school's formatting guidelines, so you are on your own if you want to figure that out

  
* I couldn't quite figure out how to make the spacing completely consistent throughout the document, but you can fine tune it with `\vspace`

# How to use

## Importing references

Click on the new file icon in the top left corner under the Menu button > import from zotero

* `\citep{}` for parentetical citations
* `\citet{}` for in-text citations

## Adding a new chapter/section

You need two lines of code to add a section to the dissertation (except the bibliography). First, `\section`, which will add a hyperlink to the navigation menu in overleaf and `\addcontentsline` to add the section to the table of contents

```
\section*{INTRODUCTION}
\addcontentsline{toc}{subsection}{INTRODUCTION}
```

## Double spaced text

I made a special environment to double space text:

```
\begin{double}
The text I type between these declarations will be double-spaced
\end{double}
```

## Double spaced lists

Similarly, to get a list that is properly double spaced, I have a special environment:

```
\begin{myitemize}
    \item first of all
    \item and another thing
    \item and another thing
\end{myitemize}
```

## Figure numbering

You will want figures in chapter1 to be numbered Figure 1.1, 1.2, etc. and then chapter 2 to be Figure 2.1, 2.2, etc. So you need to restart the figure numbering at the top of each section. You might prefer to name figures as Fig. 1.1, Fig. 1.2, so use `\figurename`. For example:

```
\setcounter{figure}{0}
\renewcommand{\figurename}{Figure}
\renewcommand{\thefigure}{1.\arabic{figure}}
```

If you have an appendix, you might want to number figures A1, A2, etc.:

```
\setcounter{figure}{0}
\renewcommand{\figurename}{Figure}
\renewcommand{\thefigure}{A\arabic{figure}}
```

## Equation numbering

Similarly, to number equations 1.1, 1.2, etc

```
\setcounter{equation}{0}
\renewcommand{\theequation}{1.\arabic{equation}}
```

## Table numbering

Similarly, to number tables 4.1, 4.2, etc.

```
\setcounter{table}{0}
\renewcommand{\tablename}{Table} 
\renewcommand{\thetable}{4.\arabic{table}}
```