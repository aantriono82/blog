# 使用 LaTeX 绘制写轮眼与轮回眼

本文讲述了如何使用 **LaTeX**（主要使用 TikZ 包）绘制《火影忍者疾风传》中最具代表性的两种眼睛——**写轮眼（Sharingan）** 和 **轮回眼（Rinnegan）**。

---

<!--more-->

> 在动画《火影忍者》中，有几种强大的“瞳术”。**轮回眼（Rinnegan）** 与 **写轮眼（Sharingan）** 是三大瞳术（*Dōjutsu*）中最强的两种。  
> 写轮眼是宇智波一族的血继限界，可以复制忍术、幻术和体术等。  
> **轮回眼** 则是结合了大筒木因陀罗与阿修罗的力量而觉醒，拥有生死掌控之能，甚至能在瞬间抽取灵魂。

## 简介
本文将介绍如何利用 **LaTeX** 绘制 **写轮眼** 与 **轮回眼**。  
主要使用的宏包为 `TikZ` 和 `fadings`，颜色定义使用 `\definecolor` 命令。

---

## 1. 写轮眼 (Sharingan)
在《火影忍者》中，写轮眼有多种形态：  
- 普通写轮眼（带勾玉）  
- 万花筒写轮眼（Mangekyō Sharingan）  
- 永恒万花筒写轮眼（Eternal Mangekyō Sharingan）  

这里我们绘制的是最基本的三勾玉写轮眼。

### 步骤：
1. 使用 `standalone` 文档类并启用 `tikz`：

    ```latex
    \documentclass[tikz]{standalone}
    ```

2. 调用 TikZ 库并创建渐变效果：

    ```latex
    \usetikzlibrary{fadings}
    \tikzfading[name=mripate sasuke, inner color=transparent!0, outer color=transparent!40]
    ```

3. 开始绘图环境：

    ```latex
    \begin{tikzpicture}
    ...
    \end{tikzpicture}
    ```

4. 绘制黑色背景：

    ```latex
    \fill[black] (-4,-4) rectangle (4,4);
    ```

5. 绘制红色主圆（眼球）：

    ```latex
    \fill[red, path fading=mripate sasuke] (0,0) circle (3);
    ```

6. 添加黑色内圈和瞳孔：

    ```latex
    \draw[thick] (0,0) circle (2);
    \fill (0,0) circle (0.3);
    ```

7. 绘制三勾玉符号：

    ```latex
    \foreach\i in {80,200,320}
    \fill[rotate=\i] (2,0) ++ (-30:0.2)
      arc (330:90:0.2) arc (90:-60:0.3) to[out=60,in=-30] cycle;
    ```

8. 结束文档：

    ```latex
    \end{document}
    ```

**最终效果：**

![Sharingan](sharingan.png "写轮眼")

---

## 2. 轮回眼 (Rinnegan)
轮回眼由因陀罗与阿修罗的力量结合而生，拥有“六道之力”，可通过不同身体施展六种不同能力（例如佩恩与带土）。

### 步骤：
1. 使用 `standalone` 文档类：

    ```latex
    \documentclass[tikz]{standalone}
    ```

2. 定义颜色与基础形状：

    ```latex
    \definecolor{rinnegan}{HTML}{C7B7D1}
    \newcommand{\mripaterinnegan}{
      (-10.3,-4.6) to[out=5,in=180] (0,-4.4)
      to[out=0,in=250,looseness=1.2] (10.6,4)
      to[out=160,in=55,looseness=1.2] cycle;
    }
    ```

3. 绘制主体：

    ```latex
    \begin{tikzpicture}
    ...
    \end{tikzpicture}
    ```

4. 绘制轮回眼主图及瞳孔：

    ```latex
    \fill[rinnegan]\mripaterinnegan;
    \fill (0,0) circle (0.4);
    ```

5. 添加同心圆线条：

    ```latex
    \begin{scope}
      \clip\mripaterinnegan;
      \foreach\i in {1.3,2.7,4.1,5.8,7.3,8.9,10.5}
        \draw (0,0) circle (\i);
      \fill[gray,fill opacity=0.8,shift={(-0.4,-0.5)},even odd rule]
        (-12,-6) rectangle (12,6) \mripaterinnegan;
    \end{scope}
    ```

6. 加深外部区域：

    ```latex
    \fill[even odd rule] (-12,-10) rectangle (12,8) \mripaterinnegan;
    ```

7. 结束文档：

    ```latex
    \end{document}
    ```

**最终效果：**  

![Rinnegan](rinnegan.png "轮回眼")

---

## 3. 总结
通过本练习，我们学习了如何利用 **LaTeX** 和 **TikZ** 以数学方式绘制《火影忍者》中独特的瞳术符号。  
这一过程展示了坐标、点、线与面如何组合形成精确而美观的图像——完美体现了 **几何与 TeX 逻辑之美**。是不是很有趣呢？😄

---

## 参考资料
1. *Drawing of Sharingan and Rinnegan Eyes.*  
   [https://tex.stackexchange.com/questions/680546/drawing-of-sharingan-and-rinnegan-eyes](https://tex.stackexchange.com/questions/680546/drawing-of-sharingan-and-rinnegan-eyes)  
   （访问时间：2023 年 3 月 24 日）

2. *写轮眼 vs 轮回眼：谁更强？*  
   [https://www.greenscene.co.id/2020/08/17/naruto-sharingan-vs-rinnegan-mana-yang-lebih-kuat/](https://www.greenscene.co.id/2020/08/17/naruto-sharingan-vs-rinnegan-mana-yang-lebih-kuat/)  
   （访问时间：2023 年 3 月 25 日）

