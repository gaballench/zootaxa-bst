# zootaxa-bst
A .bst reference style for LaTeX

## Introduction

This package provides a bst reference style file for the journal zootaxa that publishes contributions in zoology and classification. This is a fork of `apa.bst` as provided by texlive since this style file resembled the most Zootaxa's own style. Further modifications were made to the code in order to generate in-text citations and bibliography sections appropriately. Although I have not tested the style with tools other than the texlive distribution under linux, it is expected to work on any platform and distribution that the apa.bst file does. Please see below under 'Bug reports and contributing' if something is not behaving as expected.

## Download

This package is being submited to CTAN and will eventually be available there and probably bundled together with distributions such as texlive. In the meantime, it can be downloaded from github (https://github.com/gaballench/zootaxa-bst/) where we will also find the development version of the package.

## Installation

There are two ways:

- Put the .bst file where latex can find it.
- Put the .bst file in the same directory as your tex file so that it can be found during compilation. This method is preferred when you need the style file just for a single project and don't expect to needed later.

Currently Ubuntu 18.x uses texlive2017 and therefore this package can not be installed using `tlmgr install`. Therefore we will need to install it to the personal packages (i.e., outside texlive's directories). This is what I did:

```
cd ~/
tlmg init-usertree # this will throw some warning and stop because of version mismatch (texlive 2017 vs 2018)
mkdir -p texmf/bibtex/bst # create the directory path where we will place the package 
cd texmf/bibtex/bst
git clone https://github.com/gaballench/zootaxa-bst.git # clone this repository
texrehash ~/texmf # include texmf's directory tree to places where texlive will search
```

Afterwards, we can compile the document with bibtex and latex and `zootaxa.bst` will be found and used.

## Usage

Please note that three lines are necessary for compiling with this reference style:

```
\documentclass{article}

\usepackage{natbib}
...
...
...
\bibliographystyle{zootaxa}
\bibliography{example-refs}

\end{document}
```

The command `usepackage` activates the `natbib` package necessary for managing references. The command `bibliographystyle` will tell the system to use `zootaxa.bst`. The command `bibliography` points the `.bib` file. Please note that the fact that we are not indicating paths indicates that 1) the files are in the path (in the case of the package if it was installed where the system can find it),  or the in working directory where the remaining files are found (e.g., the bibliography file). 

## Author(s) and maintainer(s)

Currently only Gustavo A. Ballen is involved in the development of this package.

## Bug reports and contributing

Please feel free to send a pull request through github for improving the package. Also, you can send bug reports and suggestions for improvement; please ensure that you provide a reproducible instance along with your bug report (e.g., both the .tex file and the .bib file that I can compile so that I can better understand what is going on).

## License

This package is released under the LaTeX Project Public License in order to follow the license of the apa package on CTAN. See https://ctan.org/license/lppl1.3c for details and the file `LICENSE` for details.
