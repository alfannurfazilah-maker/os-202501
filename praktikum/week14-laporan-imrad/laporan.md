
# Laporan Praktikum Minggu 14
Topik: Penyusunan Laporan Praktikum Format IMRAD

---

## Identitas
- **Nama**  : Alfan Nur Fadzilah
- **NIM**   : 250320575
- **Kelas** : 1DSRA

---

## 1. Pendahuluan
Simulasi algoritma penjadwalan CPU merupakan bagian penting dalam pembelajaran sistem operasi karena memungkinkan analisis sistematis terhadap kinerja berbagai algoritma penjadwalan. Pada praktikum minggu ke-9, fokus percobaan adalah algoritma First Come First Served (FCFS). Tujuan eksperimen ini adalah mengimplementasikan simulasi FCFS, menjalankannya menggunakan dataset proses, menganalisis hasil berupa waiting time dan turnaround time, serta membandingkan output simulasi dengan perhitungan manual.

## 2. Metode
**Lingkungan Uji:**
- Bahasa: Python (atau sesuai program yang digunakan)
- Sistem Operasi: Windows/Linux
- Tools: Terminal/IDE, Git untuk version control

**Dataset/Parameter:**
| Proses | Arrival Time | Burst Time |
|-------|--------------|------------|
| P1 | 0 | 6 |
| P2 | 1 | 8 |
| P3 | 2 | 7 |
| P4 | 3 | 3 |

**Langkah Eksperimen:**
1. Menentukan dataset proses.
2. Mengimplementasikan algoritma FCFS.
3. Menghitung waiting time dan turnaround time.
4. Menjalankan program dan memperoleh hasil.
5. Membandingkan hasil dengan perhitungan manual.

**Cara Pengukuran:**
- Waiting time = waktu CPU mulai mengeksekusi proses − arrival time.
- Turnaround time = waiting time + burst time.

## 3. Hasil
**Tabel Hasil Simulasi FCFS:**
| Proses | Arrival Time | Burst Time | Waiting Time | Turnaround Time |
|--------|--------------|------------|--------------|-----------------|
| P1 | 0 | 6 | 0 | 6 |
| P2 | 1 | 8 | 5 | 13 |
| P3 | 2 | 7 | 12 | 19 |
| P4 | 3 | 3 | 16 | 19 |

Rata-rata Waiting Time: **8.25**  
Rata-rata Turnaround Time: **14.25**

**Screenshot Hasil Eksekusi:**  
![Screenshot hasil](screenshots/week9.png)



## 4. Pembahasan
Program berjalan sesuai dengan logika dasar FCFS, yaitu proses dieksekusi berdasarkan urutan kedatangannya. Waiting time dan turnaround time dihitung otomatis oleh program menggunakan current time. Hasil simulasi identik dengan perhitungan manual, sehingga implementasi dinyatakan benar.

Simulasi lebih cepat, akurat, dan konsisten dibanding perhitungan manual, terutama untuk dataset besar. Namun, simulasi tetap memiliki keterbatasan seperti ketergantungan pada logika program dan tidak selalu mencerminkan kondisi sistem nyata.

## 5. Kesimpulan
- Simulasi FCFS berhasil dijalankan dengan dataset empat proses.
- Hasil simulasi sesuai dengan teori dan perhitungan manual.
- Simulasi mempermudah analisis performa algoritma penjadwalan.
- FCFS mudah diimplementasikan dan menjadi dasar memahami algoritma lain.

## 6. Daftar Pustaka
1. Silberschatz, Abraham. *Operating System Concepts*. Wiley.
2. Stallings, William. *Operating Systems: Internals and Design Principles*.


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
- Apa bagian yang paling menantang minggu ini?  semua bagian menantang
- Bagaimana cara Anda mengatasinya?  mencari tau di AI

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
