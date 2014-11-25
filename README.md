
## latex-markdown-linking
Part of the core Markdown syntax is to include syntax like

```
[Bode Miller] has won 6 Olympic medals and 5 World Cup medals.

[Bode Miller]:https://en.wikipedia.org/wiki/Bode_Miller
```

yielding

> [Bode Miller](https://en.wikipedia.org/wiki/Bode_Miller) has won 6 Olympic medals and 5 World Cup medals.

This is very convenient. It allows you to define your links just as people see
them. I've found this encourages for links to have as few words as possible. I
tend to rethink my sentence structure and say something meaningful. People see
exactly what I type; that's a good way to write.

In example, a typical example of a not very meaningful link is

> A link to my Github can be found [here][My Github].

Instead of

> [My Github] includes my explorations into many languages and has some useful
> tools.

[My Github]:https://github.com/scottsievert

I've enjoyed this feature of Markdown and wish the document typesetting
program latex had something similar.

This repo adds a similar functionality to latex. The LaTeX code

```latex
\usepackage{hyperref} % required by linking.sty
\usepackage{linking.sty} % include in your compile folder
\SSdefine{Bode Miller}{https://en.wikipedia.org/wiki/Bode_Miller}

\begin{document}
\SSlink{Bode Miller} has won 6 Olympic medals and 5 World Cup medals.
\end{document}
```

will give you the same output as above.

## Limitations
* Doesn't allow the Markdown formatting `[this text will be
  shown][private_name]` (or is this a feature?)
* Doesn't overwrite the `\link` command. It was easier to use a prefix (the
  reason you see `\SSlink` not `link`.
