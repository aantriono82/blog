---
weight: 1
title: Ilusi Lingkaran: Simetri, Geometri, dan Distorsi Visual"
date: 2025-11-05
# lastmod: 2025-11-14
draft: false
author: "Aan Triono"
authorLink: "https://www.aantriono.com"
description: "Artikel ini membahas ilusi lingkaran geometris yang dibuat dengan LaTeX TikZ, di mana lingkaran konsentris dan persegi berotasi saling berinteraksi menghasilkan distorsi visual meskipun secara matematis simetris sempurna."
images: []
featuredImage: "featured-image.png"

tags: ["Ilusi Optik"]
categories: ["LaTeX"]

lightgallery: true
---

Artikel ini membahas ilusi lingkaran geometris yang dibuat dengan LaTeX TikZ, di mana lingkaran konsentris dan persegi berotasi saling berinteraksi menghasilkan distorsi visual meskipun secara matematis simetris sempurna.

<!--more-->

---

{{< admonition >}}
**Catatan**: Artikel ini dihasilkan dengan bantuan teknologi AI dan telah direview secara manual untuk memastikan keakuratan dan kejelasan informasi.
{{< /admonition >}}

## Pendahuluan

Dalam ranah persepsi visual, **geometri sederhana** dapat menghasilkan **ilusi yang kompleks**.  
Salah satu contohnya adalah **ilusi lingkaran konsentris**, di mana pola lingkaran berulang tampak terdistorsi ketika dikombinasikan dengan **elemen persegi yang berotasi**.

Artikel ini menjelaskan bagaimana pola tersebut dibuat menggunakan **LaTeX TikZ**, serta bagaimana **sistem visual manusia** menafsirkan bentuk-bentuk ini sehingga menimbulkan kesan lengkungan atau ketidakseimbangan yang salah.

---

## Kode Sumber LaTeX

```latex
\documentclass[border=10pt,tikz]{standalone}
\pagecolor{gray!5}
\begin{document}
    \begin{tikzpicture}[x=4cm,y=4cm,every rectangle node/.style={draw,thick,red,rotate=45,minimum width=0.707*4cm,minimum height=0.707*4cm}]
        \foreach \y in {1,...,3}
            \foreach \x in {1,...,3}{%
                \foreach \diameter in {1,...,6}
                    \draw[gray,thick] (\x,\y) circle (1/12*\diameter);
                \node[rectangle] at (\x,\y) {};
            }
    \end{tikzpicture}
\end{document}
```
Keluaran yang dihasilkan:

![ilusi](ilusi.png "distorsi visual")

---

## Penjelasan Struktur Kode

### **Deklarasi Dokumen**
```latex
\documentclass[border=10pt,tikz]{standalone}
```
Kelas `standalone` digunakan untuk menghasilkan gambar tunggal tanpa margin halaman.  
Parameter `border=10pt` menambah jarak tepi kecil, dan `tikz` mengaktifkan pustaka TikZ untuk menggambar vektor.

---

### **Warna Latar Belakang**
```latex
\pagecolor{gray!5}
```
Mengatur warna latar belakang abu-abu muda agar kontras dan nyaman dilihat.

---

### **Lingkungan TikZ**
```latex
\begin{tikzpicture}[x=4cm,y=4cm,...]
```
Mendefinisikan area gambar. Skala `x` dan `y` sebesar 4 cm memastikan proporsi yang konsisten di setiap grid.

---

### **Gaya Node Persegi**
```latex
every rectangle node/.style={draw,thick,red,rotate=45,minimum width=0.707*4cm,minimum height=0.707*4cm}
```
Menentukan tampilan persegi:
- `draw,thick,red`: menggambar persegi merah dengan garis tebal.  
- `rotate=45`: memutar setiap persegi 45°, membentuk pola seperti belah ketupat.  
- Ukuran `0.707*4cm` digunakan agar skala tetap proporsional setelah rotasi (berdasarkan nilai √2/2 × 4 cm).

