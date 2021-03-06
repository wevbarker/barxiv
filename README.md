# <img src="barxiv_icons/postarxiv.png" width="30"> BarXiv <img src="barxiv_icons/prearxiv.png" width="30">
##  :warning: new website [wevbarker.com](http://www.wevbarker.com) (temporary notification on all my public repos) :warning:

## Beamer arXiv citations aged with Matplotlib colormaps
---
### Install and use
BarXiv is a very simple `LaTeX2e` package for the `beamer` class. It enables audience-friendly citations of papers which may or may not be on the [arXiv](https://arxiv.org). These are highlighted according to the age of the reference, according to the ubiquitous colormaps of Matplotlib. BarXiv **does not need** Python.
1. **Download** `barxiv.tar.gz` and **unzip** to your `.tex` and `.bib` working directory:
```
tar -C <working_directory_name>/ -xvf barxiv.tar.gz
```
2. **Load** the package into your preamble:
```
\usepackage[bib file = <bib_file_name>.bib, cmap = rainbow, saturation = 40]{barxiv}
```
3. **Try** putting `\barxiv{<bibtex_label>}` in place of `\cite{<bibtex_label>}` and twiddling the options:
   - `bib file` or `bibfile`: self-explanatory
   - `cmap`: your favorite Matplotlib colormap such as `viridis` (default), `cubehelix` or `spring` -- a full list can be found [here](https://matplotlib.org/3.1.0/tutorials/colors/colormaps.html)
   - `saturation`: a percentage value, since many colormaps are rather dark
---
### Demonstration 
Here is a simple `beamer` frame to illustrate `barxiv` in use for some `cmap` choices.\
For `hsv` and `spring`:\
<img src="sample_slides/hsv.png" width="400"><img src="sample_slides/spring.png" width="400">\
For `summer` and `winter`:\
<img src="sample_slides/summer.png" width="400"><img src="sample_slides/winter.png" width="400">\
For `binary` and `inferno`:\
<img src="sample_slides/binary.png" width="400"><img src="sample_slides/inferno.png" width="400">\
For `Wistia`:\
<img src="sample_slides/Wistia.png" width="400">\
This frame was generated with `presentation.tex` as follows (note I don't include `presentation.bib`). The preamble explicitly contains all current `barxiv` options:
```
\documentclass{beamer}
\usepackage[utf8]{inputenc}
\usepackage[bib file = presentation.bib, cmap = rainbow, saturation = 40]{barxiv}
```
The body is much as you would expect:
```
\begin{document}
\tiny
\begin{frame}
  \frametitle{A \texttt{beamer} frame to demonstrate \texttt{barxiv}}
  \begin{itemize}
    \item You can recycle the \texttt{.bib} from your latest paper in your \texttt{beamer} talk, and use \texttt{\symbol{92}barxiv} just as you would use \texttt{\symbol{92}cite}.
    \item Today, all the \textbf{best} papers are on the \textbf{arXiv}, such as \barxiv{2019JMP....60e2504B,2017CQGra..34t5006B,2017CQGra..34p7001B}.
    \item In a talk, the audience might just have time to note an arXiv telephone number.
    \item The \textbf{arXiv} contains more than one eprint \textbf{class}, e.g. \barxiv{2019arXiv190800993Y,2016IJMPS..4060010N}.
    \item Long ago, books such as \barxiv{1984ucp..book.....W}, or very important papers such as \barxiv{Ashtekar_1991}, had no \textbf{arXiv} on which to appear\footnote{Because the \texttt{barxiv} command is \textbf{robust}, \barxiv{2019JMP....60e2504B,1984ucp..book.....W} should appear well in \textbf{footnotes} and \textbf{captions}.}.
    \item The \textbf{colours} reflect the \textbf{age} of the reference: a decent literature review such as \barxiv{PhysRev.101.1597,1961JMP.....2..212K,1975NCimB..28..127K,1985AmJPh..53..510H,lasenby-doran-heineke-2005,2019arXiv190800993Y,2013CQGra..30t5010C,2015arXiv151201202H,2011CQGra..28u5017B,1972PhLA...39..219K,2011JPhCS.330a2005H,2011PhRvD..83b4001B,1984CQGra...1..651G,2009PhRvD..79b7301L,1979PhLA...75...27T,2008PhRvD..78b3522S,2005NewAR..49...59P,1980PhRvD..21.3269S,1980PhLA...80..232M,RevModPhys.36.463} is thus very \textbf{colourful}.
    \item Bibliographies are not so common in \texttt{beamer} talks, but the \texttt{bibtex} backend supports them if you so choose: this is compatible with \texttt{barxiv}, though slightly against its spirit!
    \item {\large Citations \barxiv{1998RSPTA.356..487L} should scale with font \textbf{size} or font \textsc{style \barxiv{Ashtekar_1991}} }
  \end{itemize}
\end{frame}

\end{document}
```
---
### Tasks 
Things I want to do
- Auto update of current year
- wrap it up and leave it on [CTAN](https://ctan.org/?lang=en)
