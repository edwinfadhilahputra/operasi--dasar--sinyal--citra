# Eksperimen Operasi Dasar pada Sinyal dan Citra
[cite_start]**Mata Kuliah:** Pengolahan Sinyal Digital [cite: 2]  
**Institusi:** Universitas Darussalam Gontor  

---

## 👤 Identitas Mahasiswa
* **Nama:** Edwin Fadhilah Putra
* **NIM:** 452024611002
* **Kelas/Prodi:** A1 / Teknik Informatika

---

## 📝 Deskripsi Singkat Project
[cite_start]Project ini merupakan eksperimen berbasis Python untuk menerapkan dan menganalisis berbagai operasi dasar pada sinyal 1D (diskrit) dan citra 2D[cite: 12]. [cite_start]Fokus utama dari eksperimen ini adalah memahami bagaimana operasi matematika sederhana seperti penjumlahan, penggeseran (translasi), dan amplifikasi menjadi pondasi dasar bagi konsep-konsep yang lebih besar dalam Pengolahan Sinyal Digital, seperti prinsip superposisi, pengujian sistem linier, filtering, *image blending*, serta augmentasi data citra.

---

## 📚 Library yang Digunakan
[cite_start]Project ini diimplementasikan menggunakan Python dengan beberapa library standar berikut[cite: 27]:
* [cite_start]**NumPy**: Untuk komputasi numerik, manipulasi matriks citra, dan pembuatan sinyal diskrit[cite: 28].
* [cite_start]**Matplotlib**: Untuk visualisasi plot sinyal 1D dan penampilan histogram citra[cite: 29].
* [cite_start]**OpenCV (cv2)**: Untuk membaca, mengubah ukuran (*resizing*), translasi, dan manipulasi piksel citra 2D[cite: 30].
* **Pandas**: Untuk pembuatan tabel ringkasan analisis data kelinieran sistem di dalam notebook.

---

## 🚀 Cara Menjalankan Notebook
[cite_start]Anda dapat menjalankan project ini di lingkungan lokal (Jupyter Notebook) maupun berbasis cloud (Google Colab/Kaggle).

### 1. Kloning Repositori
```bash
[git clone [https://github.com/ABIN-KUN123/operasi-dasar-sinyal-citra.git](https://github.com/edwinfadhilahputra/operasi--dasar--sinyal--citra)
cd operasi-dasar-sinyal-citra](url)

```
## 2. Instalasi Dependensi
Pastikan Python sudah terinstal, lalu pasang library yang diperlukan melalui `requirements.txt`:

```bash
pip install -r requirements.txt

```
## 3. Menjalankan Notebook Jika menggunakan Jupyter Notebook/Lab lokal,
jalankan perintah:

```Bash
jupyter notebook notebook/operasi_sinyal_citra.ipynb

```
## 📂 Struktur Folder ProjectRepositori ini disusun berdasarkan standar tata letak berikut:  

```Bash
Plaintextoperasi-dasar-sinyal-citra/
│
├── notebook/
│   └── operasi_sinyal_citra.ipynb   # File Jupyter Notebook eksperimen utama [cite: 266, 267]
│
├── images/
│   └── NB-GN22-3840-2160.jpg        # File citra asli gunung yang digunakan [cite: 268]
│
├── report/
│   └── laporan.pdf                  # Laporan resmi hasil eksperimen (Maks 8 hal) [cite: 269, 270]
│
├── README.md                        # Dokumentasi utama project [cite: 271]
└── requirements.txt                 # Daftar library beserta versi yang digunakan [cite: 272]

```
## 📊 Ringkasan Hasil Eksperimen
1. Pemrosesan Sinyal 1D
   - Penjumlahan ($x_1[n] + x_2[n]$): Menghasilkan pergeseran vertikal (DC Offset) pada sinyal        sinusoidal sebesar $+1$ ketika sinyal unit step aktif ($n \geq 5$).
   - Penggeseran ($x[n-k]$): Nilai $k=4$ (positif) memberikan efek penundaan (delay/bergeser ke       kanan), sedangkan $k=-3$ (negatif) mempercepat sinyal (advance/bergeser ke kiri).
   - Amplifikasi ($\alpha x[n]$): Nilai $\alpha > 1$ memperbesar amplitudo (gain), $0 < \alpha <      1$ memperkecil amplitudo (attenuation), dan $\alpha = -1$ membalikkan fase gelombang             sebesar $180^\circ$.
  
  2. Pemrosesan Citra 2DPenjumlahan Citra:
     - Penggabungan dua citra secara element-wise wajib memiliki dimensi yang sama.
     - Penggunaan fungsi cv2.add() memberikan proteksi clipping otomatis pada batas intensitas          piksel 255 (putih murni) untuk mencegah terjadinya overflow.
     - Penggeseran Citra (Translasi): Menggeser posisi objek secara spasial, di mana area kosong        baru yang terbentuk akibat pergeseran akan diisi secara otomatis oleh nilai 0 (warna             hitam).  
     - Amplifikasi Citra: Mengalikan nilai intensitas piksel dengan konstanta $\alpha$. Eksperimen pada foto gunung dengan $\alpha = 1.5$ membuktikan peningkatan kontras dan kecerahan secara linear melalui kurva histogram yang melebar ke kanan.
   3. Uji Sistem LinierEksperimen membuktikan bahwa:
      - Sifat sistem $T_1(x) = 2x$ terbukti LINIER karena berhasil memenuhi sifat Homogenitas            dan Additivitas secara simultan.
      - Sifat sistem $T_2(x) = x^2$ terbukti NON-LINIER karena komponen pangkat dua merusak              nilai penskalaan sehingga gagal memenuhi syarat superposisi tersebut.

## 📌 Kesimpulan Singkat

Operasi dasar pemrosesan sinyal seperti penjumlahan, penggeseran, dan amplifikasi bukan sekadar manipulasi matematika biasa, melainkan pilar utama dalam membangun sistem pengolahan data digital yang lebih kompleks. Melalui eksperimen ini, perbedaan karakteristik pengolahan data antara domain 1D (waktu/indeks diskrit) dan domain 2D (koordinat ruang spasial piksel) dapat dipahami secara teknis maupun konseptual. Selain itu, pemahaman atas kelinieran suatu sistem menjadi kunci krusial dalam memprediksi keluaran serta merancang arsitektur filter digital di dunia nyata.
