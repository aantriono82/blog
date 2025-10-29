# 在不同操作系统平台上安装 MiKTeX、MacTeX 和 TeX Live 的指南


本文介绍如何在不同操作系统上安装各种 LaTeX 发行版，包括 MiKTeX、MacTeX 和 TeX Live。

<!--more-->

{{< admonition >}}

若要深入学习 LaTeX，请访问 [LaTeX 学习指南](https://www.aantriono.com/2022/07/buku-panduan-belajar-latex.html)

{{< /admonition >}}

> **想要编写论文、科研报告或书籍，让排版达到国际学术出版水准吗？**  
> 本指南将帮助您了解并在 Windows、macOS 和 Linux 上安装 LaTeX —— 从选择最佳发行版到解决常见问题。  
> 无论您是初学者还是高级用户，都能通过此指南高效且专业地工作。

---

## 1. LaTeX 概述

LaTeX 是一种用于生成专业排版文档的系统（typesetting system），在学术界、科学界和出版界被广泛使用。它能够轻松处理复杂结构，如：

- 数学公式与科学符号，  
- 自动生成引用与参考文献，  
- 保持文档布局一致且规范。

要运行 LaTeX，您需要一个 *TeX 发行版*，即包含所有必需组件的软件包，用于编写、编译和格式化文档。常见的三个发行版是 **MiKTeX**（Windows）、**MacTeX**（macOS）和 **TeX Live**（跨平台）。

---

## 2. 什么是 LaTeX 发行版？

LaTeX 发行版包含：

- **TeX 引擎**（如 pdfTeX、XeTeX、LuaTeX）；  
- **包管理器**，用于下载与更新宏包；  
- **字体与文档样式集**；  
- **编译器**，将 `.tex` 文件转换为 `.pdf`；  
- **内置编辑器**（可选）。

简而言之，发行版是使用 LaTeX 的基础。

---

## 3. 三大发行版对比

| **方面** | **MiKTeX** | **MacTeX** | **TeX Live** |
|-----------|-------------|-------------|---------------|
| **平台** | 主要为 Windows，也支持 macOS 和 Linux | 仅限 macOS | Windows、macOS、Linux |
| **安装大小** | 约 200 MB（基础版） | 约 4 GB | 约 4 GB |
| **安装类型** | 按需模块化安装 | 完整安装 | 完整或自定义 |
| **包管理器** | MiKTeX Console (GUI) | TeX Live Utility | `tlmgr` (命令行) |
| **更新频率** | 频繁 | 每年一次（含小更新） | 每年一次 |
| **易用性** | ★★★★★ | ★★★★☆ | ★★★☆☆ |
| **自动安装包** | 是（默认） | 否 | 可启用 |
| **自带编辑器** | TeXworks | TeXShop | TeXworks |
| **安装后大小** | 1–4 GB | 约 7 GB | 5–7 GB |
| **许可证** | 开源 | 开源 | 开源 |
| **用户社区** | 庞大 | 专注于 macOS | 极大 |
| **推荐用途** | Windows 初学者 | macOS 用户 | 高级用户与 Linux 用户 |

---

## 4. 在 Windows 上安装 MiKTeX

### 步骤 1：下载安装程序

1. 打开 [https://miktex.org/download](https://miktex.org/download)  
2. 选择 **Windows 版本**  
3. 下载 **MiKTeX 安装包**（约 200 MB）

### 步骤 2：安装过程
1. 双击安装文件  
2. 选择 *“Install just for me”*（无需管理员权限）  
3. 按提示完成安装  

### 步骤 3：配置选项
- **自动安装缺失包** → 选择 *Yes*  
- **纸张大小** → 设置为 *A4*  
- 点击 *Start* 开始安装  

### 步骤 4：验证安装
```bash
pdflatex --version
```
若显示 MiKTeX 版本号，则安装成功。

### 步骤 5：更新包
1. 打开 **MiKTeX Console**  
2. 点击 **Updates → Check for updates → Update now**

---

## 5. 在 macOS 上安装 MacTeX

1. 打开 [https://www.tug.org/mactex/](https://www.tug.org/mactex/)  
2. 下载 **MacTeX.pkg**（约 4 GB）  
3. 或下载 **BasicTeX**（约 100 MB）

安装步骤：  
1. 双击 `MacTeX.pkg`  
2. 按照提示操作并输入管理员密码  
3. 等待 10–20 分钟完成安装  

验证：
```bash
pdflatex --version
```
若输出 pdfTeX 版本信息，则安装成功。

更新包：使用 **TeX Live Utility → Update All Packages**。

编辑器 **TeXShop** 会自动安装，位置在：  
`Applications/TeX/TeXShop.app`。

---

## 6. 在 Linux 上安装 TeX Live

### 方法一：使用包管理器（推荐）

**Ubuntu/Debian:**
```bash
sudo apt update
sudo apt install texlive-full
```

**Fedora/RHEL:**
```bash
sudo dnf install texlive-scheme-full
```

**Arch Linux:**
```bash
sudo pacman -S texlive-most
```

### 方法二：手动安装（高级用户）

```bash
wget https://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz
tar -xzf install-tl-unx.tar.gz
cd install-tl-*/
sudo perl install-tl
```

添加 PATH：

```bash
export PATH=/usr/local/texlive/2024/bin/x86_64-linux:$PATH
source ~/.bashrc
```

---

## 7. 推荐的 LaTeX 编辑器

| **编辑器** | **平台** | **主要特点** |
|-------------|--------------|----------------------|
| **TeXstudio** | Windows, macOS, Linux | 功能全面、自动补全、集成 PDF |
| **Overleaf** | 在线 | 无需安装，实时协作 |
| **VS Code + LaTeX Workshop** | 跨平台 | 现代化、灵活、支持 Git |
| **TeXworks** | 内置 | 轻量级、适合初学者 |
| **LyX** | Windows, macOS, Linux | 类似 Word 的界面（所见即所得） |

---

## 8. 测试安装

创建 `test.tex` 文件：

```latex
\documentclass{article}
\usepackage[utf8]{inputenc}
\title{LaTeX 测试文档}
\author{您的姓名}
\date{\today}

\begin{document}
\maketitle

\section{简介}
这是我的第一篇 LaTeX 文档。

\section{公式示例}
毕达哥拉斯定理：$a^2 + b^2 = c^2$

\[
\int_0^\infty e^{-x^2} dx = \frac{\sqrt{\pi}}{2}
\]
\end{document}
```

编译命令：
```bash
pdflatex test.tex
```
若生成 `test.pdf` 文件，则安装成功。

---

## 9. 常见问题与解决方案

| **问题** | **解决方法** |
|-----------|----------------|
| 找不到包 | 启用自动安装功能（MiKTeX）或执行 `tlmgr install <包名>` |
| `pdflatex` 命令无效 | 确认 PATH 配置正确并重启终端 |
| 字体错误 | 在 Linux 中运行 `sudo fc-cache -fv` 或重新安装 MiKTeX |
| 编译失败 | 检查 `.log` 文件并确认所有依赖包已安装 |

---

## 10. 建议与维护

### 初学者推荐：
- Windows → **MiKTeX + TeXstudio**  
- macOS → **MacTeX + TeXShop**  
- Linux → **TeX Live + TeXstudio**

### 高级用户推荐：
- 选择 **TeX Live** 以保持跨平台一致性  
- 使用 **VS Code + LaTeX Workshop**  
- 通过 Git 管理项目版本

### 系统维护：
- 定期更新宏包  
- 清理临时文件（`.aux`, `.log`）  
- 备份模板与自定义样式

---

## 11. 更多学习资源

- [LaTeX Project](https://www.latex-project.org/)  
- [CTAN（综合 TeX 归档网络）](https://ctan.org/)  
- [LaTeX Wikibook](https://en.wikibooks.org/wiki/LaTeX)  
- [TeX Live 官方文档](https://www.tug.org/texlive/doc.html)  
- [TeX Stack Exchange](https://tex.stackexchange.com/)

---

## 12. 总结

选择合适的 LaTeX 发行版取决于您的操作系统和需求：

- **MiKTeX** → 轻量级、适合初学者  
- **MacTeX** → 稳定、适合 macOS 用户  
- **TeX Live** → 通用、适用于所有平台  

安装完成后，您即可开始撰写论文、学术文章或书籍，获得专业的排版效果。

> **祝您在 LaTeX 的世界中创作愉快——这是一种优雅而强大的写作工具。**

