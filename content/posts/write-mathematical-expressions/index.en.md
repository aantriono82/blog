---
weight: 4
title: "Writing Mathematical Expressions in Markdown"
date: 2025-09-27
# lastmod: 2025-09-27
draft: false
author: "Aan Triono"
authorLink: "https://www.aantriono.com"
description: "This article discusses writing mathematical expressions in Markdown using KaTeX"
images: []
featuredImage: "featured-image.png"

tags: ["KaTeX"]
categories: ["LaTeX"]

lightgallery: true
toc:
  auto: false
math:
  enable: true
twemoji:
  enable: true
---

This article discusses writing mathematical expressions in Markdown using KaTeX.

<!--more-->

--

## Writing Mathematical Expressions Using KaTeX in Markdown

KaTeX is a JavaScript library that allows you to render mathematical expressions using LaTeX syntax on web pages. KaTeX is known for being fast and lightweight, making it ideal for displaying mathematical expressions in Markdown, especially in web or static site applications like Hugo, Jekyll, or plain HTML sites.

This article will explain how to write mathematical expressions using KaTeX in Markdown, including basic setup, supported LaTeX syntax, and several usage examples. With this guide, you can create Markdown documents that present mathematical expressions professionally.

## Why KaTeX?

KaTeX has several advantages over other libraries like MathJax:
* Speed: KaTeX is designed to render mathematical expressions instantly without affecting page performance.
* Small Size: KaTeX file size is smaller compared to other libraries.
* Markdown Compatibility: KaTeX is very suitable for use with Markdown on various platforms.
* High-Quality Output: Mathematical expressions are rendered with a neat and aesthetic appearance.

## Preparation for Using KaTeX

Before you can write mathematical expressions with KaTeX in Markdown, you need to integrate KaTeX into your project.

## Installing KaTeX

If you're working with static sites like Hugo or Jekyll, download KaTeX from its official website or use a CDN. Add KaTeX scripts and styles to your HTML file.

Example:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KaTeX Example</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.0/dist/katex.min.css">
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.0/dist/katex.min.js"></script>
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.0/dist/contrib/auto-render.min.js"></script>
    <script>
        document.addEventListener("DOMContentLoaded", function () {
            renderMathInElement(document.body, {
                delimiters: [
                    { left: "$$", right: "$$", display: true },
                    { left: "$", right: "$", display: false }
                ]
            });
        });
    </script>
</head>
<body>
    <h1>KaTeX Example</h1>
    <p>This is an example: $E = mc^2$</p>
</body>
</html>
```

## Integration with Markdown Platforms

If you're using static site generators like Hugo or Jekyll, make sure to configure Markdown to support KaTeX. You can add KaTeX scripts and styles in the base layout (for example, baseof.html in Hugo).

## LaTeX Syntax Supported by KaTeX

KaTeX supports most standard LaTeX/TeX syntax.

{{< admonition tip >}}
Here is a list of [TeX functions supported by KaTeX](https://katex.org/docs/supported.html).
{{< /admonition >}}

Here are some commonly used main categories:

### a. Inline Mathematics

To write inline mathematical expressions, use single dollar signs ($).

Example:
```markdown
$E = mc^2$

$c = \pm\sqrt{a^2 + b^2}$ and \\(f(x)=\int_{-\infty}^{\infty} \hat{f}(\xi) e^{2 \pi i \xi x} d \xi\\)
```

Result:

$E=mc^2$

$c = \pm\sqrt{a^2 + b^2}$ and \\(f(x)=\int_{-\infty}^{\infty} \hat{f}(\xi) e^{2 \pi i \xi x} d \xi\\)

### b. Block Mathematics

Use double dollar signs ($$) to create mathematical expressions in block form.

Example:
```markdown
$$
\int_a^b f(x) \ dx = F(b) - F(a)
$$
```

Result:
$$\int_a^b f(x) \ dx = F(b) - F(a)$$

### c. Mathematical Operators

KaTeX supports various mathematical operators, including:

* Addition: x + y
* Multiplication: x \cdot y or x \times y
* Fractions: \frac{a}{b}
* Roots: \sqrt{x}

Example:
```markdown
$$
\frac{1}{\sqrt{2\pi}} e^{-\frac{x^2}{2}}
$$
```

Result:
$$
\frac{1}{\sqrt{2\pi}} e^{-\frac{x^2}{2}}
$$

### d. Greek and Other Symbols

Use LaTeX syntax to write Greek or special symbols:

* Lowercase Greek: \alpha, \beta, \gamma
* Uppercase Greek: \Gamma, \Delta
* Others: \infty (infinity), \partial (partial derivative), \nabla (nabla operator)

Example:
```markdown
$\alpha + \beta = \gamma$
```

Result:
$$\alpha + \beta = \gamma$$

### e. Matrices and Systems of Equations

KaTeX supports matrix format using the \begin{matrix} command.

Example:
```markdown
$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$
```

Result:
$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$

## Further Customization

### a. Custom Delimiters

You can customize delimiters in KaTeX. For example, use \( and \) for inline, or \[\] for blocks.

### b. Visual Styles

KaTeX supports visual styles such as:

* Bold Text: \mathbf{A} for bold letters.
* Italic Letters: \mathit{A} for italic letters.
* Font Size: \small, \large, \Huge.

Example:
```markdown
$$
\mathbf{F} = \frac{d}{dt} \mathit{p}
$$
```

Result:
$$
\mathbf{F} = \frac{d}{dt} \mathit{p}
$$

### c. Error Handling

KaTeX has good error handling. If you write incorrect syntax, the expression will still be rendered but will provide an error notification.

## Mathematical Expressions with KaTeX

This is an example of using KaTeX in Markdown.

## Inline Example

Famous formula by Einstein: $E = mc^2$

## Block Example

Here is an integral:

$$
\int_a^b f(x) \, dx = F(b) - F(a)
$$

## Matrix

Matrix representation:
$$
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
$$

## Greek Symbols

Some Greek symbols: $\alpha$, $\beta$, $\gamma$.

## Visual Styles

Bold letters: $\mathbf{A}$.
Italic letters: $\mathit{A}$.

The results will be rendered according to your KaTeX configuration.

## Conclusion

With KaTeX, you can create beautiful and efficient mathematical expressions in Markdown.

{{< admonition tip >}}
If you want to learn more about LaTeX or TeX, you can visit [here](https://www.aantriono.com/2022/07/buku-panduan-belajar-latex.html). Check it out directly. 😙
{{< /admonition >}}

Simple setup steps and extensive LaTeX syntax support make KaTeX an excellent choice for online mathematical needs. Make sure to adjust settings according to your project so that KaTeX runs optimally.