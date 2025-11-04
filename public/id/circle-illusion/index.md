# Ilusi Lingkaran: Fenomena Persepsi Ukuran di Sekitar Lingkaran Tengah


{{< admonition >}}

Artikel ini membahas ilusi lingkaran, di mana dua lingkaran pusat yang identik tampak berbeda ukuran karena konteks visual di sekitarnya. Dibuat menggunakan LaTeX TikZ, artikel ini memberikan penjelasan lengkap mengenai struktur kode dan konsep persepsi dibaliknya.

{{< /admonition >}}

## Pendahuluan

Dalam ranah persepsi visual, otak manusia sering kali memproses ukuran **secara relatif**, bukan **secara absolut**.  
Salah satu contoh paling terkenal dari fenomena ini adalah **Ilusi Ebbinghaus**, atau **Ilusi Lingkaran**, di mana dua lingkaran identik tampak memiliki ukuran berbeda karena bentuk-bentuk di sekelilingnya.

Artikel ini menampilkan fenomena tersebut menggunakan **LaTeX TikZ**, disertai penjelasan mendetail dari setiap bagian kode dan konsep ilmiah dibaliknya.

---

## Kode Sumber LaTeX

Berikut adalah kode LaTeX lengkap untuk menghasilkan dua lingkaran tengah berwarna oranye yang tampak berbeda ukurannya akibat perbedaan ukuran dan jarak lingkaran biru di sekelilingnya.

```latex
\documentclass{standalone}

\usepackage{tikz}

\begin{document}
\begin{tikzpicture}[baseline=(X.base)]
    \node[circle,fill=orange,draw=orange,minimum size=2cm] (X) at (0,0) {};
    \foreach \i in {0,60,...,330}{
        \filldraw[blue!50!white]  (\i:3.4) circle (1.6);}
\end{tikzpicture}
\hspace{1cm}
\begin{tikzpicture}[baseline=(X.base)]
    \node[circle,fill=orange,draw=orange,minimum size=2cm] (X) at (0,0) {};
    \foreach \i in {0,45,...,360}{
        \filldraw[blue!50!white]  (\i:1.5)  circle (.4);}
\end{tikzpicture}
\end{document}
```
---
Keluaran yang dihasilkan:

![ilusi](lingkaran.png " Lingkaran oranye sama besar atau beda? ")


## Penjelasan Struktur Kode

### **Deklarasi Dokumen**
```latex
\documentclass{standalone}
```
Kelas dokumen `standalone` memastikan hanya gambar yang dirender — tanpa margin halaman, header, atau teks lainnya.  
Sangat ideal untuk menghasilkan ilustrasi atau grafik matematis yang berdiri sendiri.

---

### **Mengimpor Paket TikZ**
```latex
\usepackage{tikz}
```
Paket TikZ memungkinkan pembuatan gambar matematis dan geometris langsung di dalam LaTeX dengan hasil berbasis vektor yang presisi.

---

### **Awal Dokumen**
```latex
\begin{document}
```
Menandai awal dari isi dokumen di mana semua perintah dan gambar ditempatkan.

---

### **Gambar Pertama — Ilusi Lingkaran Kiri**
```latex
\begin{tikzpicture}[baseline=(X.base)]
```
Mendefinisikan area gambar TikZ.  
Opsi `baseline=(X.base)` menjaga agar kedua gambar sejajar secara vertikal saat ditampilkan berdampingan.

---

#### **Lingkaran Tengah**
```latex
\node[circle,fill=orange,draw=orange,minimum size=2cm] (X) at (0,0) {};
```
- Membuat **lingkaran oranye berdiameter 2 cm** di titik pusat (0,0).  
- `(X)` berfungsi sebagai label referensi.  
- Ini adalah **lingkaran utama** dalam ilusi.

---

#### **Lingkaran Besar di Sekelilingnya**
```latex
\foreach \i in {0,60,...,330}{
    \filldraw[blue!50!white] (\i:3.4) circle (1.6);}
```
- Menggambar **enam lingkaran biru besar** yang berjarak 60° satu sama lain.  
- Masing-masing berjarak 3.4 cm dari pusat dan memiliki radius 1.6 cm.  
- Warna biru dicampur dengan putih 50% untuk kesan lembut.  
**Hasil:** Lingkaran oranye tampak **lebih kecil** karena dikelilingi lingkaran besar.

---

### **Jarak Horizontal Antar Gambar**
```latex
\hspace{1cm}
```
Menambahkan jarak horizontal 1 cm antara dua gambar agar tidak saling menimpa.

---

