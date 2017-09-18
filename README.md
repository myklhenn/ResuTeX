# ResuTeX
A LaTeX resume/CV template, currently used for my own resume.

***See the compiled document [here](https://github.com/myklhenn/ResuTeX/blob/master/mhenning-resume.pdf).***

This document implements a JSON-like syntax for defining its components, based 
on `\newcommand` macros defined at the top of the file. A sample of the resume's 
header and contact info, including the aformentioned macros and the way they are 
used to format the actual content, follows:

```latex
\newcommand{\Name}[1]{#1} % (no extra formatting on macros like these)
\newcommand{\AddressLineOne}[1]{#1}
\newcommand{\AddressLineTwo}[1]{#1}
\newcommand{\Phone}[1]{#1}
\newcommand{\Email}[1]{\href{mailto:#1}{<#1>}}
\newcommand{\Website}[1]{\texttt{\href{#1}{\textul{#1}}}}
\newcommand{\ContactInfo}[6]{
  \part*{#1}
  \begin{tabular}{ m{12em} m{24em} }
    #2 & \texttt{#4 #5} \\ #3 & #6
  \end{tabular}
}

...

\begin{document}

\ContactInfo
  {\Name{Michael Henning}}
  {\AddressLineOne{3100 Ferry Ave, Apt. D117}}
  {\AddressLineTwo{Bellingham, WA 98225}}
  {\Email{mykl951@gmail.com}}
  {\Phone{206-999-4513}}
  {\Website{https://linkedin.com/in/myklhenn}}
```

The macro definitions can be modified to change the output formatting and 
layout, but the content is provided in the hierarchical syntax at the end so 
volatile fields can be modified as they need changing, or so the whole document 
can be modified to reflect the _curriculum vitae_ of another person.