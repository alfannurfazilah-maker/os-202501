
# Laporan Praktikum Minggu 9
Topik: Simulasi Algoritma Penjadwalan CPU

---

## Identitas
- **Nama**  : Alfan Nur Fadzilah
- **NIM**   : 250320575
- **Kelas** : 1DSRA

---

## Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:
1. Membuat program simulasi algoritma penjadwalan FCFS dan/atau SJF.  
2. Menjalankan program dengan dataset uji yang diberikan atau dibuat sendiri.  
3. Menyajikan output simulasi dalam bentuk tabel atau grafik.  
4. Menjelaskan hasil simulasi secara tertulis.  
5. Mengunggah kode dan laporan ke Git repository dengan rapi dan tepat waktu.

---

## Dasar Teori
Simulasi algoritma penjadwalan CPU merupakan bagian penting dalam pembelajaran sistem operasi. Dengan simulasi, proses penjadwalan dapat dianalisis secara sistematis sehingga dapat diketahui algoritma yang paling efektif dalam meningkatkan kinerja CPU dan sistem secara keseluruhan.

---

## Langkah Praktikum
1. Langkah-langkah yang dilakukan.  
2. Perintah yang dijalankan.  
3. File dan kode yang dibuat.  
4. Commit message yang digunakan.

---

## Kode / Perintah
1. **Menyiapkan Dataset**

   Buat dataset proses minimal berisi:

   | Proses | Arrival Time | Burst Time |
   |:--:|:--:|:--:|
   | P1 | 0 | 6 |
   | P2 | 1 | 8 |
   | P3 | 2 | 7 |
   | P4 | 3 | 3 |

2. **Implementasi Algoritma**

   Program harus:
   - Menghitung *waiting time* dan *turnaround time*.  
   - Mendukung minimal **1 algoritma (FCFS atau SJF non-preemptive)**.  
   - Menampilkan hasil dalam tabel.

3. **Eksekusi & Validasi**

   - Jalankan program menggunakan dataset uji.  
   - Pastikan hasil sesuai dengan perhitungan manual minggu sebelumnya.  
   - Simpan hasil eksekusi (screenshot).

4. **Analisis**

   - Jelaskan alur program.  
   - Bandingkan hasil simulasi dengan perhitungan manual.  
   - Jelaskan kelebihan dan keterbatasan simulasi.

5. **Commit & Push**

   ```bash
   git add .
   git commit -m "Minggu 9 - Simulasi Scheduling CPU"
   git push origin main
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
1. Mengapa simulasi diperlukan untuk menguji algoritma scheduling?

   **Jawaban:**  Simulasi sangat penting dalam pengujian algoritma scheduling karena memberikan cara yang aman, efisien, dan sistematis untuk memahami, mengevaluasi, serta membandingkan kinerja algoritma penjadwalan CPU sebelum diterapkan pada sistem nyata.
2. Apa perbedaan hasil simulasi dengan perhitungan manual jika dataset besar?
 
   **Jawaban:**  Pada dataset kecil, perhitungan manual masih dapat digunakan untuk verifikasi konsep. Namun, pada dataset besar, simulasi jauh lebih unggul karena lebih cepat, akurat, konsisten, dan mampu menangani kompleksitas algoritma penjadwalan CPU secara efisien.
3. Algoritma mana yang lebih mudah diimplementasikan? Jelaskan.

   **Jawaban:**  FCFS adalah algoritma penjadwalan CPU yang paling mudah diimplementasikan karena logikanya sederhana, tidak preemptive, dan hanya membutuhkan antrian dasar tanpa perhitungan tambahan.

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
