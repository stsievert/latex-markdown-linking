
## latex-markdown-linking
Part of the core Markdown syntax is to include syntax like

```
[Bode Miller] has won 6 Olympic medals and 5 World Cup medals in every ski racing discipline

[Bode Miller]:https://en.wikipedia.org/wiki/Bode_Miller
```

yielding

> [Bode Miller](https://en.wikipedia.org/wiki/Bode_Miller) has won 6 Olympic medals and 5 World Cup medals in every ski racing discipline

This is very convenient. It allows you to define your links just as people see
them. I've enjoyed this feature of Markdown and wish the document typesetting
program latex had something similar.

This repo adds a similar functionality to latex. Including

```latex
\SSdefine{Bode Miller}{https://en.wikipedia.org/wiki/Bode_Miller}

\begin{document}
\SSlink{Bode Miller} has won 6 Olympic medals and 5 World Cup medals in every ski racing discipline.
\end{document}
```

will give you the same output as above, properly formatted.

## Notes
* Include `\usepackage{hyperref}` in your preamble.
* You can include this package by `\usepackage{linking}` after including
  `linking.sty` in the folder you're compiling in.

## Limitations
* Doesn't allow the Markdown formatting `[this link will be shown][private_name]`
* Doesn't overwrite the `\link` command. It was easier to use a prefix.
