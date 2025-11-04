# The Café Wall Illusion: Straight Lines That Appear Curved


{{< admonition >}}

This article explores the Café Wall Illusion, where parallel lines appear curved or slanted due to alternating black and white squares and horizontal offsets. Built using LaTeX TikZ, the article provides a complete explanation of both the code and the perceptual mechanisms behind it."

{{< /admonition >}}

## Introduction

Have you ever looked at a tiled wall or brick pattern that seemed wavy even though the lines were perfectly straight?  
This is known as the **Café Wall Illusion**, an optical illusion where **parallel horizontal lines** appear tilted or curved due to the **alternating contrast of black and white tiles** and **horizontal offset between rows**.

In this article, we recreate this illusion using **LaTeX TikZ**, explaining both the **structure of the source code** and the **visual science** behind the phenomenon.

---

## LaTeX Source Code

Below is the full LaTeX code used to generate the Café Wall pattern:

```latex
\documentclass[tikz]{standalone}
\usetikzlibrary{calc}
\begin{document}
    \pagecolor{gray}
    \begin{tikzpicture}
        \pgfmathsetmacro{\offsety}{.05};
        \foreach \y / \offsetx in {0/0.3,1/0.5,2/0.3,3/0,4/0.3,5/0.5,6/0.3,7/0,8/0.3}
            \foreach \x in {0,...,10}{%
                \pgfmathifthenelse{mod(\x,2) == 0}{"black"}{"white"}
                \fill[\pgfmathresult] ($ (\x,\y)+(\offsetx,\offsety*\y) $) rectangle +(1,1);
            }
    \end{tikzpicture}
\end{document}
```
The output produced:

![ilusi](ilusi.png " They are or not parallels? ")

---

## Explanation of Code Structure

### **Document Declaration**
```latex
\documentclass[tikz]{standalone}
```
The `standalone` class generates only the figure without additional margins or headers.  
The `tikz` option loads the **TikZ** package for creating vector graphics in LaTeX.

---

### **Library Import**
```latex
\usetikzlibrary{calc}
```
The `calc` library allows for dynamic coordinate calculations and mathematical positioning within TikZ.

---

### **Page Background Color**
```latex
\pagecolor{gray}
```
Applies a gray background to enhance contrast between black and white squares.

---

### **Drawing Area**
```latex
\begin{tikzpicture}
```
Starts the TikZ drawing environment that contains all visual elements.

---

### **Vertical Offset Variable**
```latex
\pgfmathsetmacro{\offsety}{.05};
```
Defines a small vertical offset of `0.05` per row, introducing subtle wave-like distortions that enhance the illusion.

---

### **Row Loop and Horizontal Offset**
```latex
\foreach \y / \offsetx in {0/0.3,1/0.5,2/0.3,3/0,4/0.3,5/0.5,6/0.3,7/0,8/0.3}
```
- Iterates over nine rows (`\y` from 0 to 8).  
- Each row has a distinct horizontal offset (`\offsetx`), alternating shifts that make the straight lines appear tilted.

---

### **Column Loop and Square Colors**
```latex
\foreach \x in {0,...,10}{
    \pgfmathifthenelse{mod(\x,2) == 0}{"black"}{"white"}
    \fill[\pgfmathresult] ($ (\x,\y)+(\offsetx,\offsety*\y) $) rectangle +(1,1);
}
```
Step-by-step breakdown:
- The outer loop draws 11 squares per row.  
- `\pgfmathifthenelse{mod(\x,2) == 0}{"black"}{"white"}` alternates square colors (black for even, white for odd).  
- `\fill[...] ... rectangle +(1,1);` draws 1×1 unit squares at the calculated positions.  
- The position formula shifts each square horizontally and vertically for illusion enhancement.

---

### **Closing the Environment**
```latex
\end{tikzpicture}
```
Ends the TikZ environment. The result is a staggered tile pattern that produces a strong illusion of curved or slanted lines.

---

## Visual and Perceptual Analysis

Although all rows of tiles are mathematically parallel, our brain misinterprets them because of **lateral inhibition** — a neural mechanism where high-contrast edges enhance perceived boundaries.

| Factor | Visual Effect |
|--------|----------------|
| Row offset | Creates slanted appearance |
| Black–white contrast | Increases perceptual distortion |
| Gray background | Adds depth and amplifies curvature illusion |

---

## Experiment and Variation

| Parameter | Function | Visual Effect |
|------------|-----------|----------------|
| `\offsetx` | Horizontal shift between rows | Adjusts illusion strength |
| `\offsety` | Vertical offset | Introduces wave-like appearance |
| Color palette | Change square colors | Alters perceived contrast |
| Square size | Modify `(1,1)` | Denser grid strengthens illusion |

Example variation:
```latex
\foreach \y / \offsetx in {0/0,1/0.2,2/0.4,3/0.6}{
    \foreach \x in {0,...,12}{
        \pgfmathifthenelse{mod(\x,2)==0}{"black"}{"white"}
        \fill[\pgfmathresult] ($ (\x,\y)+(\offsetx,0.05*\y) $) rectangle +(1,1);
    }
}
```

---

## Scientific and Artistic Relevance

The Café Wall Illusion bridges the gap between **visual psychology**, **neuroscience**, and **mathematical art**.  
It provides insight into:
- **Perceptual psychology** — understanding how contrast and alignment affect visual interpretation.  
- **Visual neuroscience** — studying edge detection and spatial inhibition.  
- **Graphic design and architecture** — creating visual depth or motion effects.  
- **Mathematical aesthetics** — blending geometry with perception.

---

## Conclusion

The Café Wall Illusion demonstrates that human perception is **context-dependent** and **contrast-driven**.  
Using **LaTeX TikZ**, we can mathematically and artistically reconstruct this optical phenomenon, merging **science, art, and geometry** into a single elegant visualization.

---

## References

1. Gregory, R. L. (1997). *Eye and Brain: The Psychology of Seeing.* Oxford University Press.  
2. Wade, N. J. (1986). *Perception and Illusion: Historical Perspectives.* Springer.  
3. Fraser, J. (1908). *A New Visual Illusion of Direction.* British Journal of Psychology.  
4. PGF/TikZ Manual, Version 3.1.10 (2023).  

---

**Written by:** [Aan Triono](https://www.aantriono.com)  
**License:** CC BY-SA 4.0

