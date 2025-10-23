
# Laporan Praktikum Minggu 2
Topik: Struktur System Call dan Fungsi Kernel

---

## Identitas
- **Nama**  : Alfan Nur Fadzilah  
- **NIM**   : 250320575
- **Kelas** : 1DSRA

---

## Tujuan
Tuliskan tujuan praktikum minggu ini:
- 1.Menjelaskan konsep dan fungsi system call dalam sistem operasi.
- 2.Mengidentifikasi jenis-jenis system call dan fungsinya.
- 3.Mengamati alur perpindahan mode user ke kernel saat system call terjadi.
- 4.Menggunakan perintah Linux untuk menampilkan dan menganalisis system call.

---

## Dasar Teori
System call adalah antarmuka (interface) antara program aplikasi/user dan kernel sistem operasi. System call memungkinkan program meminta layanan dari sistem operasi, seperti mengakses file, mengatur proses, atau menggunakan perangkat keras.

Alur Umum System Call:
- Program user memanggil fungsi system call.
- Fungsi tersebut berpindah ke mode kernel (melalui interrupt atau trap).
- Kernel menjalankan layanan yang diminta.
- Hasil dikembalikan ke program user.

---

## Langkah Praktikum
1. Langkah-langkah yang dilakukan.  
2. Perintah yang dijalankan.  
3. File dan kode yang dibuat.  
4. Commit message yang digunakan.

---

## Kode / Perintah
1. **Setup Environment**
   - Gunakan Linux (Ubuntu/WSL).
   - Pastikan perintah `strace` dan `man` sudah terinstal.
   - Konfigurasikan Git (jika belum dilakukan di minggu sebelumnya).

2. **Eksperimen 1 – Analisis System Call**
   Jalankan perintah berikut:
   ```bash
   strace ls
   ```
   > Catat 5–10 system call pertama yang muncul dan jelaskan fungsinya.  
   Simpan hasil analisis ke `results/syscall_ls.txt`.

3. **Eksperimen 2 – Menelusuri System Call File I/O**
   Jalankan:
   ```bash
   strace -e trace=open,read,write,close cat /etc/passwd
   ```
   > Analisis bagaimana file dibuka, dibaca, dan ditutup oleh kernel.

4. **Eksperimen 3 – Mode User vs Kernel**
   Jalankan:
   ```bash
   dmesg | tail -n 10
   ```
   > Amati log kernel yang muncul. Apa bedanya output ini dengan output dari program biasa?

5. **Diagram Alur System Call**
   - Buat diagram yang menggambarkan alur eksekusi system call dari program user hingga kernel dan kembali lagi ke user mode.
   - Gunakan draw.io / mermaid.
   - Simpan di:
     ```
     praktikum/week2-syscall-structure/screenshots/syscall-diagram.png
     ```

6. **Commit & Push**
   ```bash
   git add .
   git commit -m "Minggu 2 - Struktur System Call dan Kernel Interaction"
   git push origin main
   ```  
## Hasil Eksekusi
### Diagram syscall
[Screenshot hasil](<screenshots/Screenshot 2025-10-22 121029.png>)


## D. Tugas & Quiz
### Tugas
1. Dokumentasikan hasil eksperimen `strace` dan `dmesg` dalam bentuk tabel observasi.  
2. Buat diagram alur system call dari aplikasi → kernel → hardware → kembali ke aplikasi.  
3. Tulis analisis 400–500 kata tentang:
   - Mengapa system call penting untuk keamanan OS?
   -  **Jawaban:** System call sangat penting untuk keamanan sistem operasi (OS) karena menjadi jembatan utama antara program pengguna (user space) dan inti sistem operasi (kernel space). Peranannya sangat krusial karena memberikan kontrol terbatas dan terstruktur terhadap akses ke sumber daya sistem. Berikut adalah beberapa alasan utama mengapa system call penting untuk keamanan OS:
   - Bagaimana OS memastikan transisi user–kernel berjalan aman?
   -  **Jawaban:** Mode CPU (User vs Kernel):
Program user berjalan di mode terbatas (user mode), hanya OS di kernel mode yang punya akses penuh.

System Call sebagai Gerbang Aman:
Transisi hanya bisa lewat system call — jalur resmi dan dikontrol.

Validasi Argumen:
Kernel memeriksa semua input dari user untuk mencegah serangan.

Stack Terpisah:
Kernel pakai stack sendiri, terpisah dari user, untuk keamanan eksekusi
   - Sebutkan contoh system call yang sering digunakan di Linux.
   -  **Jawaban:**  -File dan I/O

open() – Membuka file.

read() – Membaca data dari file.

write() – Menulis data ke file.

close() – Menutup file.

lseek() – Mengatur posisi baca/tulis dalam file.

 Proses

fork() – Membuat proses baru.

exec() – Menjalankan program baru.

wait() – Menunggu proses anak selesai.

exit() – Keluar dari proses.

- Memori

mmap() – Memetakan file atau memori ke ruang alamat proses.

brk() – Mengatur batas atas heap proses.

- Keamanan dan Akses

chmod() – Mengubah mode/izin file.

chown() – Mengubah pemilik file.

getuid() / geteuid() – Mendapatkan UID pengguna.

- Jaringan

socket() – Membuat soket jaringan.

bind() – Mengikat alamat ke soket.

connect() – Menghubungkan ke soket jarak jauh.

accept() – Menerima koneksi masuk.

- Informasi Sistem

getpid() – Mendapatkan ID proses.

uname() – Mendapatkan info sistem.

4. Simpan semua hasil di:
   ```
   praktikum/week2-syscall-structure/
```

---

---



---

## Quiz
1. Apa fungsi utama system call dalam sistem operasi. 
  - **Jawaban:**  System call berfungsi sebagai jembatan antara program pengguna (user program) dan kernel sistem operasi. Fungsinya adalah untuk memungkinkan program mengakses layanan sistem operasi secara aman dan terkendali.
2. [Sebutkan 4 kategori system call yang umum digunakan.]  
   **Jawaban:**  Process Control,File Management,Device Management,Information Maintenance
3. [Mengapa system call tidak bisa dipanggil langsung oleh user program]  
   **Jawaban:**  System call tidak bisa dipanggil langsung oleh user program karena membutuhkan hak akses khusus dan harus dijalankan di mode kernel untuk menjamin keamanan, stabilitas, dan kontrol sistem.

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
