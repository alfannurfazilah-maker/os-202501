
# Laporan Praktikum Minggu 14
Topik: Penyusunan Laporan Praktikum Format IMRAD

---

## Identitas
- **Nama**  : Alfan Nur Fadzilah
- **NIM**   : 250320575
- **Kelas** : 1DSRA

---

## Tujuan
1. Menyusun laporan praktikum dengan struktur ilmiah (Pendahuluan–Metode–Hasil–Pembahasan–Kesimpulan).
2. Menyajikan hasil uji dalam bentuk tabel dan/atau grafik yang jelas.
3. Menuliskan analisis hasil dengan argumentasi yang logis.
4. Menyusun sitasi dan daftar pustaka dengan format yang konsisten.
5. Mengunggah draft laporan ke repositori dengan rapi dan tepat waktu.

---

## Dasar Teori
Format IMRAD merupakan struktur penulisan yang efektif dalam penyusunan laporan praktikum. Dengan membagi laporan ke dalam bagian Introduction, Methods, Results, dan Discussion, proses praktikum dapat dilaporkan secara jelas, runtut, dan ilmiah, sehingga memudahkan penyampaian informasi dan evaluasi hasil praktikum

---

## Langkah Praktikum
1. **Menentukan Topik Laporan**

   Pilih 1 topik dari praktikum sebelumnya (mis. Minggu 9/10/11/13) dan tetapkan tujuan eksperimen yang ingin disampaikan.

2. **Menyiapkan Bahan**

   - Kode/program yang digunakan.
   - Dataset/parameter uji (jika ada).
   - Bukti hasil eksekusi (screenshot) dan/atau grafik.

3. **Menulis Laporan dengan Struktur IMRAD**

   Tulis `praktikum/week14-laporan-imrad/laporan.md` dengan struktur minimal berikut:
   - **Pendahuluan (Introduction):** latar belakang, rumusan masalah/tujuan.
   - **Metode (Methods):** lingkungan uji, langkah eksperimen, parameter/dataset, cara pengukuran.
   - **Hasil (Results):** tabel/grafik hasil uji, ringkasan temuan.
   - **Pembahasan (Discussion):** interpretasi hasil, keterbatasan, perbandingan teori/ekspektasi.
   - **Kesimpulan:** 2–4 poin ringkas menjawab tujuan.

4. **Menyajikan Tabel/Grafik**

   - Tabel harus diberi judul/keterangan singkat.
   - Jika menggunakan grafik: jelaskan sumbu dan arti grafik.

5. **Sitasi dan Daftar Pustaka**

   - Cantumkan referensi minimal 2 sumber.
   - Gunakan format konsisten (mis. daftar bernomor).

6. **Commit & Push Draft**

   ```bash
   git add .
   git commit -m "Minggu 14 - Draft Laporan IMRAD"
   git push origin main
   ```

---

## Kode / Perintah
Tuliskan potongan kode atau perintah utama:
```bash
uname -a
lsmod | head
dmesg | head
```

---

## Hasil Eksekusi
Sertakan screenshot hasil percobaan atau diagram:
![Screenshot hasil](screenshots/example.png)

---

## Analisis
- Jelaskan makna hasil percobaan.  
- Hubungkan hasil dengan teori (fungsi kernel, system call, arsitektur OS).  
- Apa perbedaan hasil di lingkungan OS berbeda (Linux vs Windows)?  

---

## Kesimpulan
Tuliskan 2–3 poin kesimpulan dari praktikum ini.

---

## Quiz
1. Mengapa format IMRAD membantu membuat laporan praktikum lebih ilmiah dan mudah dievaluasi?
 
   **Jawaban:** Format IMRAD membuat laporan praktikum lebih ilmiah karena tersusun secara terstruktur, objektif, dan sesuai standar penulisan ilmiah, sekaligus memudahkan proses evaluasi oleh dosen atau penilai.
    
2. Apa perbedaan antara bagian **Hasil** dan **Pembahasan**?
   
   **Jawaban:** Perbedaan antara bagian Hasil dan Pembahasan adalah sebagai berikut:

**Bagian Hasil (Results) :**

- Menyajikan data atau temuan praktikum secara objektif

- Berisi hasil pengamatan, perhitungan, tabel, grafik, atau gambar

- Tidak disertai analisis atau pendapat

- Fokus pada apa yang diperoleh dari praktikum

**Bagian Pembahasan (Discussion) :**

- Berisi analisis dan interpretasi dari hasil yang diperoleh

- Mengaitkan hasil praktikum dengan teori atau referensi

- Membahas penyebab hasil, kesalahan, dan keterbatasan praktikum
- Fokus pada mengapa hasil tersebut terjadi
    
3. Mengapa sitasi dan daftar pustaka penting, bahkan untuk laporan praktikum?
   
   **Jawaban:**  Sitasi dan daftar pustaka penting untuk menjaga kejujuran akademik, memperkuat landasan teori, serta meningkatkan kualitas dan kredibilitas laporan praktikum.

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
