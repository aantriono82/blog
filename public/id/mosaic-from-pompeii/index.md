# Membuat Pola Mosaik Pompeii dengan LaTeX TikZ


Artikel ini membahas analisis komprehensif terhadap kode LaTeX TikZ karya Daniel Steger untuk menghasilkan pola mosaik Pompeii — mencakup struktur kode, filosofi visual, serta relevansi ilmiah dan artistik.

<!--more-->

---

## Pendahuluan

Karya ini berasal dari *Daniel Steger*, yang menafsirkan ulang pola mosaik kuno dari **Casa degli Amorini Dorati** di Pompeii. Dengan menggunakan **LaTeX TikZ**, ia merekonstruksi bentuk-bentuk geometris kompleks melalui prinsip **interseksi lingkaran dan simetri rotasional**.

Tujuan artikel ini adalah untuk membedah kode tersebut secara menyeluruh: mulai dari struktur teknis, prinsip matematis, interpretasi visual-filosofis, hingga relevansi ilmiah dan artistik di era modern.

---

## Kode Sumber LaTeX

Berikut adalah kode lengkap untuk menghasilkan pola mosaik Pompeii menggunakan TikZ:

```latex
% Author: Daniel Steger
% Source: Mosaic from Pompeji
% Casa degli Armorini Dorati, Living room, mosaic
\documentclass{minimal}
\usepackage{tikz}

\begin{document}

\begin{tikzpicture}[cap=round]
% Colors
\colorlet{anglecolor}{green!50!black}
\colorlet{bordercolor}{black}

%Configuration
\def\alpha{5} % degree
\def\layer{5}

\begin{scope}[scale=5]
\pgfmathsetmacro\sinTriDiff{sin(60-\alpha)}
\pgfmathsetmacro\cosTriDiff{1-cos(60-\alpha)}
\pgfmathsetmacro\radiusC{sqrt(\cosTriDiff*\cosTriDiff + \sinTriDiff*\sinTriDiff)}
\pgfmathsetmacro\startAng{\alpha + atan(\sinTriDiff/\cosTriDiff)}
\pgfmathsetmacro\al{\alpha*\layer}

\foreach \x in {0,\alpha,...,\al}
{
  \pgfmathsetmacro\ang{\x + \startAng}
  \pgfmathsetmacro\xRs{\radiusC*cos(\ang)}
  \pgfmathsetmacro\yRs{\radiusC*sin(\ang)}
  \pgfmathsetmacro\radiusLayer{\xRs + sqrt( 1 - \yRs*\yRs )}
  \pgfmathsetmacro\angRs{acos(\yRs)}
  \pgfmathsetmacro\angRss{acos(\radiusC*sin(\ang-\alpha))}
  \colorlet{anglecolor}{black!\ang!green}
  \pgfmathsetmacro\step{2*\alpha - 180}
  \pgfmathsetmacro\stop{180-2*\alpha}

  \foreach \y in {-180, \step ,..., \stop}
  {
    \pgfmathsetmacro\deltaAng{\y-\x}
    \filldraw[color=anglecolor,draw=bordercolor] 
        (\y-\x:\radiusLayer)    
                arc (-90+\angRs+\deltaAng : \alpha-90+\angRss+\deltaAng :1) 
                arc (\alpha+90-\angRss+\deltaAng : 2*\alpha+90-\angRs+\deltaAng :1)
                arc (\deltaAng+2*\alpha : \deltaAng : \radiusLayer);
  }
}

\pgfmathsetmacro\xRs{\radiusC*cos(\al+\startAng)}
\pgfmathsetmacro\yRs{\radiusC*sin(\al+\startAng)}
\pgfmathsetmacro\radiusLayer{\xRs + sqrt( 1 - \yRs*\yRs )}
\draw[line width=2, color=bordercolor] (0,0) circle (.8*\radiusLayer);
\pgfmathsetmacro\radiusSmall{.7*\radiusLayer}

\foreach \x in {-60,0,...,240}
{
    \fill[color=anglecolor] (\x:\radiusSmall) arc (-180+\x+60: -180+\x: \radiusSmall)
                             arc (0+\x: -60+\x: \radiusSmall)
                             arc (120+\x: 60+\x: \radiusSmall); 
}

\foreach \x in {0, 4, ..., 360}
{
  \fill[color=anglecolor] (\x:1) -- (\x+3:1.05) -- (\x+5:1.05) -- (\x+2:1) -- cycle;
  \fill[color=anglecolor] (\x+5:1.05) -- (\x+7:1.05) -- (\x+4:1.1) -- (\x+2:1.1) -- cycle;
}
\draw[line width=1, color=bordercolor] (0,0) circle (1);
\draw[line width=1, color=bordercolor] (0,0) circle (1.1);
\end{scope}

\end{tikzpicture}
\end{document}
```
---

Keluaran yang dihasilkan:

![mandala](mandala.png  "Mosaik Pompeii")

---

## Penjelasan Struktur Kode

### Inisialisasi dan Paket
```latex
\documentclass{minimal}
\usepackage{tikz}
```
Kode menggunakan kelas `minimal` untuk keperluan grafik murni dan paket `tikz` untuk menggambar bentuk vektor.

