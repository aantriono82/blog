# 技術指南：完整且高效地編譯 LaTeX 文件的方法


編譯（compilation）是將 LaTeX 命令轉換為可列印文件的過程。  
本文介紹 LaTeX 的工作方式、可用的編譯器（compiler）類型、處理順序，以及如何高效地解決錯誤。

---

<!--more-->

## 前言

LaTeX 是一種專為科學與技術文本設計的高品質文件排版系統。  
與一般的文字處理器（word processor）不同，LaTeX 文件必須先**編譯（compile）**，才能將 `.tex` 檔案轉換為最終輸出格式，例如 `.pdf`、`.dvi` 或 `.ps`。

{{< admonition >}}
**注意**：本文由人工智慧技術協助生成，並經人工審核以確保資訊的準確性與清晰度。
{{< /admonition >}}

---

## 1. 什麼是 LaTeX 編譯（Compilation）？

LaTeX 編譯是由編譯器（compiler）讀取來源檔（通常副檔名為 `.tex`）、解析指令（如 `\section{}`、`\usepackage{}` 等），並輸出最終檔案（如 `.pdf`）的過程。

簡而言之：

```
dokumen.tex → [compiler] → dokumen.pdf
```

這個過程與 Microsoft Word 等一般文字處理器不同，LaTeX 將**內容撰寫**與**輸出生成**分離，讓格式更一致且可重現。

---

## 2. 常見的 LaTeX 編譯器（Compiler）類型

| 編譯器 | 主要輸出格式 | 優點 | 缺點 |
|---------|----------------|------|------|
| **pdfLaTeX** | 直接輸出 PDF | 快速、穩定、與許多套件相容 | 僅支援 TeX 字型與 ASCII 輸入 |
| **XeLaTeX** | PDF | 支援 Unicode 與系統字型（TTF/OTF） | 編譯速度稍慢 |
| **LuaLaTeX** | PDF | 支援 Lua 腳本，效能高 | 對舊套件相容性較低 |
| **LaTeX → DVI → PS → PDF** | PDF/DVI | 傳統方法，適合舊專案 | 編譯流程較長，現今少用 |

> 💡 **建議：** 一般文件可使用 `pdfLaTeX`；若包含非拉丁字母（如中文、日文、阿拉伯文），建議使用 `XeLaTeX`；若需圖形或程式化控制，可用 `LuaLaTeX`。

---

## 3. 文件編譯流程

當執行編譯時，LaTeX 系統會依序進行以下階段：

1. **讀取 `.tex` 檔案** — 處理前導區（preamble）與內容。  
2. **建立文件結構** — 生成目錄、標籤、參照與索引。  
3. **排版數學符號、圖片與表格。**  
4. **生成輔助檔（auxiliary files）**：  
   - `.aux` → 用於交叉引用（cross-reference，如 `\ref`, `\cite`）  
   - `.toc` → 目錄（table of contents）  
   - `.log` → 錯誤記錄  
5. **產生最終輸出檔（如 `.pdf` 或 `.dvi`）**。

由於使用了輔助檔，**通常需多次編譯**以更新交叉引用、目錄或參考文獻。

---

## 4. 在終端機（Terminal）中進行編譯

若使用本機系統（Windows、macOS、Linux），可透過命令列（command line）進行：

```bash
pdflatex dokumen.tex
bibtex dokumen
pdflatex dokumen.tex
pdflatex dokumen.tex
```

步驟說明：  
1. 第一次編譯：生成 `.aux` 和 `.toc`。  
2. 執行 `bibtex`（若包含參考文獻）。  
3. 再次編譯以更新引用。  
4. 最後一次編譯生成最終輸出。

> ⚙️ 若使用 `biber`（搭配 `biblatex`），請將 `bibtex` 改為 `biber dokumen`。

---

## 5. 在編輯器（Editor）中編譯

除終端機外，也可直接於 LaTeX 編輯器中執行編譯。

![overleaf](overleaf.png "Tampilan antarmuka di Overleaf")

### 5.1. Overleaf（線上）
- 每次儲存後自動編譯。  
- 可於 **Menu → Compiler → pdfLaTeX/XeLaTeX** 中選擇編譯器。  
- 無需本機安裝。

### 5.2. TeXworks / TeXstudio（離線）
- 按 **Ctrl + T** 或點擊「Typeset」圖示。  
- 可於下拉選單中選擇編譯器。  
- 適合 Windows/macOS 使用者。

![overleaf](texstudio.png "Tampilan antarmuka di TeXstudio")


### 5.3. Visual Studio Code + LaTeX Workshop
- 現代化環境中最受歡迎的擴充套件。  
- 支援「自動編譯鏈」（build chain），例如：`pdflatex → bibtex → pdflatex → pdflatex`。  
- 設定檔位於 `.vscode/settings.json`。

範例設定：

```json
"latex-workshop.latex.recipes": [
  {
    "name": "pdflatex -> bibtex -> pdflatex x2",
    "tools": ["pdflatex", "bibtex", "pdflatex", "pdflatex"]
  }
]
```

---

## 6. 常見錯誤與解決方式

| 錯誤訊息 | 原因 | 解決方案 |
|------------|--------|-----------|
| `! Undefined control sequence.` | 指令未定義 | 確認是否已載入所需套件（`\usepackage{}`） |
| `! LaTeX Error: File 'xxx.sty' not found.` | 缺少套件 | 透過套件管理器安裝（`tlmgr install xxx`） |
| `! Missing $ inserted.` | 數學模式錯誤 | 確保數學公式以 `$...$` 或 `\[...\]` 包圍 |
| `Package hyperref Warning: Token not allowed in a PDF string` | 超連結中有非法字元 | 使用 `{}` 包裹或更改特殊字元 |
| 參照失效或空白 | 尚未多次編譯 | 請重複編譯 2–3 次 |

> 🧩 **提示：** 可查看 `dokumen.log` 檔以獲取錯誤詳細資訊與行號。

---

## 7. 現代化工作流程與自動化

現今許多用戶利用自動化工具提升編譯效率：

- **latexmk** — 自動執行所有必要步驟（LaTeX、BibTeX、索引等）  
  ```bash
  latexmk -pdf dokumen.tex
  ```
- **arara** — 基於註解指令的編譯系統  
  ```latex
  % arara: pdflatex
  % arara: bibtex
  % arara: pdflatex
  % arara: pdflatex
  ```
- **Makefile** — 適用於大型多檔專案。

使用這些自動化工具，只需一條指令即可完成整個編譯流程。

---

## 8. 結論

編譯是 LaTeX 系統的核心，負責將原始碼轉換為高品質輸出文件。  
理解編譯器（compiler）的工作方式、執行順序及錯誤處理，能顯著提升撰寫學術文件的效率與專業度。

無論您使用 Overleaf、VS Code 或終端機，原則相同：  
**確保所有套件、參考與來源在最終編譯前均已準備完善。**

---

### 參考資料

- The LaTeX Project — [https://www.latex-project.org](https://www.latex-project.org)  
- Overleaf 文件：*Understanding PDF Compilation* — [https://www.overleaf.com/learn/latex](https://www.overleaf.com/learn/latex)  
- TeX Users Group (TUG)：*LaTeX Compilation Workflow* — [https://tug.org](https://tug.org)  
- Wikibooks：*LaTeX/Installing and Compiling* — [https://en.wikibooks.org/wiki/LaTeX/Installing_and_Compiling](https://en.wikibooks.org/wiki/LaTeX/Installing_and_Compiling)