### **Gambar Kedua — Ilusi Lingkaran Kanan**
```latex
\begin{tikzpicture}[baseline=(X.base)]
```
Memulai area gambar TikZ kedua untuk ilustrasi di sisi kanan.

---

#### **Lingkaran Tengah**
```latex
\node[circle,fill=orange,draw=orange,minimum size=2cm] (X) at (0,0) {};
```
Sama seperti lingkaran tengah pertama. Namun, secara visual akan tampak **lebih besar** karena konteks di sekitarnya berbeda.

---

#### **Lingkaran Kecil di Sekelilingnya**
```latex
\foreach \i in {0,45,...,360}{
    \filldraw[blue!50!white]  (\i:1.5)  circle (.4);}
```
- Menggambar **delapan lingkaran biru kecil** dengan jarak sudut 45°.  
- Masing-masing berjarak 1.5 cm dari pusat dengan radius hanya 0.4 cm.  
**Hasil:** Lingkaran oranye tampak **lebih besar**.

---

### **Akhir Dokumen**
```latex
\end{document}
```
Menandai akhir dokumen LaTeX. Hasil akhirnya berupa dua gambar berdampingan yang membentuk **Ilusi Ebbinghaus**.

---

## Analisis Visual

| Gambar | Ukuran Lingkaran Sekitar | Jarak dari Pusat | Efek Persepsi |
|:--------|:--------------------------|:-----------------|:---------------|
| Kiri    | Besar (radius 1.6 cm)    | 3.4 cm           | Lingkaran pusat tampak lebih kecil |
| Kanan   | Kecil (radius 0.4 cm)    | 1.5 cm           | Lingkaran pusat tampak lebih besar |

Meskipun kedua lingkaran oranye berukuran sama, otak manusia **menafsirkan ukuran secara kontekstual**, bukan berdasarkan ukuran sebenarnya.

---

## Cara Ilusi Ini Bekerja

1. **Perbandingan Kontekstual** — Otak menilai ukuran relatif terhadap objek lain di sekitarnya.  
2. **Normalisasi Visual** — Sistem persepsi menyederhanakan perbedaan ukuran untuk efisiensi pengolahan spasial.  
3. **Petunjuk Lingkungan** — Objek besar di sekitar membuat pusat tampak kecil, sebaliknya objek kecil membuatnya tampak besar.

---

## Eksperimen Lanjutan

Coba ubah parameter berikut dalam kode TikZ untuk melihat variasi efek:

| Parameter | Fungsi | Efek Visual |
|------------|----------|-------------|
| `3.4` / `1.5` | Jarak dari pusat | Mengubah jarak antara lingkaran |
| `1.6` / `0.4` | Ukuran lingkaran sekitar | Memperkuat atau melemahkan ilusi |
| Warna | Ubah `blue!50!white` | Mengubah kontras dan kedalaman warna |
| Jumlah lingkaran | Ubah langkah 60° / 45° | Mengubah kepadatan dan simetri |

Contoh variasi:
```latex
\foreach \i in {0,30,...,330}{
    \filldraw[green!40!white] (\i:2.5) circle (.8);}
```

---

## Relevansi Ilmiah dan Artistik

Ilusi lingkaran menjembatani **psikologi, geometri, dan seni**.  
Fenomena ini memiliki nilai penting dalam:
- **Psikologi kognitif** — memahami persepsi ukuran dan konteks visual.  
- **Desain & UI/UX** — memanfaatkan ruang dan kontras untuk menonjolkan elemen.  
- **Seni matematis** — memvisualisasikan hubungan antara simetri dan ilusi.

---

## Kesimpulan

Ilusi Ebbinghaus menunjukkan bahwa persepsi ukuran manusia **bergantung pada konteks**, bukan pada ukuran sebenarnya.  
Dengan **LaTeX TikZ**, kita dapat merekonstruksi fenomena visual ini secara matematis, menggabungkan **sains dan estetika** dalam satu representasi elegan.

---

## Referensi

1. Ebbinghaus, H. (1897). *Über eine neue Methode zur Prüfung geistiger Fähigkeiten und ihre Anwendung bei Schulkindern.*  
2. Coren, S., & Girgus, J. S. (1978). *Seeing is Deceiving: The Psychology of Visual Illusions.* Lawrence Erlbaum.  
3. Gregory, R. L. (1997). *Eye and Brain: The Psychology of Seeing.* Oxford University Press.  
4. PGF/TikZ Manual, Versi 3.1.10 (2023).

---

**Ditulis oleh:** [Aan Triono](https://www.aantriono.com)  
**Lisensi:** CC BY-SA 4.0