### Pengaturan Warna dan Parameter
```latex
\colorlet{anglecolor}{green!50!black}
\colorlet{bordercolor}{black}
\def\alpha{5}
\def\layer{5}
```
- `anglecolor`: warna gradasi hijau gelap digunakan untuk efek rotasional.
- `bordercolor`: batas tiap bentuk dalam warna hitam.
- `\alpha`: interval sudut antar elemen (5°).
- `\layer`: jumlah lapisan utama (5).

### Perhitungan Geometri Dasar
Bagian ini memanfaatkan trigonometri untuk menentukan posisi dan jari-jari lingkaran hasil interseksi.
```latex
\pgfmathsetmacro\sinTriDiff{sin(60-\alpha)}
\pgfmathsetmacro\cosTriDiff{1-cos(60-\alpha)}
\pgfmathsetmacro\radiusC{sqrt(\cosTriDiff^2 + \sinTriDiff^2)}
```
Nilai-nilai ini menjadi fondasi posisi titik potong antar lingkaran yang membentuk pola hexagonal atau bunga.

### Pembuatan Segmen dan Pola Utama
Blok utama loop `\foreach` mengulang rotasi setiap `\alpha` derajat.
```latex
\foreach \x in {0,\alpha,...,\al}
```
Dalam setiap iterasi:
- Koordinat titik pusat dihitung.
- Sudut interseksi (`\angRs`, `\angRss`) diperoleh dengan `acos`.
- Pola arc dibuat melalui tiga `arc` bertautan, membentuk bentuk seperti daun atau sisik.

### Elemen Dekoratif Tengah dan Luar
Bagian ini menambahkan lingkaran tengah dan ornamen kelopak kecil di sekeliling.
```latex
\foreach \x in {-60,0,...,240}
```
Membentuk enam elemen simetris, melambangkan harmoni hexagonal khas mosaik Romawi.

Sedangkan lingkaran luar:
```latex
\foreach \x in {0, 4, ..., 360}
```
Menghasilkan pola seperti *gigi roda*, simbol keteraturan dan kesinambungan.

---

## Analisis Visual dan Filosofis

Secara visual, pola ini membentuk **keteraturan yang lahir dari pengulangan dan perpotongan lingkaran**. Dalam konteks estetika klasik Pompeii:
- Lingkaran merepresentasikan **kesempurnaan dan keabadian**.
- Interseksi melambangkan **keterhubungan antara unsur duniawi dan ilahi**.
- Gradasi warna hijau-hitam menghadirkan **kontras antara kehidupan dan struktur**, memberi kedalaman spasial.

Filosofinya mendekati konsep **mandala**, namun dengan sentuhan geometri Barat kuno — bukan spiritualitas Timur, melainkan *rasionalitas estetis*.

---

## Eksperimen Variasi TikZ

Anda dapat mengeksplorasi parameter berikut untuk menciptakan variasi:

| Parameter | Efek Visual | Contoh |
|------------|-------------|--------|
| `\alpha` | Mengatur kerapatan pola | `\def\alpha{10}` → bentuk lebih jarang |
| `\layer` | Jumlah lapisan rotasi | `\def\layer{8}` → pola lebih dalam |
| `anglecolor` | Skema warna | Ganti dengan `blue!50!black` |
| `scale` | Ukuran keseluruhan pola | `scale=3` → pola lebih padat |

Eksperimen ini menunjukkan fleksibilitas **TikZ sebagai medium artistik** berbasis kode.

---

## Relevansi Ilmiah dan Artistik

Dari perspektif ilmiah:
- Kode ini mendemonstrasikan **transformasi rotasi**, **interseksi lingkaran**, dan **simetri polar**.
- Dapat diterapkan dalam **geometri komputasional**, **grafik vektor**, dan **pendidikan matematika visual**.

Secara artistik:
- Ia menghidupkan kembali estetika **arsitektur Romawi** dalam medium digital.
- Menjadi contoh nyata bagaimana **kode dapat menjadi kanvas seni**.

---

## Kesimpulan

Melalui eksplorasi karya Daniel Steger, kita belajar bahwa:
> "Kode dapat menjadi bentuk seni yang setara dengan kuas dan kanvas — hanya saja ia menggambar dengan logika dan simetri."

Dengan LaTeX TikZ, hubungan antara **sains, seni, dan geometri** bersatu dalam harmoni yang menggemakan kejayaan Pompeii.

---

## Referensi

1. Daniel Steger, *TikZ example: Mosaic from Pompeji*, [TeXample.net](https://texample.net/tikz/examples/mosaic-from-pompeji/)
2. Till Tantau, *The TikZ and PGF Manual*, v3.1.10, 2024.
3. Plato, *Timaeus*: tentang geometri dan keteraturan kosmos.
4. Gombrich, E. H. *The Sense of Order: A Study in the Psychology of Decorative Art*. Oxford University Press, 1979.

---

**Ditulis oleh:** [Aan Triono](https://www.aantriono.com)  
**Lisensi:** CC BY-SA 4.0
