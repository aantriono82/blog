# Ilusi Titik Putih: Persepsi Kontras dalam Pola Kisi Gelap

Artikel ini membahas ilusi visual berupa titik putih pada kisi hitam, di mana otak memunculkan persepsi kontras yang tidak nyata. Dibuat menggunakan LaTeX PSTricks, artikel ini menjelaskan struktur kode dan konsep persepsi yang mendasarinya

<!--more-->

{{< admonition >}}
**Catatan**: Artikel ini dihasilkan dengan bantuan teknologi AI dan telah direview secara manual untuk memastikan keakuratan dan kejelasan informasi.
{{< /admonition >}}

## Pendahuluan

Ilusi optik adalah bukti bahwa apa yang kita lihat tidak selalu mencerminkan kenyataan fisik. Dalam banyak kasus, otak melakukan **interpretasi terhadap sinyal visual** untuk memberikan makna yang cepat dan efisien terhadap dunia di sekitar kita.  
Salah satu fenomena terkenal yang menunjukkan hal ini adalah **ilusi Hermann Grid** atau **ilusi titik putih**, di mana pengamat melihat titik-titik putih atau abu-abu yang tampak muncul dan menghilang di persimpangan garis hitam.

Fenomena ini terjadi karena **mekanisme adaptasi kontras** di retina dan korteks visual otak. Artikel ini menjelaskan bagaimana ilusi tersebut dapat direpresentasikan menggunakan **LaTeX PSTricks**, serta memberikan analisis mendalam tentang struktur kode dan konsep ilmiah yang melatarinya.

---

## Kode Sumber LaTeX

Berikut adalah kode lengkap yang digunakan untuk membuat pola ilusi menggunakan **PSTricks**.

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

## Penjelasan Struktur Kode

### **Deklarasi Dokumen**
```latex
\documentclass[pstricks,border=12pt]{standalone}
```
Baris ini menentukan bahwa dokumen akan menggunakan kelas `standalone`, yang memungkinkan output berupa satu gambar tunggal tanpa elemen halaman tambahan seperti margin atau header.  
Opsi `pstricks` mengaktifkan pustaka **PSTricks** untuk membuat grafik berbasis PostScript.

---

### **Mendefinisikan Gaya Kisi**
```latex
\newpsstyle{gridstyle}
{
    gridlabels=0,
    gridwidth=6pt,
    subgriddiv=1,
    gridcolor=gray,
}
```
Bagian ini mendefinisikan gaya bernama `gridstyle` yang akan digunakan untuk menggambar kisi.  
- `gridlabels=0` menonaktifkan label koordinat.  
- `gridwidth=6pt` mengatur ketebalan garis kisi.  
- `gridcolor=gray` memberi warna abu-abu pada garis.  
- `subgriddiv=1` memastikan tidak ada subdivisi tambahan pada kisi.

---

### **Lingkungan Gambar PSTricks**
```latex
\begin{pspicture}(8,8)
```
Mendefinisikan area gambar dengan ukuran 8x8 satuan. Semua elemen visual akan digambar di dalam area ini.

---

### **Latar Belakang dan Kisi**
```latex
\psframe*(8,8)
\psgrid[style=gridstyle]
```
- `\psframe*(8,8)` membuat persegi hitam berukuran 8x8 sebagai latar belakang.  
- `\psgrid[style=gridstyle]` menggambar kisi abu-abu di atas latar belakang hitam menggunakan gaya yang telah ditentukan.

---

### **Mengatur Warna Garis dan Titik**
```latex
\psset{linecolor=white}
```
Mengubah warna garis aktif menjadi putih agar titik-titik yang digambar berikutnya kontras terhadap latar belakang hitam.

---

### **Menggambar Titik Putih Menggunakan `multips`**
```latex
\multips(0,1)(0,1){7}{\multips(1,0)(1,0){7}{\qdisk(0,0){4.242pt}}}
```
Bagian ini menggambar **pola titik-titik putih** yang membentuk struktur kisi:
- `\multips(0,1)(0,1){7}{...}` mengulangi pola secara vertikal sebanyak 7 kali.  
- Di dalamnya, `\multips(1,0)(1,0){7}{...}` menggambar 7 titik secara horizontal untuk setiap baris.  
- `\qdisk(0,0){4.242pt}` menggambar sebuah **disk (titik) putih** kecil berdiameter sekitar 4.242 pt di setiap posisi kisi.

---

### **Penutupan Lingkungan dan Dokumen**
```latex
\end{pspicture}
\end{document}
```
Menutup lingkungan `pspicture` dan `document`. Hasil akhirnya adalah pola persegi dengan kisi abu-abu dan titik-titik putih yang tampak muncul di persimpangan.

---

## Analisis Visual dan Perseptual

Fenomena yang muncul dari gambar ini adalah ilusi titik putih yang tampak **berkedip** atau **menghilang** ketika pengamat memindahkan pandangan mereka di sekitar gambar.  
Hal ini terjadi karena **neuron ganglion retina** di mata manusia memiliki **medan reseptif (receptive fields)** yang berfungsi mendeteksi kontras lokal. Ketika area sekitarnya lebih gelap, sinyal cahaya di pusat medan reseptif dipersepsikan lebih terang — menciptakan ilusi titik putih yang muncul di persimpangan garis.

---

## Eksperimen dan Variasi

Anda dapat memodifikasi parameter berikut untuk mengeksplorasi efek visual yang berbeda:

| Parameter | Fungsi | Efek Visual |
|------------|----------|-------------|
| `gridwidth` | Ketebalan garis kisi | Mempengaruhi kekuatan ilusi |
| `gridcolor` | Warna garis | Mengubah tingkat kontras |
| Ukuran titik (`\qdisk`) | Besar kecilnya titik | Mengubah jumlah titik yang tampak |
| Jumlah pengulangan (`7`) | Banyaknya kisi | Mengontrol kerapatan pola |

Contoh variasi kecil:
```latex
\psgrid[style=gridstyle,gridcolor=lightgray]
\qdisk(0,0){3pt}
```

---

## Relevansi Ilmiah dan Artistik

Ilusi Hermann Grid bukan hanya eksperimen visual sederhana, tetapi juga memiliki nilai ilmiah dan artistik yang besar.  
- Dalam **psikologi kognitif**, ilusi ini membantu memahami bagaimana otak memproses kontras dan ruang.  
- Dalam **desain visual**, fenomena ini menginspirasi pembuatan pola dan tekstur yang menarik.  
- Dalam **seni matematika**, kombinasi antara geometri dan persepsi menghasilkan karya visual yang elegan dan ilmiah sekaligus.

---

## Kesimpulan

Ilusi titik putih pada kisi gelap membuktikan bahwa persepsi visual manusia tidak selalu obyektif. Dengan menggunakan **LaTeX PSTricks**, kita dapat merepresentasikan fenomena ini secara matematis dan estetis.  
Melalui eksperimen sederhana, kita dapat mempelajari bagaimana **kontras dan konteks** memengaruhi cara kita melihat dunia.

---

## Referensi

1. Hermann, L. (1870). *Eine Erscheinung simultanen Contrastes*. Pflügers Archiv für die gesamte Physiologie.  
2. Coren, S., & Girgus, J. S. (1978). *Seeing is Deceiving: The Psychology of Visual Illusions.* Lawrence Erlbaum.  
3. Gregory, R. L. (1997). *Eye and Brain: The Psychology of Seeing.* Oxford University Press.  
4. PSTricks User Manual, Version 3.1.8 (2023).  

---

**Ditulis oleh:** [Aan Triono](https://www.aantriono.com)  
**Lisensi:** CC BY-SA 4.0

