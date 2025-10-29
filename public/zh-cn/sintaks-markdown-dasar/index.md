# Markdown 基础语法


本文介绍了在 Hugo 内容文件中可使用的 Markdown 基本语法示例。

<!--more-->

{{< admonition >}}
本文内容转载自 [Grav 原始页面](https://learn.getgrav.org/content/markdown)。

如需更完整的说明，请参阅页面 [Markdown 语法](../theme-documentation-content#extended-markdown-syntax)。
{{< /admonition >}}

为网络撰写内容是一项艰巨的任务。虽然 WYSIWYG 编辑器在一定程度上减轻了负担，但它们通常会生成复杂或杂乱的 HTML 页面。

Markdown 是一种更简洁的方式，用纯文本来编写 HTML，没有传统格式的繁琐与缺陷。

Markdown 的主要优点包括：

1. Markdown 易学、符号少，写作效率高。
2. 减少语法错误的可能性。
3. 输出有效的 XHTML 代码。
4. 内容与样式分离，不会破坏网页的整体外观。
5. 可以使用任何文本编辑器或 Markdown 应用程序编写。

Markdown 作者 **John Gruber** 如此说道：

> Markdown 的主要设计目标是让格式化文本尽可能易读。  
> 其理念是：即使不进行渲染，Markdown 文档本身也应像普通文本一样自然可读。  
> Markdown 的语法受到一些文本到 HTML 过滤器的启发，但最主要的灵感来自传统纯文本电子邮件的格式。  
>
> {{< style "text-align: right;" >}}-- _John Gruber_{{< /style >}}

接下来，让我们一起了解 Markdown 的主要元素，以及它们在 HTML 中的呈现方式！

{{< admonition tip >}}
:smile: 收藏此页面，方便日后参考！
{{< /admonition >}}

## 1 标题（Headings）

从 `h2` 到 `h6` 的标题通过在文本前添加 `#` 来实现：

```markdown
## h2 标题
### h3 标题
#### h4 标题
##### h5 标题
###### h6 标题
```

生成的 HTML 如下：

```html
<h2>h2 标题</h2>
<h3>h3 标题</h3>
<h4>h4 标题</h4>
<h5>h5 标题</h5>
<h6>h6 标题</h6>
```

{{< admonition note "自定义标题 ID" >}}
为标题添加自定义 ID，只需在标题末尾加上花括号：

```markdown
### 大标题 {#custom-id}
```

生成的 HTML 如下：

```html
<h3 id="custom-id">大标题</h3>
```
{{< /admonition >}}

## 2 注释（Comments）

Markdown 中的注释使用 HTML 语法。

```html
<!-- 这是注释 -->
```

下面的注释 **不会显示**：

<!-- 这是注释 -->

## 3 分隔线（Horizontal Rules）

在 Markdown 中，可以使用以下任意方式创建 `<hr>`：

* `___`：三个下划线  
* `---`：三个短横线  
* `***`：三个星号  

结果如下：
___
---
***

## 4 段落（Paragraphs）

普通文本会被包裹在 `<p></p>` 标签中：

```markdown
这是一个段落。
```

输出的 HTML：

```html
<p>这是一个段落。</p>
```

## 5 内联 HTML

如果需要使用特定 HTML 标签（带 class），可直接写入 HTML：

```html
Markdown 段落。

<div class="class">
    这里是 <b>HTML</b>
</div>

Markdown 段落。
```

## 6 文本强调（Emphasis）

### 加粗（Bold）

```markdown
**加粗文本**
__加粗文本__
```

HTML 输出：

```html
<strong>加粗文本</strong>
```

### 斜体（Italic）

```markdown
*斜体文本*
_斜体文本_
```

HTML 输出：

```html
<em>斜体文本</em>
```

### 删除线（Strikethrough）

```markdown
~~带删除线的文本~~
```

HTML 输出：

```html
<del>带删除线的文本</del>
```

### 组合使用

```markdown
***加粗并斜体***
~~**删除线加粗**~~
~~*删除线斜体*~~
~~***加粗、斜体和删除线***~~
```

## 7 引用块（Blockquotes）

使用 `>` 添加引用：

```markdown
> 这是一个引用块。
```

嵌套引用：

```markdown
> 第一层
>> 第二层
```

## 8 列表（Lists）

### 无序列表

```markdown
* 第一项
- 第二项
+ 第三项
```

### 有序列表

```markdown
1. 第一项
2. 第二项
3. 第三项
```

### 任务列表

```markdown
- [x] 已完成
- [ ] 未完成
```

## 9 代码（Code）

### 行内代码

```markdown
在此例中，`<section></section>` 将被包裹为代码。
```

### 多行代码块

```markdown
```js
console.log("Hello Markdown!");
```
```

## 10 表格（Tables）

```markdown
| 选项 | 描述 |
| ---- | ---- |
| data | 数据文件路径 |
| engine | 模板引擎 |
| ext | 文件扩展名 |
```

输出如下：

| 选项 | 描述 |
| ---- | ---- |
| data | 数据文件路径 |
| engine | 模板引擎 |
| ext | 文件扩展名 |

## 11 链接（Links）

```markdown
<https://assemble.io>
[Assemble](https://assemble.io)
```

## 12 脚注（Footnotes）

```markdown
这是脚注示例 [^1]

[^1]: 这里是脚注说明。
```

## 13 图片（Images）

```markdown
![小黄人](https://octodex.github.com/images/minion.png)
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg)
![Dojocat](https://octodex.github.com/images/dojocat.jpg)
```

![小黄人](https://octodex.github.com/images/minion.png)
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg)
![Dojocat](https://octodex.github.com/images/dojocat.jpg)

---

本文到此结束，希望对你有所帮助！😙

