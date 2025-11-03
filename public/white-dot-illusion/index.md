# White Dot Illusion: Perceptual Contrast in a Dark Grid Pattern


This article discusses the visual illusion of white dots appearing in a dark grid pattern, where the brain creates contrast perceptions that are not physically present. Built using LaTeX PSTricks, it provides a complete explanation of the code structure and the perceptual mechanisms behind it.

<!--more-->

{{< admonition >}}
**Note:** This article was generated with the help of AI technology and has been manually reviewed to ensure accuracy and clarity.
{{< /admonition >}}


## Introduction

Optical illusions reveal how the human brain interprets visual information beyond mere physical reality. One fascinating example is the **Hermann Grid Illusion**, also known as the **White Dot Illusion**, where white or gray dots appear and disappear at the intersections of dark grid lines.

This phenomenon occurs due to **lateral inhibition** in the retina — a neural mechanism that enhances contrast but also leads to perceptual distortions.  
In this article, we recreate this effect using **LaTeX PSTricks** and explain the structure of the code along with the underlying perceptual science.

---

## LaTeX Source Code

Below is the complete LaTeX source used to visualize the illusion:

```latex
\documentclass[pstricks,border=12pt]{standalone}
\newpsstyle{gridstyle}
{
    gridlabels=0,
    gridwidth=6pt,
    subgriddiv=1,
    gridcolor=gray,
}
\begin{document}
\begin{pspicture}(8,8)
    \psframe*(8,8)
    \psgrid[style=gridstyle]
    \psset{linecolor=white}
    \multips(0,1)(0,1){7}{\multips(1,0)(1,0){7}{\qdisk(0,0){4.242pt}}}
\end{pspicture}
\end{document}
```

---

The output produced:

![ilusi titik](ilusi.png "White Dot Illusion")

## Explanation of Code Structure

### **Document Declaration**
```latex
\documentclass[pstricks,border=12pt]{standalone}
```
Specifies that the document uses the `standalone` class, which produces a single figure without page margins or headers.  
The `pstricks` option enables **PSTricks**, a LaTeX package for creating PostScript-based vector graphics.

---

### **Defining the Grid Style**
```latex
\newpsstyle{gridstyle}
{
    gridlabels=0,
    gridwidth=6pt,
    subgriddiv=1,
    gridcolor=gray,
}
```
Defines a new drawing style named `gridstyle`:
- `gridlabels=0` disables coordinate labels.  
- `gridwidth=6pt` sets grid line thickness.  
- `gridcolor=gray` colors the grid lines gray.  
- `subgriddiv=1` ensures no subgrid divisions are drawn.

---

### **PSTricks Drawing Environment**
```latex
\begin{pspicture}(8,8)
```
Creates a drawing area of 8x8 units where all graphical elements are placed.

---

### **Background and Grid**
```latex
\psframe*(8,8)
\psgrid[style=gridstyle]
```
- `\psframe*(8,8)` draws a solid black square background.  
- `\psgrid[style=gridstyle]` overlays a gray grid on top of the background using the defined style.

---

### **Setting Line Color**
```latex
\psset{linecolor=white}
```
Sets the current drawing color to white, so that the subsequent dots will contrast with the dark background.

---

### **Drawing White Dots Using `multips`**
```latex
\multips(0,1)(0,1){7}{\multips(1,0)(1,0){7}{\qdisk(0,0){4.242pt}}}
```
Draws the pattern of white dots forming the grid illusion:
- The first `\multips` repeats the inner pattern vertically 7 times.  
- The inner `\multips` repeats horizontally 7 times per row.  
- `\qdisk(0,0){4.242pt}` draws a small white circular dot of radius ≈ 4.24pt at each grid intersection.

---

### **Closing the Environments**
```latex
\end{pspicture}
\end{document}
```
Ends both the drawing and the document environments, generating the final figure.

---

## Visual and Perceptual Analysis

The final output produces a dark grid where **white dots seem to flicker or disappear** at intersections.  
This illusion arises from **lateral inhibition** — when bright and dark areas interact, neurons responsible for detecting light suppress their neighbors’ activity, leading to **false contrast enhancement**.

| Observation | Neural Explanation |
|--------------|--------------------|
| Dots vanish at intersections | Lateral inhibition reduces local contrast |
| Dots reappear when stared at directly | Focused vision minimizes surround inhibition |

---

## Experimental Variations

You can adjust the parameters in the code to explore perceptual effects:

| Parameter | Purpose | Visual Effect |
|------------|----------|----------------|
| `gridwidth` | Grid line thickness | Alters strength of illusion |
| `gridcolor` | Grid color | Affects contrast intensity |
| Dot size (`\qdisk`) | Controls dot visibility | Larger dots reduce illusion |
| Number of repetitions | Changes grid density | More intersections strengthen illusion |

Example modification:
```latex
\psgrid[style=gridstyle,gridcolor=lightgray]
\qdisk(0,0){3pt}
```

---

## Scientific and Artistic Relevance

The Hermann Grid Illusion bridges **visual neuroscience**, **mathematics**, and **art**.  
It demonstrates how simple geometry can expose deep insights into **human perception**. Applications include:
- **Cognitive psychology** — studying spatial inhibition and lightness perception.  
- **Visual design** — understanding how contrast guides attention.  
- **Mathematical art** — turning perceptual science into geometric beauty.

---

## Conclusion

The White Dot Illusion exemplifies how perception is **context-dependent**, not purely physical.  
By using **LaTeX PSTricks**, we can mathematically and aesthetically recreate this effect, merging **science and art** in a single figure.

---

## References

1. Hermann, L. (1870). *Eine Erscheinung simultanen Contrastes.* Pflügers Archiv für die gesamte Physiologie.  
2. Coren, S., & Girgus, J. S. (1978). *Seeing is Deceiving: The Psychology of Visual Illusions.* Lawrence Erlbaum.  
3. Gregory, R. L. (1997). *Eye and Brain: The Psychology of Seeing.* Oxford University Press.  
4. PSTricks User Manual, Version 3.1.8 (2023).  

---

**Written by:** [Aan Triono](https://www.aantriono.com)  
**License:** CC BY-SA 4.0