---

### **Grid Lingkaran**
```latex
\foreach \y in {1,...,3}
    \foreach \x in {1,...,3}{ ... }
```
Membuat grid 3×3 yang menjadi pusat bagi kumpulan lingkaran konsentris.

---

### **Lingkaran Konsentris**
```latex
\foreach \diameter in {1,...,6}
    \draw[gray,thick] (\x,\y) circle (1/12*\diameter);
```
Menggambar enam lingkaran konsentris pada setiap titik grid, menciptakan efek kedalaman bertingkat.

---

### **Node Persegi**
```latex
\node[rectangle] at (\x,\y) {};
```
Menempatkan persegi merah berotasi di tengah setiap kumpulan lingkaran.  
Konflik antara arah radial (lingkaran) dan diagonal (persegi) inilah yang menimbulkan **ilusi visual**.

---

## Analisis Visual

Ilusi muncul dari **interaksi antara simetri lingkaran dan orientasi diagonal**.  
Mata manusia menangkap arah yang saling bersaing antara bentuk melingkar dan persegi, menghasilkan efek distorsi semu.

| Faktor Visual | Efek Persepsi |
|----------------|----------------|
| Persegi diagonal | Menciptakan ketegangan visual dan kesan miring |
| Lingkaran konsentris | Memusatkan perhatian ke arah radial |
| Warna netral | Menjaga keseimbangan antar elemen |

Meskipun semua elemen **matematis simetris**, otak menafsirkan pola ini seolah-olah tidak sejajar.

---

## Variasi Eksperimen

| Parameter | Fungsi | Dampak Visual |
|------------|---------|---------------|
| Jumlah lingkaran (`1,...,6`) | Mengatur jumlah lapisan | Lebih banyak lingkaran meningkatkan efek kedalaman |
| Warna persegi | Misalnya `biru` atau `oranye` | Mengubah fokus perhatian |
| Sudut rotasi | Ganti ke 30° atau 60° | Mengubah arah distorsi |
| Jarak antar lingkaran | Ubah `1/12` menjadi `1/10` | Mengubah kerapatan dan tumpang tindih |

Contoh variasi:
```latex
\node[rectangle,draw=blue,rotate=30] at (\x,\y) {};
```

---

## Relevansi Ilmiah dan Artistik

Pola ini menunjukkan bagaimana **geometri memengaruhi persepsi visual**:
- **Psikologi kognitif:** menggambarkan konflik orientasi dan penafsiran visual.  
- **Seni geometris:** mengubah simetri matematika menjadi karya estetis.  
- **Visualisasi data:** membantu memahami persepsi keselarasan bentuk.  
- **Desain:** diterapkan pada arsitektur dan seni optik untuk menciptakan komposisi dinamis.

---

## Kesimpulan

Ilusi lingkaran menunjukkan bahwa **simetri sempurna tidak selalu menghasilkan persepsi yang stabil**.  
Kombinasi antara **geometri konsentris dan rotasi diagonal** membuat otak kita membentuk lengkungan yang sebenarnya tidak ada.  
Dengan **LaTeX TikZ**, ilusi semacam ini dapat dibuat secara presisi, menjadikan matematika dan seni berpadu indah dalam satu representasi visual.

---

## Referensi

1. Gregory, R. L. (1997). *Eye and Brain: The Psychology of Seeing.* Oxford University Press.  
2. Coren, S., & Girgus, J. S. (1978). *Seeing is Deceiving: The Psychology of Visual Illusions.* Lawrence Erlbaum.  
3. Ware, C. (2013). *Information Visualization: Perception for Design.* Morgan Kaufmann.  
4. PGF/TikZ Manual, Versi 3.1.10 (2023).

---

**Ditulis oleh:** [Aan Triono](https://www.aantriono.com)  
**Lisensi:** CC BY-SA 4.0
