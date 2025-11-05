---
weight: 4
title: "Text Formatting in LaTeX"
date: 2025-10-16
# lastmod: 2025-10-16
draft: false
author: "Aan Triono"
authorLink: "https://www.aantriono.com"
description: "This article discusses text formatting commonly used in documents written with LaTeX."
images: []
featuredImage: "featured-image.png"

tags: ["Formatting"]
categories: ["LaTeX"]

lightgallery: true
twemoji: true

---

LaTeX is a powerful document preparation system, primarily used in scientific and technical writing. One of its strengths is its ability to format text flexibly and precisely. This article will cover various basic and advanced text formatting techniques in LaTeX, including the use of font styles, font sizes, text alignment, and other elements commonly used in LaTeX documents.

<!--more-->

---

## Font Styles

LaTeX provides various commands to change text font styles:

- `\textbf{...}`: Makes text bold.
- `\textit{...}`: Makes text italic.
- `\underline{...}`: Underlines text.
- `\emph{...}`: Emphasizes text, usually by making it italic.
- `\textsc{...}`: Converts text to small caps.
- `\textrm{...}`: Sets text using roman (serif) font.
- `\textsf{...}`: Sets text using sans-serif font.
- `\texttt{...}`: Sets text using monospace (typewriter) font.
- `\textnormal{...}`: Returns text to default font style.

Usage example:

```latex
\textbf{This text is bold}, \textit{italic}, \underline{underlined}, \emph{emphasized}, \textsc{small caps}.
```

## Font Sizes

To change font size, LaTeX provides several commands:

- `\tiny{...}`: Very small font size.
- `\scriptsize{...}`: Small font size for scripts.
- `\footnotesize{...}`: Font size for footnotes.
- `\small{...}`: Small font size.
- `\normalsize{...}`: Normal (default) font size.
- `\large{...}`: Large font size.
- `\Large{...}`: Very large font size.
- `\huge{...}`: Huge font size.
- `\Huge{...}`: Largest font size.

Usage example:

```latex
\huge{This text is very large}
```

## Text Alignment

LaTeX allows text alignment with several commands:

- `\centering`: Centers text.
- `\raggedright`: Aligns text to the left.
- `\raggedleft`: Aligns text to the right.

Usage example:

```latex
\begin{center}
\textbf{\Large This text is centered}
\end{center}
```

## Lists and Bullet Points

LaTeX provides environments for creating lists:

- Unordered list:

```latex
\begin{itemize}
  \item First point
  \item Second point
  \item Third point
\end{itemize}
```

- Ordered list:

```latex
\begin{enumerate}
  \item First item
  \item Second item
  \item Third item
\end{enumerate}
```

## Colors and Backgrounds

To add color to text or backgrounds, you need to load the `xcolor` package:

```latex
\usepackage{xcolor}
```

Usage example:

```latex
\textcolor{red}{This text is red}
```

To add a background to text:

```latex
\colorbox{yellow}{Text with yellow background}
```

## Tables and Figures

LaTeX allows easy creation of tables and insertion of images:

- Tables:

```latex
\begin{tabular}{|c|c|c|}
\hline
Column 1 & Column 2 & Column 3 \\
\hline
Data 1   & Data 2   & Data 3   \\
\hline
\end{tabular}
```

- Figures:

```latex
\begin{figure}[h]
\centering
\includegraphics[width=0.5\textwidth]{image.jpg}
\caption{Image description}
\end{figure}
```

## Using Macros

Macros in LaTeX allow you to define new commands to simplify writing:

```latex
\newcommand{\myname}{John Doe}
```

Then, you can use `\myname` throughout the document to insert "John Doe".

## Special Characters

LaTeX has several special characters with specific functions, such as:

- `# $ % ^ & _ { } ~ _` and `\`.

To use these characters as regular text, you need to use special commands:

- `\#` for hash sign (`#`).
- `\%` for percent (`%`).
- `\&` for ampersand (`&`).
- `\_` for underscore (`_`).
- `\{` and `\}` for curly braces (`{` and `}`).
- `\~{}` for tilde (`~`).
- `\textbackslash` for backslash (`\`).

## Conclusion

LaTeX is a very powerful tool for formatting text in scientific and technical documents. By understanding and utilizing the basic and advanced commands discussed, you can create documents that are not only informative but also visually appealing. Continue exploring and experimenting with LaTeX to maximize its potential in document preparation.