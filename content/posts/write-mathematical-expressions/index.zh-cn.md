---
weight: 4
title: "在 Markdown 中编写数学表达式"
date: 2025-09-27
lastmod: 2025-09-27
draft: false
author: "Aan Triono"
authorLink: "https://www.aantriono.com"
description: "本文讨论如何使用 KaTeX 在 Markdown 中编写数学表达式"
images: []
featuredImage: "featured-image.png"

tags: ["LaTeX", "KaTeX"]
categories: ["LaTeX"]

lightgallery: true
toc:
  auto: false
math:
  enable: true
twemoji:
  enable: true
---

本文介绍如何使用 **KaTeX** 在 Markdown 中编写数学表达式。

<!--more-->

## 使用 KaTeX 在 Markdown 中编写数学表达式

**KaTeX** 是一个 JavaScript 库，可在网页中使用 LaTeX 语法渲染数学表达式。KaTeX 以其 **高速、轻量** 和 **高兼容性** 而著称，非常适合在 Hugo、Jekyll 等静态网站或 HTML 页面中展示数学公式。

本文将介绍如何在 Markdown 中使用 KaTeX，包括基础配置、LaTeX 语法支持以及示例展示，帮助您创建具有专业数学排版的文档。

## 为什么选择 KaTeX？

KaTeX 相较于其他库（如 MathJax）具有以下优势：
- 🚀 **速度快**：即时渲染，不影响页面性能。  
- 📦 **体积小**：文件比其他库更轻量。  
- ✍️ **兼容 Markdown**：非常适合与各种平台的 Markdown 一起使用。  
- 🎨 **高质量输出**：数学表达式排版精美、专业。

## 使用 KaTeX 前的准备

在编写数学表达式之前，需要将 KaTeX 集成到项目中。

### 安装 KaTeX

在 Hugo 或 Jekyll 等静态网站中，可从官网或 CDN 获取 KaTeX，并在 HTML 文件中添加以下代码：

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>KaTeX 示例</title>
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
  <h1>KaTeX 示例</h1>
  <p>示例：$E = mc^2$</p>
</body>
</html>
```

## 在 Markdown 平台中的集成

若您使用 Hugo 或 Jekyll，请确保在布局文件（如 `baseof.html`）中加载 KaTeX 脚本与样式，以便正确渲染数学公式。

## KaTeX 支持的 LaTeX 语法

KaTeX 支持大部分标准的 LaTeX / TeX 语法。  
👉 [KaTeX 支持的命令列表](https://katex.org/docs/supported.html)

### 常见类型

#### a. 行内数学公式

使用 `$...$` 来编写行内公式：

```markdown
$E = mc^2$
$c = \pm\sqrt{a^2 + b^2}$
```
结果：  
$E=mc^2$  
$c = \pm\sqrt{a^2 + b^2}$

#### b. 块级数学公式

使用 `$$...$$` 来书写块级公式：

```markdown
$$
\int_a^b f(x) \, dx = F(b) - F(a)
$$
```

结果：  
$$
\int_a^b f(x) \, dx = F(b) - F(a)
$$

#### c. 常见数学运算符

- 加法：`x + y`  
- 乘法：`x \cdot y` 或 `x \times y`  
- 分数：`\frac{a}{b}`  
- 开方：`\sqrt{x}`

#### d. 希腊字母与特殊符号

- 小写希腊字母：\alpha, \beta, \gamma  
- 大写希腊字母：\Gamma, \Delta  
- 特殊符号：\infty（无穷），\partial（偏导），\nabla（nabla算子）

#### e. 矩阵与方程组

使用 `\begin{bmatrix}` 可创建矩阵：

```markdown
$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$
```

结果：  
$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$

## 更多自定义选项

- 自定义分隔符（如 `\( ... \)`）  
- 视觉样式：\mathbf{A}（粗体），\mathit{A}（斜体）  
- 字体大小控制：\small, \large, \Huge  

示例：  
$$
\mathbf{F} = \frac{d}{dt} \mathit{p}
$$

## 示例与结果

行内示例：$E = mc^2$  
块级示例：
$$
\int_a^b f(x) \, dx = F(b) - F(a)
$$

矩阵示例：
$$
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
$$

希腊符号：$\alpha$, $\beta$, $\gamma$

## 结论

使用 KaTeX，您可以在 Markdown 中轻松编写高质量数学表达式。  
配置简单、语法广泛支持，使其成为展示在线数学内容的理想选择。  

👉 想学习更多 LaTeX 知识？请访问 [LaTeX 学习手册](https://www.aantriono.com/2022/07/buku-panduan-belajar-latex.html)。
