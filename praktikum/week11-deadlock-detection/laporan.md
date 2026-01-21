# Laporan Praktikum Minggu [X]
Topik: Simulasi dan Deteksi Deadlock

---

## Identitas
- **Nama**  : Alfan Nur Fadzilah
- **NIM**   : 250320575
- **Kelas** : 1DSRA

---

## Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:
1. Membuat program sederhana untuk mendeteksi deadlock.  
2. Menjalankan simulasi deteksi deadlock dengan dataset uji.  
3. Menyajikan hasil analisis deadlock dalam bentuk tabel.  
4. Memberikan interpretasi hasil uji secara logis dan sistematis.  
5. Menyusun laporan praktikum sesuai format yang ditentukan.

---

## Dasar Teori
Simulasi dan Deteksi Deadlock

Deadlock adalah kondisi pada sistem operasi di mana dua atau lebih proses saling menunggu sumber daya yang sedang dipegang oleh proses lain, sehingga tidak ada proses yang dapat melanjutkan eksekusi. Deadlock umumnya terjadi pada sistem multiprogramming yang melibatkan pembagian sumber daya secara bersamaan.

Terjadinya deadlock dipengaruhi oleh empat kondisi utama, yaitu mutual exclusion, hold and wait, no preemption, dan circular wait. Jika keempat kondisi tersebut terpenuhi secara bersamaan, maka deadlock dapat terjadi.

Simulasi deadlock digunakan untuk memodelkan interaksi antara proses dan sumber daya guna memahami bagaimana deadlock terjadi serta untuk menguji strategi penanganannya. Dengan simulasi, perilaku sistem dapat dianalisis tanpa harus terjadi deadlock nyata pada sistem sebenarnya.

Deteksi deadlock adalah mekanisme yang digunakan sistem operasi untuk mengidentifikasi adanya deadlock. Salah satu cara yang umum digunakan adalah dengan resource allocation graph atau algoritma pendeteksian yang memeriksa adanya siklus dalam penggunaan sumber daya. Jika terdeteksi deadlock, sistem dapat mengambil tindakan seperti menghentikan proses atau mengambil kembali sumber daya.

---

## Langkah Praktikum
1. **Menyiapkan Dataset**

   Gunakan dataset sederhana yang berisi:
   - Daftar proses  
   - Resource Allocation  
   - Resource Request / Need

   Contoh tabel:

   | Proses | Allocation | Request |
   |:--:|:--:|:--:|
   | P1 | R1 | R2 |
   | P2 | R2 | R3 |
   | P3 | R3 | R1 |

2. **Implementasi Algoritma Deteksi Deadlock**

   Program minimal harus:
   - Membaca data proses dan resource.  
   - Menentukan apakah sistem berada dalam kondisi deadlock.  
   - Menampilkan proses mana saja yang terlibat deadlock.

3. **Eksekusi & Validasi**

   - Jalankan program dengan dataset uji.  
   - Validasi hasil deteksi dengan analisis manual/logis.  
   - Simpan hasil eksekusi dalam bentuk screenshot.

4. **Analisis Hasil**

   - Sajikan hasil deteksi dalam tabel (proses deadlock / tidak).  
   - Jelaskan mengapa deadlock terjadi atau tidak terjadi.  
   - Kaitkan hasil dengan teori deadlock (empat kondisi).

5. **Commit & Push**

   ```bash
   git add .
   git commit -m "Minggu 11 - Deadlock Detection"
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
1. Apa perbedaan antara *deadlock prevention*, *avoidance*, dan *detection*?

 **Jawaban**: Perbedaan deadlock prevention, avoidance, dan detection terletak pada cara dan waktu penanganannya:

Deadlock Prevention: Mencegah deadlock sejak awal dengan menghilangkan salah satu dari empat kondisi deadlock, sehingga deadlock tidak mungkin terjadi.

Deadlock Avoidance: Menghindari deadlock dengan mengatur alokasi sumber daya secara hati-hati agar sistem selalu berada pada kondisi aman (safe state).

Deadlock Detection: Membiarkan deadlock terjadi, lalu mendeteksinya dan mengambil tindakan untuk memulihkan sistem.

2. Mengapa deteksi deadlock tetap diperlukan dalam sistem operasi?

 **Jawaban**: Deteksi deadlock tetap diperlukan dalam sistem operasi karena tidak semua deadlock dapat dicegah atau dihindari secara efisien.

Pada sistem yang kompleks, penerapan prevention atau avoidance dapat menurunkan kinerja atau membatasi penggunaan sumber daya. Oleh karena itu, sistem operasi sering membiarkan deadlock terjadi dan menggunakan deteksi deadlock untuk mengenali kondisi tersebut, sehingga dapat dilakukan tindakan pemulihan seperti menghentikan proses atau mengambil kembali sumber daya.

3. Apa kelebihan dan kekurangan pendekatan deteksi deadlock?

 **Jawaban**: Kelebihan:

Penggunaan sumber daya lebih fleksibel karena sistem tidak terlalu dibatasi.

Cocok untuk sistem dengan tingkat deadlock yang jarang terjadi.

Implementasi lebih sederhana dibanding avoidance.

Kekurangan:

Deadlock dibiarkan terjadi sebelum ditangani.

Memerlukan overhead untuk proses pendeteksian.

Dibutuhkan mekanisme pemulihan yang dapat mengganggu proses yang sedang berjalan.

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
