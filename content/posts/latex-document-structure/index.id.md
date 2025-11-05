---
weight: 4
title: "Struktur Dokumen LaTeX"
date: 2025-10-14
# lastmod: 2025-10-14
draft: false
author: "Aan Triono"
authorLink: "https://www.aantriono.com"
description: "Artikel ini membahas tentang struktur dokumen LaTeX baik pada kelas dokumen surat, artikel, laporan, dan buku"
images: []
featuredImage: "featured-image.png"

tags: ["Struktur"]
categories: ["LaTeX"]

lightgallery: true
twemoji: true
---
Artikel ini membahas tentang struktur dokumen LaTeX baik pada kelas dokumen surat, artikel, laporan, dan buku.

<!--more-->

---

## Pendahuluan

**LaTeX** adalah sistem typesetting berbasis markup yang banyak digunakan untuk penulisan karya ilmiah, laporan, buku, hingga skripsi.  
Salah satu platform populer untuk menulis dan menyusun dokumen LaTeX adalah **Overleaf**, editor daring yang memungkinkan kolaborasi real-time serta menyediakan dokumentasi dan template lengkap.

Sebelum memulai penulisan dokumen, penting memahami struktur dasar dokumen LaTeX.  
Sebuah file `.tex` umumnya terdiri dari tiga bagian besar:

1. **Preamble** – pengaturan awal dokumen sebelum `\begin{document}`
2. **Body** – isi utama dokumen di antara `\begin{document}` dan `\end{document}`
3. **Bagian tambahan** – seperti lampiran, bibliografi, atau indeks

---

## Struktur Umum Dokumen LaTeX

Struktur minimal dokumen LaTeX adalah sebagai berikut:

```latex
\documentclass{article}
\usepackage[utf8]{inputenc}

\title{Judul Dokumen}
\author{Nama Penulis}
\date{\today}

\begin{document}

\maketitle
\section{Pendahuluan}
Teks pendahuluan Anda di sini.

\end{document}
```

Overleaf menjelaskan bahwa setiap dokumen LaTeX **harus dimulai** dengan deklarasi `\documentclass{}` dan diakhiri dengan `\end{document}`.  

---

## Preamble

Preamble berisi semua pengaturan awal sebelum dokumen dimulai. Biasanya meliputi:

### Kelas Dokumen

```latex
\documentclass[12pt, a4paper]{article}
```

Kelas dokumen menentukan jenis dan gaya umum dokumen.  
Beberapa kelas standar:

| Kelas | Deskripsi |
|-------|------------|
| `article` | Untuk artikel, laporan pendek, atau paper |
| `report` | Untuk laporan panjang, tugas akhir, atau disertasi |
| `book` | Untuk buku dengan bab (chapter) |
| `letter` | Untuk surat resmi |

---

### Paket (Packages)

Paket memperluas kemampuan LaTeX.  
Contoh umum:

```latex
\usepackage[utf8]{inputenc}   % Mengatur encoding teks
\usepackage[T1]{fontenc}      % Mengatur encoding font
\usepackage{graphicx}         % Menyisipkan gambar
\usepackage{amsmath, amssymb} % Simbol dan rumus matematika
```

---

### Metadata Dokumen

Metadata berisi informasi seperti judul, penulis, dan tanggal.

```latex
\title{Contoh Dokumen LaTeX}
\author{Nama Penulis}
\date{\today} % atau bisa dikosongkan dengan {}
```

Metadata ini digunakan ketika perintah `\maketitle` dipanggil dalam body dokumen.

---

## Body Dokumen

Bagian ini berisi konten utama antara `\begin{document}` dan `\end{document}`.

Contoh struktur dasar:

```latex
\begin{document}

\maketitle

\section{Pendahuluan}
Bagian pembuka atau pengantar topik.

\section{Metodologi}
Menjelaskan cara atau langkah penelitian.

\subsection{Langkah-langkah}
Penjabaran lebih detail dari metode.

\section{Kesimpulan}
Kesimpulan akhir dari pembahasan.

\end{document}
```

### Penomoran Bagian

LaTeX secara otomatis menomori bagian (`\section`, `\subsection`, dll).  
Untuk bagian tanpa nomor, gunakan tanda bintang:

```latex
\section*{Ucapan Terima Kasih}
```

---

### Menambahkan Gambar

Gunakan paket `graphicx`:

```latex
\usepackage{graphicx}

\begin{figure}[h]
\centering
\includegraphics[width=0.5\textwidth]{gambar.png}
\caption{Contoh Gambar}
\label{fig:contoh}
\end{figure}
```

---

### Menulis Rumus dan Persamaan

Gunakan paket `amsmath`:

```latex
\begin{equation}
E = mc^2
\end{equation}
```

---

## Bagian Tambahan (Optional)

Untuk dokumen akademik atau buku, LaTeX menyediakan pembagian tambahan seperti:

### Frontmatter, Mainmatter, dan Backmatter

```latex
\frontmatter    % Untuk bagian awal (abstrak, daftar isi)
\tableofcontents

\mainmatter     % Isi utama (bab, subbab)
\chapter{Pendahuluan}

\backmatter     % Bagian akhir (daftar pustaka, lampiran)
\appendix
\chapter{Lampiran}
```

---

### Bibliografi

Gunakan `biblatex` untuk daftar pustaka otomatis:

```latex
\usepackage{biblatex}
\addbibresource{daftar-pustaka.bib}

...

\printbibliography
```
---

## Contoh Dokumen Minimal

Berikut contoh dokumen **paling sederhana** yang valid:

```latex
\documentclass{article}
\usepackage[utf8]{inputenc}

\title{Hello World in LaTeX}
\author{Penulis}
\date{}

\begin{document}

\maketitle

\section{Pendahuluan}
Ini adalah contoh dokumen minimal di LaTeX.

\end{document}
```

---

## Tips dan Best Practice

- Gunakan **struktur folder** terpisah (`/images`, `/chapters`, `/bib`) agar dokumen besar mudah dikelola.  
- Pisahkan tiap bab ke dalam file `.tex` dan panggil dengan `\input{}` atau `\include{}`.  
- Gunakan **Overleaf Outline Panel** untuk melihat struktur dokumen dengan cepat.  
- Hindari memuat paket berlebihan yang tidak diperlukan untuk menjaga performa kompilasi.

---

## Kesimpulan

Struktur dasar dokumen LaTeX sangat teratur dan modular.  
Dengan memahami pembagian antara **preamble**, **body**, dan **bagian tambahan**, penulis dapat mengelola dokumen teknis dengan lebih efisien.  

Overleaf menyediakan panduan lengkap, contoh praktis, serta template yang memudahkan pengguna baru untuk belajar dan menulis dokumen profesional.

---

### 📚 Referensi

1. [Learn LaTeX in 30 Minutes – Overleaf](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes)  
2. [Sections and Chapters – Overleaf](https://www.overleaf.com/learn/latex/Sections_and_chapters)  
3. [How to Write a Thesis in LaTeX (Part 1): Basic Structure – Overleaf](https://www.overleaf.com/learn/latex/How_to_Write_a_Thesis_in_LaTeX_%28Part_1%29%3A_Basic_Structure)  
4. [Inserting Images – Overleaf](https://www.overleaf.com/learn/latex/Inserting_Images)  
5. [Bibliography Management with BibLaTeX – Overleaf](https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex)  
6. [Using the File Outline in Overleaf](https://www.overleaf.com/learn/how-to/Using_the_File_Outline_in_Overleaf)

---
