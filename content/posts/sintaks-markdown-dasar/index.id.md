---
weight: 4
title: "Sintaks Markdown Dasar"
date: 2025-09-01T21:57:40+08:00
# lastmod: 2025-10-01T16:45:40+08:00
draft: false
author: "Aan Triono"
authorLink: "https://www.aantriono.com"
description: "Artikel ini membahas tentang sintaks markdown dasar."
images: []
resources:
featuredImage: "featured-image.png"

tags: ["Markdown"]
categories: ["Markdown"]

math:
enable: true
lightgallery: true
twemoji: true
---

Artikel ini membahas contoh sintaks Markdown dasar yang dapat digunakan dalam file konten Hugo.

<!--more-->

{{< admonition >}}
Artikel ini adalah salinan dari halaman [Grav original](https://learn.getgrav.org/content/markdown).

Jika Anda ingin mengetahui secara lebih lengkap, silakan baca halaman [Sintaks Markdown](../theme-documentation-content#extended-markdown-syntax).

{{< /admonition >}}

Menulis konten untuk Web itu melelahkan. Editor WYSIWYG membantu meringankan tugas ini, tetapi mereka umumnya menghasilkan kode yang rumit, atau lebih buruk lagi, halaman web jelek.

Markdown adalah cara yang lebih baik untuk menulis HTML, tanpa semua kompleksitas dan kekurangan yang biasanya menyertainya.

Beberapa manfaat utama Markdown adalah:

   1. Markdown mudah dipelajari, dengan karakter tambahan minimal, jadi juga lebih cepat untuk menulis konten.
   2. Kurangnya kemungkinan kesalahan saat menulis di Markdown.
   3. Menghasilkan output XHTML yang valid.
   4. Menjaga konten dan tampilan visual terpisah, sehingga Anda tidak dapat mengacaukan tampilan situs Anda.
   5. Tulis di editor teks atau aplikasi Markdown yang Anda sukai.

John Gruber, penulis Markdown, mengatakan seperti ini:


> Tujuan desain utama untuk sintaks pemformatan Markdown adalah membuatnya dapat dibaca sebisa mungkin. 
> Idenya adalah bahwa dokumen yang diformat Markdown harus dapat dipublikasikan sebagai-adalah, sebagai teks biasa, tanpa terlihat seperti itu telah ditandai dengan tag atau petunjuk pemformatan. 
> Sementara sintaks Markdown telah dipengaruhi oleh beberapa filter teks-ke-HTML yang ada, Satu-satunya sumber inspirasi terbesar untuk sintaks Markdown adalah format email teks biasa.
>
> {{< style "text-align: right;" >}}-- _John Gruber_{{< /style >}}

Tanpa penundaan lebih lanjut, mari kita bahas elemen utama Markdown dan seperti apa HTML yang dihasilkan!

{{< admonition tip >}}
:smile: Bookmark halaman ini untuk memudahkan referensi di masa mendatang!
{{< /admonition >}}

## Headings

Headings dari `h2` sampai `h6` dibangun dengan  `#` untuk setiap level:

```markdown
## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading
```

Keluaran HTML terlihat seperti berikut:

```html
<h2>h2 Heading</h2>
<h3>h3 Heading</h3>
<h4>h4 Heading</h4>
<h5>h5 Heading</h5>
<h6>h6 Heading</h6>
```

{{< admonition note "Heading IDs" >}}
Untuk menambahkan ID judul khusus, lampirkan ID khusus dalam kurung kurawal pada baris yang sama dengan judul:

```markdown
### Judul Besar {#custom-id}
```

Keluaran HTML terlihat seperti berikut:

```html
<h3 id="custom-id">Judul Besar</h3>
```
{{< /admonition >}}

## Komentar

Komentar harus kompatibel dengan HTML.

```html
<!--
Ini adalah sebuah komentar
-->
```

Komentar di bawah ini **tidak** boleh dilihat:

<!--
Ini adalah sebuah komentar
-->

## Aturan Horizontal

Elemen HTML `<hr>` adalah untuk menciptakan “tekanan tematik” antara elemen tingkat paragraf. Di Markdown, Anda dapat membuat `<hr>` dengan salah satu cara dari berikut:

* `___`: tiga underscores berturut-turut
* `---`: tiga dashes berturut-turut
* `***`: tiga asterisks berturut-turut

Keluaran yang dihasilkan terlihat seperti berikut.
___
---
***

## Salinan 

Salinan ditulis sebagai normal, teks biasa akan dibungkus dengan `<p></p>` tag dalam HTML yang diberikan.

Jadi salinan tubuh ini:

```markdown
Lorem ipsum dolor sit amet, graecis denique ei vel, at duo primis mandamus. Et legere ocurreret pri,
animal tacimates complectitur ad cum. Cu eum inermis inimicus efficiendi. Labore officiis his ex,
soluta officiis concludaturque ei qui, vide sensibus vim ad.
```

Di HTML terlihat seperti berikut:

```html
<p>Lorem ipsum dolor sit amet, graecis denique ei vel, at duo primis mandamus. Et legere ocurreret pri, animal tacimates complectitur ad cum. Cu eum inermis inimicus efficiendi. Labore officiis his ex, soluta officiis concludaturque ei qui, vide sensibus vim ad.</p>
```

**Baris pemisah** dapat dilakukan dengan satu baris kosong..

## Inline HTML

ika Anda membutuhkan tag HTML tertentu (dengan kelas), Anda cukup menggunakan HTML:

```html
Paragrap di Markdown.

<div class="class">
    Ini adalah <b>HTML</b>
</div>

Paragrap di Markdown.
```

## Emphasis

### Bold

Untuk menekankan cuplikan teks dengan berat font yang lebih berat.

Cuplikan teks berikut dianggap sebagai **teks yang dibold**.

```markdown
**teks yang dibold**
__teks yang dibold__
```

Di HTML terlihat seperti berikut:

```html
<strong>teks yang dibold</strong>
```

### Italics

Untuk menekankan cuplikan teks dengan huruf miring.

Cuplikan teks berikut ini dianggap sebagai _teks yang dicetak miring_.

```markdown
*teks yang dicetak miring*
_teks yang dicetak miring_
```

Di HTML akan terlihat seperti berikut:

```html
<em>teks yang dicetak miring</em>
```

### Strikethrough

Dalam [[GFM]^(GitHub flavored Markdown)](https://github.github.com/gfm/) kamu dapat melakukan strikethroughs.

```markdown
~~Strike through this text.~~
```

Keluaran yang diberikan terlihat seperti ini:
~~Strike through this text.~~

Di HTML terlihat seperti berikut:

```html
<del>Teks ini di-strike through .</del>
```

### Kombinasi

Bold, italics, dan strikethrough dapat dilakukan dalam kombinasi:

```markdown
***bold dan italics***
~~**strikethrough dan bold**~~
~~*strikethrough dan italics*~~
~~***bold, italics dan strikethrough***~~
```

Keluaran yang dihasilkan akan terlihat seperti berikut:

***bold dan italics***

~~**strikethrough dan bold**~~

~~*strikethrough dan italics*~~

~~***bold, italics dan strikethrough***~~

Di HTML terlihat seperti berikut:
```html
<em><strong>bold dan italics</strong></em>
<del><strong>strikethrough dan bold</strong></del>
<del><em>strikethrough dan italics</em></del>
<del><em><strong>bold, italics dan strikethrough</strong></em></del>
```

## Blockquotes

Untuk mengutip blockquotes dari sumber lain dalam dokumen Anda.

Tambahkan `>` sebelum teks apa pun yang ingin Anda kutip:

```markdown
> **Fusion Drive** menggabungkan hard drive dengan penyimpanan flash (solid-state drive) dan menyajikannya sebagai volume logis tunggal dengan ruang kedua drive digabungkan.
```

Keluaran terilhat seperti berikut:

> **Fusion Drive** menggabungkan hard drive dengan penyimpanan flash (solid-state drive) dan menyajikannya sebagai volume logis tunggal dengan ruang kedua drive digabungkan.

Di HTML terlihat seperti berikut:

```html
<blockquote>
  <p>
    <strong>Fusion Drive</strong> menggabungkan hard drive dengan penyimpanan flash (solid-state drive) dan menyajikannya sebagai volume logis tunggal dengan ruang kedua drive digabungkan.
  </p>
</blockquote>
```

Blockquotes juga dapat bertingkat:

```markdown
> Donec massa lacus, ultricies a ullamcorper in, fermentum sed augue.
Nunc augue augue, aliquam non hendrerit ac, commodo vel nisi.
>> Sed adipiscing elit vitae augue consectetur a gravida nunc vehicula. Donec auctor
odio non est accumsan facilisis. Aliquam id turpis in dolor tincidunt mollis ac eu diam.
```

Keluaran terlihat seperti berikut:

> Donec massa lacus, ultricies a ullamcorper in, fermentum sed augue.
Nunc augue augue, aliquam non hendrerit ac, commodo vel nisi.
>> Sed adipiscing elit vitae augue consectetur a gravida nunc vehicula. Donec auctor
odio non est accumsan facilisis. Aliquam id turpis in dolor tincidunt mollis ac eu diam.

## Daftar

### Tidak Berurut

Daftar item di mana urutan item tidak secara eksplisit penting.

Anda dapat menggunakan salah satu simbol berikut untuk menunjukkan bullets untuk setiap item daftar:

```markdown
* valid bullet
- valid bullet
+ valid bullet
```

Sebagai contoh

```markdown
* Lorem ipsum dolor sit amet
* Consectetur adipiscing elit
* Integer molestie lorem at massa
* Facilisis in pretium nisl aliquet
* Nulla volutpat aliquam velit
  * Phasellus iaculis neque
  * Purus sodales ultricies
  * Vestibulum laoreet porttitor sem
  * Ac tristique libero volutpat at
* Faucibus porta lacus fringilla vel
* Aenean sit amet erat nunc
* Eget porttitor lorem
```

Keluaran yang dihasilkan terlihat seperti berikut:

* Lorem ipsum dolor sit amet
* Consectetur adipiscing elit
* Integer molestie lorem at massa
* Facilisis in pretium nisl aliquet
* Nulla volutpat aliquam velit
  * Phasellus iaculis neque
  * Purus sodales ultricies
  * Vestibulum laoreet porttitor sem
  * Ac tristique libero volutpat at
* Faucibus porta lacus fringilla vel
* Aenean sit amet erat nunc
* Eget porttitor lorem

Di HTML seperti berikut:

```html
<ul>
  <li>Lorem ipsum dolor sit amet</li>
  <li>Consectetur adipiscing elit</li>
  <li>Integer molestie lorem at massa</li>
  <li>Facilisis in pretium nisl aliquet</li>
  <li>Nulla volutpat aliquam velit
    <ul>
      <li>Phasellus iaculis neque</li>
      <li>Purus sodales ultricies</li>
      <li>Vestibulum laoreet porttitor sem</li>
      <li>Ac tristique libero volutpat at</li>
    </ul>
  </li>
  <li>Faucibus porta lacus fringilla vel</li>
  <li>Aenean sit amet erat nunc</li>
  <li>Eget porttitor lorem</li>
</ul>
```

### Berurut

Daftar item di mana urutan item secara eksplisit penting.

```markdown
1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa
4. Facilisis in pretium nisl aliquet
5. Nulla volutpat aliquam velit
6. Faucibus porta lacus fringilla vel
7. Aenean sit amet erat nunc
8. Eget porttitor lorem
```

Keluaran yang dihasilkan terlihat seperti berikut:
1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa
4. Facilisis in pretium nisl aliquet
5. Nulla volutpat aliquam velit
6. Faucibus porta lacus fringilla vel
7. Aenean sit amet erat nunc
8. Eget porttitor lorem

Di HTML terlihat seperti berikut::

```html
<ol>
  <li>Lorem ipsum dolor sit amet</li>
  <li>Consectetur adipiscing elit</li>
  <li>Integer molestie lorem at massa</li>
  <li>Facilisis in pretium nisl aliquet</li>
  <li>Nulla volutpat aliquam velit</li>
  <li>Faucibus porta lacus fringilla vel</li>
  <li>Aenean sit amet erat nunc</li>
  <li>Eget porttitor lorem</li>
</ol>
```

{{< admonition tip >}}
Jika Anda hanya menggunakan `1.` untuk setiap nomor, Markdown akan secara otomatis mengurutkan nomor setiap item. Sebagai contoh: 

```markdown
1. Lorem ipsum dolor sit amet
1. Consectetur adipiscing elit
1. Integer molestie lorem at massa
1. Facilisis in pretium nisl aliquet
1. Nulla volutpat aliquam velit
1. Faucibus porta lacus fringilla vel
1. Aenean sit amet erat nunc
1. Eget porttitor lorem
```

Keluaran yang dihasilkan terlihat seperti berikut:

1. Lorem ipsum dolor sit amet
1. Consectetur adipiscing elit
1. Integer molestie lorem at massa
1. Facilisis in pretium nisl aliquet
1. Nulla volutpat aliquam velit
1. Faucibus porta lacus fringilla vel
1. Aenean sit amet erat nunc
1. Eget porttitor lorem
{{< /admonition >}}

### Daftar Tugas

Daftar tugas memungkinkan Anda membuat daftar item dengan kotak centang. Untuk membuat daftar tugas, tambahkan dashes (`-`) dan brackets dengan spasi (`[ ]`) sebelum item daftar tugas. Untuk memilih kotak centang, tambahkan x diantara kurung (`[x]`).

```markdown
- [x] Tulis siaran pers
- [ ] Update website
- [ ] Hubungi media
```

The rendered output looks like this:

- [x] Tulis siaran pers
- [ ] Update website
- [ ] Hubungi media

## Kode

### kode Sebaris

Bungkus dalam cuplikan kode dengan `<code></code>`.

```markdown
In this example, `<section></section>` should be wrapped as **code**.
```

Keluaran yang dihasilkan terlihat seperti berikut:

In this example, `<section></section>` should be wrapped as **code**.

Di HTML terlihat seperti berikut:

```html
<p>
  In this example, <code>&lt;section&gt;&lt;/section&gt;</code> should be wrapped with <strong>code</strong>.
</p>
```

### Kode Teridentifikasi

Atau berbagai baris kode dengan setidaknya empat ruang, seperti dalam:

```markdown
    // Beberapa komentar
    baris 1 dari kode
    baris 2 dari kode
    baris 3 dari kode
```

Keluaran yang dihasilkan terlihat seperti berikut:
    // Beberapa komentar
    baris 1 dari kode
    baris 2 dari kode
    baris 3 dari kode

Di HTML terlihat seperti berikut:

```html
<pre>
  <code>
    // Beberapa komentar
    baris 1 dari kode
    baris 2 dari kode
    baris 3 dari kode
  </code>
</pre>
```

### Blok Kode Bertanda

Gunakan "tanda" <code>```</code> untuk memblokir dalam beberapa baris kode dengan atribut bahasa.

{{< highlight markdown >}}
```markdown
Contoh teks di sini...
```
{{< / highlight >}}

Di HTML terlihat seperti berikut:

```html
<pre language-html>
  <code>Contoh teks di sini...</code>
</pre>
```

### Penyorotan Sintaks

[GFM]^(GitHub Flavored Markdown) juga mendukung penyorotan sintaks.

Untuk mengaktifkannya, cukup tambahkan ekstensi file dari bahasa yang ingin Anda gunakan langsung setelah kode pertama "tanda", ```js, dan sinkped sintaks secara otomatis akan diterapkan dalam HTML yang diberikan.

Misalnya, untuk menerapkan sinkped sintaks ke kode JavaScript: 

{{< highlight markdown >}}
```js
grunt.initConfig({
  assemble: {
    options: {
      assets: 'docs/assets',
      data: 'src/data/*.{json,yml}',
      helpers: 'src/custom-helpers.js',
      partials: ['src/partials/**/*.{hbs,md}']
    },
    pages: {
      options: {
        layout: 'default.hbs'
      },
      files: {
        './': ['src/templates/pages/index.hbs']
      }
    }
  }
};
```
{{< / highlight >}}

Keluaran yang dihasilkan terlihat seperti berikut:

```js
grunt.initConfig({
  assemble: {
    options: {
      assets: 'docs/assets',
      data: 'src/data/*.{json,yml}',
      helpers: 'src/custom-helpers.js',
      partials: ['src/partials/**/*.{hbs,md}']
    },
    pages: {
      options: {
        layout: 'default.hbs'
      },
      files: {
        './': ['src/templates/pages/index.hbs']
      }
    }
  }
};
```

{{< admonition >}}
[Syntax highlighting page](https://gohugo.io/content-management/syntax-highlighting/)  di **Hugo** Docs memperkenalkan lebih banyak tentang sorotan sintaks, termasuk sorotan shortcode.
{{< /admonition >}}

## Tabel

Tabel dibuat dengan menambahkan pipa sebagai pembagi diantara setiap sel, dan dengan menambahkan garis-garis dashes (juga dipisahkan oleh batang) di bawah header. Perhatikan bahwa pipa tidak perlu disejajarkan secara vertikal.

```markdown
| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
```

Keluaran yang dihasilkan terlihat seperti berikut:

| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

Di HTML terlihat seperti berikut:

```html
<table>
  <thead>
    <tr>
      <th>Option</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>data</td>
      <td>path to data files to supply the data that will be passed into templates.</td>
    </tr>
    <tr>
      <td>engine</td>
      <td>engine to be used for processing templates. Handlebars is the default.</td>
    </tr>
    <tr>
      <td>ext</td>
      <td>extension to be used for dest files.</td>
    </tr>
  </tbody>
</table>
```

{{< admonition note "Right or center aligned text" >}}
Menambahkan colon (titik dua) di sisi kanan dasbor di bawah judul apa pun akan menyelaraskan teks untuk kolom itu.

Menambahkan colon (titik dua) di kedua sisi garis di bawah judul apa pun akan berpusat menyelaraskan teks untuk kolom itu.

```markdown
| Option | Description |
|:------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
```

Keluaran yang dihasilkan terlihat seperti berikut:
| Option | Description |
|:------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
{{< /admonition >}}

## Tautan 

### Tautan Dasar

```markdown
<https://assemble.io>
<contact@revolunet.com>
[Assemble](https://assemble.io)
```

Output yang diberikan terlihat seperti ini (hover di atas tautan, tidak ada tooltip):

<https://assemble.io>

<contact@revolunet.com>

[Assemble](https://assemble.io)

Di HTML terlihat seperti berikut:

```html
<a href="https://assemble.io">https://assemble.io</a>
<a href="mailto:contact@revolunet.com">contact@revolunet.com</a>
<a href="https://assemble.io">Assemble</a>
```

### Menambahkan Judul

```markdown
[Upstage](https://github.com/upstage/ "Visit Upstage!")
```

Output yang diberikan terlihat seperti ini (hover di atas tautan, tidak ada tooltip):

[Upstage](https://github.com/upstage/ "Visit Upstage!")

Di HTML terlihat seperti berikut:

```html
<a href="https://github.com/upstage/" title="Visit Upstage!">Upstage</a>
```

### Named Anchors

Named anchors memungkinkan Anda untuk melompat ke titik anchor yang ditentukan pada halaman yang sama. Sebagai contoh, masing-masing bab ini:

```markdown
## Daftar Isi
  * [Bab 1](#bab-1)
  * [Bab 2](#bab-2)
  * [Bab 3](#bab-3)
```

akan melompat ke bagian-bagian ini:

```markdown
## Bab 1 <a id="bab-1"></a>
Isi dari bab 1.

## Bab 2 <a id="bab-2"></a>
Isi dari bab 2

## Bab 3 <a id="bab-3"></a>
Isi dari bab 3.
```

{{< admonition >}}
Penempatan spesifik dari tag anchor tampaknya tidak teratur. Mereka ditempatkan sebaris karena tampaknya tidak mengganggu, dan itu berhasil.
{{< /admonition >}}

## Catatan Kaki

Catatan kaki memungkinkan Anda untuk menambahkan catatan dan referensi tanpa mengacaukan tubuh dokumen. Saat Anda membuat catatan kaki, nomor superskrip dengan tautan muncul di mana Anda menambahkan referensi catatan kaki. Pembaca dapat mengklik tautan untuk melompat ke konten catatan kaki di bagian bawah halaman.

Untuk membuat referensi catatan kaki, tambahkan caret dan pengenal di dalam kurung ([^1]). Pengidentifikasi bisa berupa angka atau kata-kata, tetapi mereka tidak dapat berisi spasi atau tab. Pengidentifikasi hanya menghubungkan referensi catatan kaki dengan catatan kaki itu sendiri - dalam output, catatan kaki diberi nomor secara berurutan.

Tambahkan catatan kaki menggunakan caret lain dan nomor di dalam kurung dengan kolon dan teks ([^1]: My footnote.). Anda tidak perlu menempatkan catatan kaki di akhir dokumen. Anda dapat menempatkan mereka di mana saja kecuali di dalam elemen lain seperti daftar, tandan, dan tabel blok.

```markdown
Ini adalah catatan kaki digital [^1]
Ini adalah catatan kaki dengan “label” [^label]

[^1]: Ini adalah catatan kaki digital
[^label]: Ini adalah catatan kaki dengan “label”
```

Ini adalah catatan kaki digital [^1]
Ini adalah catatan kaki dengan “label” [^label]

[^1]: Ini adalah catatan kaki digital
[^label]: Ini adalah catatan kaki dengan “label”

## Gambar

Gambar memiliki sintaks yang sama dengan tautan tetapi termasuk titik seru sebelumnya.

```markdown
![Minion](https://octodex.github.com/images/minion.png)
```

![Minion](https://octodex.github.com/images/minion.png)

atau:

```markdown
![Alt text](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")
```

![Alt text](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

Seperti link, gambar juga memiliki sintaks gaya catatan kaki:

```markdown
![Alt text][id]
```

![Alt text][id]

Dengan referensi kemudian dalam dokumen yang menentukan lokasi URL:

```markdown
[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"
```

[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"

Demikian artikel tentang sintaks Markdown dasar. Semoga bermanfaat. 😙
