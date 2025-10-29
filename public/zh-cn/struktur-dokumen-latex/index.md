# LaTeX文档结构


本文讨论信件、文章、报告和书籍文档类的LaTeX文档结构。

---

<!--more-->

## 1. 引言

**LaTeX** 是一种基于标记的排版系统,广泛用于撰写学术论文、报告、书籍甚至毕业论文。**Overleaf** 是编写和编译LaTeX文档的流行平台,这是一个在线编辑器,支持实时协作并提供完整的文档和模板。

在开始撰写文档之前,了解LaTeX文档的基本结构非常重要。一个 `.tex` 文件通常由三个主要部分组成:

1. **导言区(Preamble)** – `\begin{document}` 之前的初始设置
2. **正文(Body)** – `\begin{document}` 和 `\end{document}` 之间的主要内容
3. **附加部分** – 如附录、参考文献或索引

---

## 2. LaTeX文档的通用结构

LaTeX文档的最小结构如下:

```latex
\documentclass{article}
\usepackage[utf8]{inputenc}

\title{文档标题}
\author{作者姓名}
\date{\today}

\begin{document}

\maketitle
\section{引言}
您的引言文本在此处。

\end{document}
```

Overleaf 解释说,每个LaTeX文档**必须以** `\documentclass{}` 声明开始,并以 `\end{document}` 结束。

---

## 3. 导言区

导言区包含文档开始之前的所有初始设置。通常包括:

### a. 文档类

```latex
\documentclass[12pt, a4paper]{article}
```

文档类决定文档的类型和通用样式。一些标准类别:

| 类别 | 描述 |
|-------|------------|
| `article` | 用于文章、短报告或论文 |
| `report` | 用于长报告、毕业论文或学位论文 |
| `book` | 用于带章节(chapter)的书籍 |
| `letter` | 用于正式信件 |

---

### b. 宏包(Packages)

宏包扩展了LaTeX的功能。常见示例:

```latex
\usepackage[utf8]{inputenc}   % 设置文本编码
\usepackage[T1]{fontenc}      % 设置字体编码
\usepackage{graphicx}         % 插入图片
\usepackage{amsmath, amssymb} % 数学符号和公式
```

---

### c. 文档元数据

元数据包含标题、作者和日期等信息。

```latex
\title{LaTeX文档示例}
\author{作者姓名}
\date{\today} % 或可以用 {} 留空
```

当在文档正文中调用 `\maketitle` 命令时,将使用此元数据。

---

## 4. 文档正文

此部分包含 `\begin{document}` 和 `\end{document}` 之间的主要内容。

基本结构示例:

```latex
\begin{document}

\maketitle

\section{引言}
主题的开篇或介绍部分。

\section{方法论}
解释研究的方法或步骤。

\subsection{步骤}
方法的更详细说明。

\section{结论}
讨论的最终结论。

\end{document}
```

### a. 章节编号

LaTeX自动为章节(`\section`、`\subsection` 等)编号。要创建无编号的章节,使用星号:

```latex
\section*{致谢}
```

---

### b. 添加图片

使用 `graphicx` 宏包:

```latex
\usepackage{graphicx}

\begin{figure}[h]
\centering
\includegraphics[width=0.5\textwidth]{gambar.png}
\caption{图片示例}
\label{fig:contoh}
\end{figure}
```

---

### c. 编写公式和方程

使用 `amsmath` 宏包:

```latex
\begin{equation}
E = mc^2
\end{equation}
```

---

## 5. 附加部分(可选)

对于学术文档或书籍,LaTeX提供额外的分区,如:

### a. 前置内容、主体内容和后置内容

```latex
\frontmatter    % 前置部分(摘要、目录)
\tableofcontents

\mainmatter     % 主要内容(章节、小节)
\chapter{引言}

\backmatter     % 后置部分(参考文献、附录)
\appendix
\chapter{附录}
```

---

### b. 参考文献

使用 `biblatex` 实现自动参考文献列表:

```latex
\usepackage{biblatex}
\addbibresource{daftar-pustaka.bib}

...

\printbibliography
```

---

## 6. 最小文档示例

以下是**最简单**的有效文档示例:

```latex
\documentclass{article}
\usepackage[utf8]{inputenc}

\title{LaTeX中的Hello World}
\author{作者}
\date{}

\begin{document}

\maketitle

\section{引言}
这是LaTeX中的最小文档示例。

\end{document}
```

---

## 7. 技巧和最佳实践

- 使用**分离的文件夹结构**(`/images`、`/chapters`、`/bib`)以便轻松管理大型文档。
- 将每个章节分离到单独的 `.tex` 文件中,并使用 `\input{}` 或 `\include{}` 调用。
- 使用 **Overleaf大纲面板** 快速查看文档结构。
- 避免加载不必要的过多宏包,以保持编译性能。

---

## 8. 结论

LaTeX文档的基本结构非常有序和模块化。通过理解**导言区**、**正文**和**附加部分**之间的划分,作者可以更高效地管理技术文档。

Overleaf提供完整的指南、实用示例和模板,帮助新用户学习并撰写专业文档。

---

### 📚 参考资料

1. [30分钟学习LaTeX – Overleaf](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes)  
2. [章节和段落 – Overleaf](https://www.overleaf.com/learn/latex/Sections_and_chapters)  
3. [如何用LaTeX撰写论文(第1部分):基本结构 – Overleaf](https://www.overleaf.com/learn/latex/How_to_Write_a_Thesis_in_LaTeX_%28Part_1%29%3A_Basic_Structure)  
4. [插入图片 – Overleaf](https://www.overleaf.com/learn/latex/Inserting_Images)  
5. [使用BibLaTeX管理参考文献 – Overleaf](https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex)  
6. [在Overleaf中使用文件大纲](https://www.overleaf.com/learn/how-to/Using_the_File_Outline_in_Overleaf)

---
