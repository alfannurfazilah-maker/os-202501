
# Laporan Praktikum Minggu 3
### Topik: Manajemen File dan Permission di Linux

---

## Identitas
- **Nama**  : Alfan Nur Fadzilah  
- **NIM**   : 250320575 
- **Kelas** : 1DSRA

---

## Tujuan  
Setelah menyelesaikan tugas ini, mahasiswa mampu:
- Menggunakan perintah ls, pwd, cd, cat untuk navigasi file dan direktori.
- Menggunakan chmod dan chown untuk manajemen hak akses file.
- Menjelaskan hasil output dari perintah Linux dasar.
- Menyusun laporan praktikum dengan struktur yang benar.
- Mengunggah dokumentasi hasil ke Git Repository tepat waktu.

---

## Dasar Teori
Sistem file Linux adalah struktur penyimpanan data yang bersifat hierarkis, di mana semua file dan direktori disusun dalam bentuk pohon yang dimulai dari direktori akar (/). Melalui sistem ini, Linux mengatur bagaimana data disimpan, diakses, dan diorganisasikan sehingga pengguna dapat mengelola file dengan efisien. Setiap komponen dalam sistem Linux, termasuk perangkat keras, dianggap sebagai bagian dari sistem file.

Dalam sistem Linux, setiap file atau direktori memiliki hak akses (permission) yang menentukan siapa yang dapat membaca, menulis, atau mengeksekusi file tersebut. Hak akses ini dibagi menjadi tiga kategori pengguna, yaitu owner (pemilik), group (kelompok), dan others (pengguna lain).

Selain itu, setiap file memiliki kepemilikan yang mencakup pemilik dan kelompok tertentu. Kepemilikan ini dapat diubah dengan perintah chown untuk mengganti pemilik dan chgrp untuk mengganti kelompok. Untuk mengatur izin akses, digunakan perintah chmod, baik dalam bentuk simbolik (misalnya u+rwx) maupun numerik.

---

## Langkah Praktikum

1. **Setup Environment**
   - Gunakan Linux (Ubuntu/WSL).
   - Pastikan folder kerja berada di dalam direktori repositori Git praktikum:
     ```
     praktikum/week3-linux-fs-permission/
     ```

2. **Eksperimen 1 – Navigasi Sistem File**
   Jalankan perintah berikut:
   ```bash
   pwd
   ls -l
   cd /tmp
   ls -a
   ```
   - Jelaskan hasil tiap perintah.
   - Catat direktori aktif, isi folder, dan file tersembunyi (jika ada).

3. **Eksperimen 2 – Membaca File**
   Jalankan perintah:
   ```bash
   cat /etc/passwd | head -n 5
   ```
   - Jelaskan isi file dan struktur barisnya (user, UID, GID, home, shell).

4. **Eksperimen 3 – Permission & Ownership**
   Buat file baru:
   ```bash
   echo "Hello <NAME><NIM>" > percobaan.txt
   ls -l percobaan.txt
   chmod 600 percobaan.txt
   ls -l percobaan.txt
   ```
   - Analisis perbedaan sebelum dan sesudah chmod.  
   - Ubah pemilik file (jika memiliki izin sudo):
   ```bash
   sudo chown root percobaan.txt
   ls -l percobaan.txt
   ```
   - Catat hasilnya.

5. **Eksperimen 4 – Dokumentasi**
   - Ambil screenshot hasil terminal dan simpan di:
     ```
     praktikum/week3-linux-fs-permission/screenshots/
     ```
   - Tambahkan analisis hasil pada `laporan.md`.

6. **Commit & Push**
   ```bash
   git add .
   git commit -m "Minggu 3 - Linux File System & Permission"
   git push origin main
---

## Hasil Eksekusi
Sertakan screenshot hasil percobaan atau diagram:
![Screenshot hasil](<screenshots/Screenshot 2025-10-29 180259.png>)

---

## Analisis
| No | Perintah | Fungsi | Hasil / Penjelasan |
|----|-----------|--------|--------------------|
| 1 | `pwd` | Menampilkan direktori kerja saat ini | Output: `/home/alfan` |
| 2 | `ls -l` | Menampilkan daftar file dan folder secara detail | Menunjukkan folder `praktikum-week-3` dan `results` |
| 3 | `cd /tmp` | Berpindah ke direktori `/tmp` | Lokasi berpindah ke `/tmp` |
| 4 | `ls -a` | Menampilkan semua file termasuk yang tersembunyi | Terlihat file seperti `.X11-unix`, `snap-private-tmp`, dll |
| 5 | `cat /etc/passwd \| head -n 5` | Menampilkan 5 baris pertama dari file `/etc/passwd` | Menampilkan data akun sistem seperti root, daemon, bin, dsb |
| 6 | `echo "Hello Alfan Nur Fazilah - 250320575" > percobaan.txt` | Membuat file baru dan menulis teks ke dalamnya | File `percobaan.txt` berisi teks tersebut |
| 7 | `ls -l percobaan.txt` | Melihat izin, pemilik, ukuran, dan tanggal file | Awalnya: `-rw-r--r-- 1 alfan alfan ...` |
| 8 | `sudo chmod 600 percobaan.txt` | Mengubah izin file menjadi hanya pemilik yang bisa baca dan tulis | Izin berubah menjadi `-rw-------` |
| 9 | `sudo chown root percobaan.txt` | Mengubah pemilik file menjadi user `root` | Setelah perintah: `root alfan ...` |
| 10 | `sudo cat percobaan.txt` | Menampilkan isi file (karena sekarang dimiliki root) | Output: `Hello Alfan Nur Fazilah – 250320575` |






  

---

## Kesimpulan
1. Perintah chmod digunakan untuk mengatur izin akses file atau direktori, sedangkan chown digunakan untuk mengubah kepemilikan file.


2. Sistem Linux memiliki mekanisme keamanan berbasis hak akses (read, write, execute) yang membatasi siapa yang dapat mengakses atau memodifikasi file.


3. Praktikum menunjukkan bahwa hanya pengguna dengan hak yang sesuai (misalnya root) yang dapat mengubah izin atau kepemilikan file tertentu.


4. Pemahaman tentang izin file penting untuk menjaga keamanan dan integritas sistem operasi Linux.



---

## Quiz
1. Apa fungsi dari perintah `chmod`?  
   **Jawaban:**  Perintah chmod berfungsi untuk mengubah izin akses (read, write, execute) pada file atau direktori di sistem Linux.
2. Apa arti dari kode permission `rwxr-xr--`?  
   **Jawaban:**  Kode rwxr-xr-- artinya:

Pemilik (user): read, write, execute (rwx)

Grup: read, execute (r-x)

Lainnya (others): read saja (r--)

3.  Jelaskan perbedaan antara `chown` dan `chmod`.   
   **Jawaban:**  chown digunakan untuk mengubah pemilik (owner) dan grup dari suatu file atau direktori.

chmod digunakan untuk mengubah izin akses (read, write, execute) dari file atau direktori.

---

## Refleksi Diri
Tuliskan secara singkat:
- Bagian yang paling menantang minggu ini adalah tidak ada menurut saya semua bagian menantang
- Cara mengatasinya adalah bertanya kepada teman atau mencari tau di AI

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
