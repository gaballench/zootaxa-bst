# zootaxa-bst
A .bst reference style for LaTeX

The usage is pretty simple: Just install `zootaxa.bst` in a place where `bibtex` can find it and the compile a couple times with bibtex before compiling with latex. Rinse and repeat if needed. Also, don't forget to create your `bibtex` `.bib` bibliography file. Please note that three lines are absolutely necessary for this:

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

Please feel free to send a pull request for improving the package.
